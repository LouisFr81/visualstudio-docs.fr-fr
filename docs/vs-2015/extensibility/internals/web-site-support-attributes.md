---
title: Attributs de prise en charge de Site Web | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 312d8a760cc7005afc4308b637b12a292bd20329
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51756690"
---
# <a name="web-site-support-attributes"></a>Attributs de prise en charge de site web
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Projet de site Web peut être étendu pour prendre en charge pour le Web, langages de programmation. La langue doit s’inscrire avec [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] afin que les modèles de projet peuvent apparaître dans le **nouveau Site Web** boîte de dialogue lors de la langue sélectionnée.  
  
 L’exemple de IronPython Studio inclut la prise en charge du site web. Vous pouvez le trouver avec le [exemples d’extensibilité Visual Studio](../../misc/vssdk-samples.md). Il inclut des classes d’attributs suivantes pour inscrire IronPython comme un langage de code-behind pour les nouveaux projets Web.  
  
## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute  
 Cet attribut est placé sur le projet de langage. Il ajoute la langue à la liste des langages de programmation Web le **langage** liste dans le **nouveau Site Web** boîte de dialogue. Par exemple, ce qui suit ajoute IronPython à la liste :  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Cet attribut définit également le chemin d’accès de modèles pour pointer vers le dossier de modèles. Pour plus d’informations sur l’emplacement du dossier de modèles, consultez [modèles de prise en charge de Site Web](../../extensibility/internals/web-site-support-templates.md).  
  
## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute  
 Cet attribut est placé sur le projet de langage. Il permet au projet de Site Web d’imbriquer un type de fichier (associé) sous un autre type de fichier (principal) dans le **l’Explorateur de solutions**.  
  
 Exemple :  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Spécifie qu’un fichier de code-behind IronPython est lié à un fichier .aspx. Création d’une page Web .aspx dans une solution de site Web de IronPython, un nouveau fichier de source .py est généré et apparaît sous la forme d’un nœud enfant de la page .aspx.  
  
## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute  
 Cet attribut est placé sur le package de projet de langage. Il sélectionne le fournisseur d’Intellisense pour la langue.  
  
 Exemple :  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 Spécifie qu’une instance de PythonIntellisenseProvider, qui implémente <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, doit être créée à la demande pour fournir des services de langage.  
  
 L’implémentation de IVsIntellisenseProject traite les références et appelle le compilateur de langage lorsqu’une page Web avec le code est demandée mais n’est pas mis en cache.  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de site Web](../../extensibility/internals/web-site-support.md)

