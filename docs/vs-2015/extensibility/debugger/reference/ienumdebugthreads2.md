---
title: IEnumDebugThreads2 | Microsoft Docs
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
- IEnumDebugThreads2
helpviewer_keywords:
- IEnumDebugThreads2
ms.assetid: 1854f078-3b49-42c2-b65b-33e3b506fd63
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9b60d62846ce777897784e005457fe6cf2ca272a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51754519"
---
# <a name="ienumdebugthreads2"></a>IEnumDebugThreads2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interfac énumère les threads en cours d’exécution dans la session de débogage actuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugThreads2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Le moteur de débogage (dé) implémente cette interface pour représenter une liste de threads dans un programme.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Appelez [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md) pour obtenir cette interface représentant une liste de tous les threads dans tous les programmes en cours d’exécution dans un processus. Appelez [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) pour obtenir cette interface représentant une liste de threads en cours d’exécution dans un programme.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IEnumDebugThreads2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)|Récupère un nombre spécifié de threads dans la séquence d’énumération.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugthreads2-skip.md)|Ignore un nombre spécifié de threads dans une séquence d’énumération.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugthreads2-reset.md)|Réinitialise une séquence d’énumération au début.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugthreads2-clone.md)|Crée un énumérateur qui contient le même état d’énumération que celui en cours.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugthreads2-getcount.md)|Obtient le nombre de threads dans un énumérateur.|  
  
## <a name="remarks"></a>Notes  
 Visual Studio obtient généralement cette interface pour mettre à jour le **Threads** fenêtre ainsi que pour obtenir le premier thread de la liste, afin d’appeler [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md), [continuer](../../../extensibility/debugger/reference/idebugprocess3-continue.md), et [Étape](../../../extensibility/debugger/reference/idebugprocess3-step.md).  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)   
 [Étape](../../../extensibility/debugger/reference/idebugprocess3-step.md)   
 [Continuer](../../../extensibility/debugger/reference/idebugprocess3-continue.md)   
 [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md)

