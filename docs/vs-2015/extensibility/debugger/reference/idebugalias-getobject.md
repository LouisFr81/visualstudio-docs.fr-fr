---
title: IDebugAlias::GetObject | Microsoft Docs
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
- IDebugAlias::GetObject
helpviewer_keywords:
- IDebugAlias::GetObject method
ms.assetid: 97bc3af6-6e55-4940-8a6d-692c61257806
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bb08d0199342b95ab58cccac3616be0fc061254e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51767453"
---
# <a name="idebugaliasgetobject"></a>IDebugAlias::GetObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obtient l’objet auquel cet alias est destinée.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetObject(  
   IDebugObject2** ppObject  
);  
```  
  
```csharp  
int GetObject(  
   Out IDebugObject2 ppObject  
)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ppObject`  
 [out] Le [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) représente cet alias.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne S_OK ; Sinon, retourne un code d’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)   
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)

