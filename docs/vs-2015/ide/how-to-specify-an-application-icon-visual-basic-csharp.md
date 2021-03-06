---
title: 'Procédure : Spécifier une icône d’Application (Visual Basic, C#) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
ms.assetid: ad8e14ed-adc2-45b6-a0be-818b16d5616f
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7f794f1c988215f8899dce495f725b3a9c14a435
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788163"
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Guide pratique pour spécifier une icône d'application (Visual Basic, C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La propriété `Icon` d'un projet spécifie le fichier de l'icône (.ico) qui sera affichée pour l'application compilée dans l'Explorateur de fichiers et dans la barre des tâches Windows.  
  
 La propriété `Icon` est accessible dans le volet **Application** du **Concepteur de projet**. Elle contient une liste des icônes qui ont été ajoutées à un projet comme ressources ou comme fichiers de contenu.  
  
> [!NOTE]
>  Après avoir défini la propriété Icon pour une application, vous pouvez également définir la propriété `Icon` de chaque **Fenêtre** ou **Formulaire** de l’application. Pour plus d'informations sur les icônes de fenêtre pour les applications autonomes Windows Presentation Foundation (WPF), consultez la propriété <xref:System.Windows.Window.Icon%2A>.  
  
### <a name="to-specify-an-application-icon"></a>Pour spécifier une icône d'application  
  
1.  Dans l’**Explorateur de solutions**, choisissez un nœud de projet (pas le nœud **Solution**).  
  
2.  Dans la barre de menus, choisissez **Projet**, **Propriétés**.  
  
3.  Quand le **Concepteur de projet** apparaît, choisissez l’onglet **Application**.  
  
4.  **(Visual Basic)** Dans la liste **Icône**, sélectionnez un fichier icône (.ico).  
  
     **C#** À côté de la liste **Icône**, choisissez le bouton **\<Parcourir...>**, puis accédez à l’emplacement du fichier icône souhaité.  
  
## <a name="see-also"></a>Voir aussi  
 [Page Application, Concepteur de projets (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Page Application, Concepteur de projets (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Gestion des propriétés de l’application](../ide/application-properties.md)  
 [Guide pratique pour Ajouter ou supprimer des ressources](http://msdn.microsoft.com/7b77bc06-3952-4799-b029-def3f8f7f88d)
