---
title: Enregistrer les données avec le DBDirect du TableAdapter méthodes | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- TableAdapters, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], TableAdapter
ms.assetid: 74a6773b-37e1-4d96-a39c-63ee0abf49b1
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6b7a7ec1d244f8bf711f0d1aaf4726c910846357
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50219716"
---
# <a name="save-data-with-the-tableadapter-dbdirect-methods"></a>Enregistrer des données avec les méthodes DBDirect du TableAdapter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Cette procédure pas à pas fournit des instructions détaillées pour l’exécution des instructions SQL directement sur une base de données en utilisant les méthodes DBDirect d’un TableAdapter. Les méthodes DBDirect d’un TableAdapter fournissent un niveau de contrôle sur vos mises à jour de la base de données. Vous pouvez les utiliser pour exécuter des instructions SQL et les procédures stockées en appelant l’individu `Insert`, `Update`, et `Delete` méthodes selon les besoins de votre application (par opposition à surchargées `Update` méthode qui effectue la mise à jour Instructions INSERT et DELETE dans un seul appel).  
  
 Pendant cette procédure pas à pas, vous allez apprendre à :  
  
-   Créer un nouveau **Windows Application**.  
  
-   Créer et configurer un jeu de données avec le [Assistant de Configuration de Source de données](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f).  
  
-   Sélectionnez le contrôle à créer sur le formulaire lorsque vous faites glisser des éléments à partir de la **des Sources de données** fenêtre. Pour plus d’informations, consultez [définir le contrôle à créer lors du déplacement de la fenêtre Sources de données](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
-   Créer un formulaire lié aux données en faisant glisser des éléments à partir de la **des Sources de données** fenêtre vers le formulaire.  
  
-   Ajouter des méthodes pour accéder à la base de données directement et d’effectuer des insertions, mises à jour et suppressions...  
  
## <a name="prerequisites"></a>Prérequis  
 Pour exécuter cette procédure pas à pas, vous avez besoin des éléments suivants :  
  
-   avoir accès à l'exemple de base de données Northwind. Pour plus d’informations, consultez [Comment : installer Sample Databases](../data-tools/how-to-install-sample-databases.md).  
  
## <a name="create-a-windows-application"></a>Créer une application Windows  
 La première étape consiste à créer un **Windows Application**.  
  
#### <a name="to-create-the-new-windows-project"></a>Pour créer un projet Windows  
  
1.  Dans Visual Studio, sur le **fichier** menu, créez un **projet**.  
  
2.  Nommez le projet **TableAdapterDbDirectMethodsWalkthrough**.  
  
3.  Sélectionnez **Windows Application**, puis sélectionnez **OK**. Pour plus d’informations, consultez [les Applications clientes](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68).  
  
     Le **TableAdapterDbDirectMethodsWalkthrough** projet est créé et ajouté à **l’Explorateur de solutions**.  
  
## <a name="create-a-data-source-from-your-database"></a>Créer une source de données à partir de votre base de données  
 Cette étape utilise le **Assistant de Configuration de Source de données** pour créer une source de données basée sur le `Region` table dans la base de données Northwind. Vous devez avoir accès à l'exemple de base de données Northwind pour créer la connexion. Pour plus d’informations sur la configuration de la base de données Northwind, consultez [Comment : installer Sample Databases](../data-tools/how-to-install-sample-databases.md).  
  
#### <a name="to-create-the-data-source"></a>Pour créer la source de données  
  
1.  Sur le **données** menu, sélectionnez **afficher les Sources de données**.  
  
2.  Dans le **des Sources de données** fenêtre, sélectionnez **ajouter une nouvelle Source de données** pour démarrer le **Assistant de Configuration de Source de données**.  
  
3.  Sur le **choisir un Type de Source de données** s’affiche, sélectionnez **base de données**, puis sélectionnez **suivant**.  
  
4.  Sur le **choisir votre connexion de données** , effectuez une des opérations suivantes :  
  
    -   Si une connexion de données à l’exemple de base de données Northwind est disponible dans la liste déroulante, sélectionnez-la.  
  
         - ou -  
  
    -   Sélectionnez **nouvelle connexion** pour lancer le **Ajouter/modifier la connexion** boîte de dialogue.  
  
5.  Si votre base de données requiert un mot de passe, sélectionnez l’option pour inclure les données sensibles, puis sélectionnez **suivant**.  
  
6.  Sur le **enregistrer la chaîne de connexion dans le fichier de Configuration de l’Application** s’affiche, sélectionnez **suivant**.  
  
7.  Sur le **choisir vos objets de base de données** écran, développez le **Tables** nœud.  
  
8.  Sélectionnez le `Region` table, puis sélectionnez **Terminer**.  
  
     Le **NorthwindDataSet** est ajouté à votre projet et le `Region` table s’affiche dans le **des Sources de données** fenêtre.  
  
## <a name="addcontrols-to-the-form-to-display-the-data"></a>Addcontrols au formulaire pour afficher les données  
 Créer les contrôles liés aux données en faisant glisser des éléments à partir de la **des Sources de données** fenêtre vers votre formulaire.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Pour créer des données des contrôles sur le formulaire Windows liés  
  
-   Faites glisser le **région** nœud à partir de la **des Sources de données** fenêtre vers le formulaire.  
  
     Un contrôle <xref:System.Windows.Forms.DataGridView> et une barre d'outils (<xref:System.Windows.Forms.BindingNavigator>) pour parcourir les enregistrements apparaissent dans le formulaire. Un [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), [RegionTableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource>, et <xref:System.Windows.Forms.BindingNavigator> s’affichent dans la barre d’état du composant.  
  
#### <a name="to-add-buttons-that-will-call-the-individual-tableadapter-dbdirect-methods"></a>Pour ajouter des boutons pour appeler les méthodes DbDirect individuelles de TableAdapter  
  
1.  Faites glisser trois <xref:System.Windows.Forms.Button> des contrôles de la **boîte à outils** sur **Form1** (sous le **RegionDataGridView**).  
  
2.  Définissez les éléments suivants **nom** et **texte** propriétés sur chaque bouton.  
  
    |Name|Texte|  
    |----------|----------|  
    |`InsertButton`|**Insert**|  
    |`UpdateButton`|**Mettre à jour**|  
    |`DeleteButton`|**Supprimer**|  
  
#### <a name="to-add-code-to-insert-new-records-into-the-database"></a>Pour ajouter du code afin d'insérer de nouveaux enregistrements dans la base de données  
  
1.  Sélectionnez **InsertButton** pour créer un gestionnaire d’événements pour l’événement click et ouvrir votre formulaire dans l’éditeur de code.  
  
2.  Remplacez le gestionnaire d'événements `InsertButton_Click` par le code suivant :  
  
     [!code-csharp[VbRaddataSaving#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#1)]
     [!code-vb[VbRaddataSaving#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#1)]  
  
#### <a name="to-add-code-to-update-records-in-the-database"></a>Pour ajouter du code afin de mettre à jour des enregistrements dans la base de données  
  
1.  Double-cliquez sur le **UpdateButton** pour créer un gestionnaire d’événements pour l’événement click et ouvrir votre formulaire dans l’éditeur de code.  
  
2.  Remplacez le gestionnaire d'événements `UpdateButton_Click` par le code suivant :  
  
     [!code-csharp[VbRaddataSaving#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#2)]
     [!code-vb[VbRaddataSaving#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#2)]  
  
#### <a name="to-add-code-to-delete-records-from-the-database"></a>Pour ajouter du code pour supprimer des enregistrements à partir de la base de données  
  
1.  Sélectionnez **DeleteButton** pour créer un gestionnaire d’événements pour l’événement click et ouvrir votre formulaire dans l’éditeur de code.  
  
2.  Remplacez le gestionnaire d'événements `DeleteButton_Click` par le code suivant :  
  
     [!code-csharp[VbRaddataSaving#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#3)]
     [!code-vb[VbRaddataSaving#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#3)]  
  
## <a name="run-the-application"></a>Exécuter l'application  
  
#### <a name="to-run-the-application"></a>Pour exécuter l’application  
  
-   Sélectionnez **F5** pour exécuter l’application.  
  
-   Sélectionnez le **insérer** bouton et vérifiez que le nouvel enregistrement apparaît dans la grille.  
  
-   Sélectionnez le **mise à jour** bouton, puis vérifiez que l’enregistrement est mis à jour dans la grille.  
  
-   Sélectionnez le **supprimer** bouton et vérifiez que l’enregistrement est supprimé de la grille.  
  
## <a name="next-steps"></a>Étapes suivantes  
 Selon les exigences de votre application, il existe plusieurs étapes, que vous souhaiterez peut-être effectuer après la création d’un formulaire lié aux données. Vous pouvez apporter à cette procédure pas à pas les améliorations suivantes :  
  
-   Ajout d'une fonctionnalité de recherche au formulaire. Pour plus d’informations, consultez [Comment : ajouter une requête paramétrable à une Application de formulaires Windows](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416).  
  
-   Ajout de tables supplémentaires au jeu de données en sélectionnant **configurer le jeu de données avec l’Assistant** depuis le **des Sources de données** fenêtre. Vous pouvez ajouter des contrôles pour afficher les données associées en faisant glisser les nœuds associés vers le formulaire. Pour plus d’informations, consultez la page [Comment : afficher des données connexes dans une application Windows Forms](../data-tools/how-to-display-related-data-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Enregistrer les données dans la base de données](../data-tools/save-data-back-to-the-database.md)

