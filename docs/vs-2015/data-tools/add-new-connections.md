---
title: Ajouter de nouvelles connexions | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a93c287-2834-4a83-a590-bdc3fe8d293f
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 03407962b4ea8160d492971367f121835fa39aae
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49218503"
---
# <a name="add-new-connections"></a>Ajouter de nouvelles connexions
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Vous pouvez tester votre connexion à une base de données ou un service et Explorer le contenu de la base de données et des schémas, à l’aide **Explorateur de serveurs**, **Cloud Explorer**, ou **Explorateur d’objets SQL Server**. Les fonctionnalités de ces fenêtres se chevauchent dans une certaine mesure. Les principales différences sont :  
  
 Explorateur de serveurs  
 Installé par défaut dans Visual Studio. Peut être utilisé pour tester les connexions et afficher les bases de données SQL Server, les autres bases de données ayant un fournisseur ADO.NET installé et certains services Azure. Montre également les objets de bas niveau tels que les compteurs de performances système, les journaux des événements et les files d’attente. Si une source de données n’a aucun fournisseur ADO.NET, il n’apparaît pas ici, mais vous pouvez toujours utiliser il à partir de Visual Studio en vous connectant par programmation.  
  
 Cloud Explorer  
 Installez cette fenêtre manuellement comme une extension Visual Studio en sélectionnant **outils** > **Extensions et mises à jour** > **Online**  >  **Galerie visual Studio**. Fournit des fonctionnalités spécialisées pour l’exploration et la connexion aux services Azure.  
  
 Explorateur d'objets SQL Server  
 Installé avec SQL Server Data Tools et visible sous le **vue** menu. Si vous n’apparaît pas, accédez à **programmes et fonctionnalités** dans le panneau de configuration, recherchez Visual Studio, puis sélectionnez **modification** exécuter à nouveau le programme d’installation après avoir sélectionné la case à cocher pour SQL Server Data Tools. Utilisez **Explorateur d’objets SQL Server** vue SQL bases de données (si elles ont un fournisseur ADO.NET), créer de nouvelles bases de données, modifier des schémas, créer des procédures stockées, récupérer les chaînes de connexion, afficher les données et bien plus encore. Les bases de données SQL disposant d’aucun fournisseur ADO.NET installé n’apparaîtront pas ici, mais vous pouvez toujours y connecter par programmation.  
  
## <a name="add-a-connection-in-server-explorer"></a>Ajouter une connexion dans l’Explorateur de serveurs  
 Pour créer une connexion à la base de données, cliquez sur le **ajouter une connexion** icône dans **Explorateur de serveurs**, ou avec le bouton droit dans **Explorateur de serveurs** sur la **données Connexions** nœud et sélectionnez **ajouter une connexion**. À ce stade, vous pouvez également vous connecter à une base de données sur un autre serveur, un service SharePoint ou un service Azure.  
  
 ![Icône d’Explorer la nouvelle connexion serveur](../data-tools/media/raddata-server-explorer-new-connection-icon.png "icône de nouvelle connexion de serveur Explorateur raddata")  
  
 Ceci fait apparaître la **ajouter une connexion** boîte de dialogue. Ici, nous avons entré le nom de l’instance de SQL Server LocalDB.  
  
 ![Ajouter une nouvelle connexion](../data-tools/media/raddata-add-new-connection-dialog.png "raddata boîte de dialogue Ajouter nouvelle connexion")  
  
## <a name="change-the-provider"></a>Modifier le fournisseur  
 Si la source de données n’est pas ce que vous souhaitez, cliquez sur le **modification** pour choisir une source de données et/ou un nouveau fournisseur de données ADO.NET. Le nouveau fournisseur peut demander vos informations d’identification, en fonction de sa configuration.  
  
 ![Modifier le fournisseur de données AD0.NET](../data-tools/media/raddata-change-ad0-net-data-provider.png "raddata AD0.NET modification du fournisseur de données")  
  
## <a name="test-the-connection"></a>Tester la connexion  
 Une fois que vous avez choisi la source de données, cliquez sur **tester la connexion**. Si elle n’aboutit pas, vous devez résoudre les problèmes en fonction de la documentation du fournisseur.  
  
 ![Tester la connexion](../data-tools/media/raddata-test-connection.png "raddata tester la connexion")  
  
 Si le test réussit, vous êtes prêt à créer un *source de données*, qui est un terme de Visual Studio signifie en réalité un *modèle de données* qui repose sur la base de données ou le service sous-jacent.  
  
## <a name="see-also"></a>Voir aussi  
 [Outils de données Visual Studio pour .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)

