---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs
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
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 67f1d4580d2722c1043c9287cd1eae4c6084dd7f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51736333"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tente de déterminer pourquoi un auto-attach a échoué.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszUrl`  
 [in] Actuellement non utilisé ; doit toujours être défini sur une valeur null.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur. Autres codes de retour standard sont les suivantes :  
  
|Code|Description|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Impossible de déterminer pourquoi le serveur distant a échoué démarrer le débogage.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Impossible de déboguer sur un serveur distant, probablement en raison d’autorisations insuffisantes ou parce que l’exécution du verbe DEBUG n’est pas activé.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Le serveur web a été verrouillé et bloque l’exécution du verbe DEBUG, ce qui est nécessaire pour activer le débogage.|  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)

