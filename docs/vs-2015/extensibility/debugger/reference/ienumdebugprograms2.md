---
title: IEnumDebugPrograms2 | Microsoft Docs
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
- IEnumDebugPrograms2
helpviewer_keywords:
- IEnumDebugPrograms2
ms.assetid: 7fbb8fb7-db64-4546-a364-dc668430c8af
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4a39fd4c6fa6621ac00e3bfe98060229509cb750
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51726144"
---
# <a name="ienumdebugprograms2"></a>IEnumDebugPrograms2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface énumère les programmes en cours d’exécution dans la session de débogage actuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugPrograms2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Le moteur de débogage (dé) implémente cette interface pour fournir une liste des programmes en cours de débogage par le DE.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Les appels de Visual Studio [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) pour obtenir cette interface. [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md) n’est pas utilisé par Visual Studio.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IEnumDebugPrograms2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)|Récupère un nombre spécifié de programmes dans une séquence d’énumération.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprograms2-skip.md)|Ignore un nombre spécifié de programmes dans une séquence d’énumération.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugprograms2-reset.md)|Réinitialise une séquence d’énumération au début.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugprograms2-clone.md)|Crée un énumérateur qui contient le même état d’énumération que l’énumérateur en cours.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprograms2-getcount.md)|Obtient le nombre de programmes dans un énumérateur.|  
  
## <a name="remarks"></a>Notes  
 Visual Studio utilise cette interface pour :  
  
-   Remplir le **Modules** fenêtre (en appelant [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) , puis en appelant [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) sur chaque programme).  
  
-   Remplir le **attacher au processus** liste (en appelant `IDebugProcess2::EnumPrograms` , puis en appelant [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) sur chaque [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) interface pour obtenir un [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md) interface).  
  
-   Générer une liste DEs, qui peut déboguer chaque programme dans le processus (à l’aide de [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)).  
  
-   Appliquer des mises à jour de modifier & Continuer (ENC) pour chaque programme (en appelant IDebugProcess2::EnumPrograms, puis [GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)).  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)

