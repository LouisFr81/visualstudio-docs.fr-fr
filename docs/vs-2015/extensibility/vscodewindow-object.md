---
title: Objet VSCodeWindow | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e0abc38177bc10f4a8ddd9c20cbde1409de20ea3
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51727358"
---
# <a name="vscodewindow-object"></a>Objet VSCodeWindow
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Une fenêtre de code est une fenêtre de document spécialisé qui peut inclure une ou plusieurs vues de texte, généralement le <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objet.  
  
 Point de vue architectural, la fenêtre de code est une fenêtre de document qui se trouve dans un frame de fenêtre. Point de vue fonctionnel, la fenêtre de code est simplement une fenêtre de document avec des fonctionnalités supplémentaires. Dans le mode d’interface multidocument (MDI), la fenêtre de code est le frame enfant MDI. Pour plus d’informations, consultez [personnalisation de Code Windows à l’aide de l’API héritée](../extensibility/customizing-code-windows-by-using-the-legacy-api.md).  
  
 Le tableau suivant contient les interfaces dans le <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> objet.  
  
|Méthode|Description|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|Fournit un mécanisme d’accès génériques pour rechercher un service qui identifie un identificateur global unique (GUID).|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|Représente un enfant d’interface (multidocument MDI) document plusieurs contenant une ou plusieurs vues de code.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Remplit un frame de fenêtre.|  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Édition de figures](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)

