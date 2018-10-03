---
title: IDebugCodeContext2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCodeContext2
helpviewer_keywords:
- IDebugCodeContext2 interface
ms.assetid: 3670439e-2171-405d-9d77-dedb0f1cba93
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c22d29a4bdd575f093087f0385919968c9f0cc96
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47505225"
---
# <a name="idebugcodecontext2"></a>IDebugCodeContext2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [IDebugCodeContext2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcodecontext2).  
  
Cette interface représente la position de départ d’une instruction de code. Pour la plupart des architectures d’exécution dès aujourd'hui, un contexte de code peut être considéré comme une adresse dans le flux de l’exécution d’un programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCodeContext2 : IDebugMemoryContext2  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Le moteur de débogage implémente cette interface pour associer la position d’une instruction de code vers une position de document.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Les méthodes sur le nombre d’interfaces retournent cette interface, plus généralement, [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md). Il est également largement utilisé avec le [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) interface ainsi que dans les informations de résolution de point d’arrêt.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Outre les méthodes sur le [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) interface, cette interface implémente les méthodes suivantes :  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)|Obtient le contexte de document correspondant au contexte de code actif.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugcodecontext2-getlanguageinfo.md)|Obtient les informations de langue pour ce contexte de code.|  
  
## <a name="remarks"></a>Notes  
 La principale différence entre un `IDebugCodeContext2` interface et un [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) interface est qu’un `IDebugCodeContext2` est toujours instruction aligné. Cela signifie qu’un `IDebugCodeContext2` pointe toujours vers le début d’une instruction, tandis qu’un `IDebugMemoryContext2` peut pointer vers n’importe quel octet de mémoire dans l’architecture de l’exécution. `IDebugCodeContext2` est incrémenté par instructions plutôt que par la taille de stockage de base (généralement octets).  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)   
 [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)   
 [Suivant](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
