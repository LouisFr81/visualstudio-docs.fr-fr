---
title: IDebugStackFrame2::EnumProperties | Microsoft Docs
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
- IDebugStackFrame2::EnumProperties
helpviewer_keywords:
- IDebugStackFrame2::EnumProperties
ms.assetid: 334bb95e-c7e0-4008-9f06-8c3999e47ee8
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5144a96c5bcf5b73cad98816059d1023ed61ca2b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51748380"
---
# <a name="idebugstackframe2enumproperties"></a>IDebugStackFrame2::EnumProperties
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Crée un énumérateur pour les propriétés associées avec le frame de pile, telles que des variables locales.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnumProperties (   
   DEBUGPROP_INFO_FLAGS      dwFieldSpec,  
   UINT                      nRadix,  
   REFIID                    refiid,  
   DWORD                     dwTimeout,  
   ULONG*                    pcelt,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumProperties (   
   enum_DEBUGPROP_INFO_FLAGS   dwFieldSpec,  
   uint                        nRadix,  
   ref Guid                    refiid,  
   uint                        dwTimeout,  
   out uint                    pcelt,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dwFieldSpec`  
 [in] Une combinaison d’indicateurs de la [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) énumération qui spécifie les champs dans la liste énumérée [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) structures doivent être renseignés.  
  
 `nRadix`  
 [in] La base à utiliser dans toutes les informations numériques de mise en forme.  
  
 `refiid`  
 [in] Un GUID d’un filtre pour sélectionner les [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) structures sont énumérés, tel que `guidFilterLocals`.  
  
 `dwTimeout`  
 [in] Durée maximale, en millisecondes, à attendre avant de retourner à partir de cette méthode. Utilisez `INFINITE` pour attendre indéfiniment.  
  
 `pcelt`  
 [out] Retourne le nombre de propriétés énumérées. Ceci est le même que si vous appelez le [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md) (méthode).  
  
 `ppEnum`  
 [out] Retourne un [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objet contenant une liste des propriétés souhaitées.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Étant donné que cette méthode permet à toutes les propriétés sélectionnées être récupéré avec un seul appel, il est plus rapide que l’appel de manière séquentielle les [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) et [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) méthodes.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)   
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)

