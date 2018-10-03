---
title: Guide pratique pour résoudre les problèmes des modèles | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, troubleshooting
ms.assetid: 3e577ad2-f725-4c11-93b3-477f2404ec81
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b249fe28f91a8dfb24e73ab86f785103910ee9d9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47502667"
---
# <a name="how-to-troubleshoot-templates"></a>Comment : dépanner des modèles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Comment : résoudre les problèmes de modèles](https://docs.microsoft.com/visualstudio/ide/how-to-troubleshoot-templates).  
  
Si le chargement d’un modèle dans l’environnement de développement échoue, il existe plusieurs façons de procéder pour localiser le problème.  
  
## <a name="validating-the-vstemplate-file"></a>Validation du fichier .vstemplate  
 Si le fichier .vstemplate d’un modèle n’adhère pas au schéma de modèle [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], il se peut que le modèle n’apparaisse pas dans la boîte de dialogue **Nouveau projet**.  
  
#### <a name="to-validate-the-vstemplate-file"></a>Pour valider le fichier .vstemplate  
  
1.  Localisez le fichier .zip qui contient le modèle.  
  
2.  Extrayez le fichier zip.  
  
3.  Dans le menu **Fichier**, de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], cliquez sur **Ouvrir**, puis sur **Fichier**.  
  
4.  Sélectionnez le fichier .vstemplate du modèle, puis cliquez sur **Ouvrir**.  
  
5.  Vérifiez que le code XML du fichier .vstemplate adhère au schéma de modèle [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Pour plus d’informations sur le schéma .vstemplate, consultez [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md).  
  
    > [!NOTE]
    >  Pour obtenir la prise en charge IntelliSense lorsque vous créez le fichier .vstemplate, ajoutez un `xmlns` attribut le `VSTemplate` élément et lui attribuer une valeur de http://schemas.microsoft.com/developer/vstemplate/2005.  
  
6.  Enregistrez et fermez le fichier .vstemplate.   
  
7.  Sélectionnez les fichiers inclus dans votre modèle, cliquez avec le bouton droit, sélectionnez **Envoyer vers**, puis cliquez sur **Dossier compressé**. Les fichiers que vous avez sélectionnés sont compressés dans un fichier .zip.  
  
8.  Placez le nouveau fichier .zip dans le même répertoire que l’ancien fichier .zip.  
  
9. Supprimez les fichiers de modèles extraits et l'ancien fichier .zip du modèle.  
  
## <a name="monitoring-the-event-log"></a>Analyse du journal des événements  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] journalise les erreurs rencontrées lors du traitement des fichiers .zip du modèle. Si un modèle n’apparaît pas dans la boîte de dialogue **Nouveau projet** comme prévu, vous pouvez utiliser l’**observateur d’événements** pour résoudre le problème.  
  
#### <a name="to-locate-template-errors-in-event-viewer"></a>Pour localiser des erreurs de modèle dans l’observateur d’événements  
  
1.  Dans Windows, cliquez sur **Démarrer**, sur **Panneau de configuration**, et double-cliquez sur **Outils d’administration**, puis sur **Observateur d’événements**.  
  
2.  Dans le volet gauche, cliquez sur **Application**.  
  
3.  Recherchez les événements dont la **Source** a la valeur `Visual Studio - VsTemplate`.  
  
4.  Double-cliquez sur un événement de modèle pour afficher l’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation des modèles](../ide/customizing-project-and-item-templates.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)


