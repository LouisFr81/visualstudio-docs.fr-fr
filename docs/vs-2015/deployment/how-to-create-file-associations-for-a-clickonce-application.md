---
title: 'Comment : créer des Associations de fichiers pour une Application ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: fd1bd7965f0277ce1d3d900be6ee10db097eeb3f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49909105"
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>Comment : créer des associations de fichiers pour une application ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] applications peuvent être associées à une ou plusieurs extensions de nom de fichier afin que l’application démarrera automatiquement quand l’utilisateur ouvre un fichier de ces types. Ajout du support d’extension de nom de fichier à un [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application est simple.  
  
### <a name="to-create-file-associations-for-a-clickonce-application"></a>Pour créer des associations de fichiers pour une application ClickOnce  
  
1. Créer un [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application normalement, ou utilisez votre [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application.  
  
2. Ouvrez le manifeste d’application avec un texte ou un éditeur XML, tel que le bloc-notes.  
  
3. Recherchez l’élément `assembly` . Pour plus d’informations, consultez [Manifeste d’application ClickOnce](../deployment/clickonce-application-manifest.md).  
  
4. En tant qu’enfant de le `assembly` élément, ajoutez un `fileAssociation` élément. Le `fileAssociation` élément présente quatre attributs :  
  
   - `extension`: L’extension de nom de fichier à associer avec l’application.  
  
   - `description`: Description du type de fichier, qui apparaîtra dans l’interpréteur de commandes Windows.  
  
   - `progid`: Chaîne identifiant de manière unique le type de fichier pour le marquer dans le Registre.  
  
   - `defaultIcon`: Une icône à utiliser pour ce type de fichier. L’icône doit être ajoutée comme une ressource de fichier dans le manifeste d’application. Pour plus d'informations, consultez [Comment : inclure un fichier de données dans une application ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
     Pour obtenir un exemple de la `file` et `fileAssociation` éléments, consultez [ \<fileAssociation > élément](../deployment/fileassociation-element-clickonce-application.md).  
  
5. Si vous souhaitez associer plusieurs types de fichier à l’application, ajoutez d’autres `fileAssociation` éléments. Notez que le `progid` attribut doit être différent pour chacun.  
  
6. Une fois que vous avez terminé avec le manifeste d’application, signer à nouveau le manifeste. Faire cela à partir de la ligne de commande à l’aide de Mage.exe.  
  
    `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
    Pour plus d’informations, consultez [Mage.exe (Manifest Generation and Editing Tool)](http://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)  
  
## <a name="see-also"></a>Voir aussi  
 [\<fileAssociation > élément](../deployment/fileassociation-element-clickonce-application.md)   
 [Manifeste d’application ClickOnce](../deployment/clickonce-application-manifest.md)   
 [Mage.exe (outil Manifest Generation and Editing)](http://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)



