---
title: IDebugBreakpointRequest3::GetRequestInfo2 | Microsoft Docs
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
- IDebugBreakpointRequest3::GetRequestInfo2
helpviewer_keywords:
- IDebugBreakpointRequest3::GetRequestInfo2
ms.assetid: 33942e4a-0a0a-49e8-a693-004954f6d38a
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 62c04aef42571eebe96e2f03b3cc99eedd8e7b3e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47516734"
---
# <a name="idebugbreakpointrequest3getrequestinfo2"></a>IDebugBreakpointRequest3::GetRequestInfo2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [IDebugBreakpointRequest3::GetRequestInfo2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2).  
  
Cette méthode obtient les informations de demande de point d’arrêt qui décrit cette demande de point d’arrêt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetRequestInfo2(  
   BPREQI_FIELDS      dwFields,  
   BP_REQUEST_INFO2*  bBPRequestInfo  
);  
```  
  
```csharp  
int GetRequestInfo2(  
   enum_BPREQI_FIELDS  dwFields,   
   BP_REQUEST_INFO2[]  bBPRequestInfo  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dwFields`  
 [in] Une combinaison d’indicateurs de la [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) énumération qui déterminent quels champs de `pBPRequestInfo` doivent être renseignés.  
  
 `bBPRequestInfo`  
 [out] Le [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) structure doit être renseigné.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne le code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Il existe plus d’informations dans cette demande qu’est retourné à partir de la [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugBreakpointRequest3](../../../extensibility/debugger/reference/idebugbreakpointrequest3.md)   
 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)
