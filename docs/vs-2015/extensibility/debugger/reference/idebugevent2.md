---
title: IDebugEvent2 | Microsoft Docs
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
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e3d4b1022d8eda4cfb992e9bfcc997193a84ee37
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51770016"
---
# <a name="idebugevent2"></a>IDebugEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface est utilisée pour communiquer des informations de débogage critiques, tels que l’arrêt à un point d’arrêt et les informations non critiques, par exemple, un message de débogage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Le moteur de débogage (dé) et le fournisseur de port personnalisé implémentent cette interface sur le même objet en tant que toutes les autres interfaces d’événement.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 À l’aide de l’interface argument ID (IID) donné à [événement](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) ou [événement](../../../extensibility/debugger/reference/idebugportevents2-event.md), appelle le Gestionnaire de session de débogage (SDM) [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) sur la `IDebugEvent2` interface à obtenir l’interface d’événements approprié.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDebugEvent2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Obtient les attributs de cet événement de débogage.|  
  
## <a name="remarks"></a>Notes  
 Interfaces de l’événement plus spécifique, tel que [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), ne dérivent pas de l’interface IDebugEvent2 mais sont plutôt implémentées comme une interface distincte sur le même objet en tant que `IDebugEvent2`.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Événement](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

