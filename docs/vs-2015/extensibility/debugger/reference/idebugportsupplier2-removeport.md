---
title: IDebugPortSupplier2::RemovePort | Microsoft Docs
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
- IDebugPortSupplier2::RemovePort
helpviewer_keywords:
- IDebugPortSupplier2::RemovePort
ms.assetid: f5c1fbf2-9084-46f2-a682-7db963928df2
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d7f3c9481dd50be00528ce6306222edab9e20a62
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807346"
---
# <a name="idebugportsupplier2removeport"></a>IDebugPortSupplier2::RemovePort
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Supprime un port.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT RemovePort(   
   IDebugPort2* pPort  
);  
```  
  
```csharp  
int RemovePort(   
   IDebugPort2 pPort  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pPort`  
 [in] Un [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) objet qui représente le port à supprimer.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Cette méthode supprime le port à partir de la liste interne du fournisseur de port des ports actifs.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)

