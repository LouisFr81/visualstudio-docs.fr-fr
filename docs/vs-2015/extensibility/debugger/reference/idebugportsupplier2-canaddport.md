---
title: IDebugPortSupplier2::CanAddPort | Microsoft Docs
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
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e29478d71b60376bbd396650935e6257d11a7d37
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51769727"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vérifie qu’un fournisseur de port peut ajouter de nouveaux ports.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Si le port peut être ajouté, retourne `S_OK`; sinon, retourne `S_FALSE` pour indiquer aucune ports ne peuvent être ajoutés à ce fournisseur de port.  
  
## <a name="remarks"></a>Notes  
 Appelez cette méthode avant d’appeler le [ajouter un port](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) (méthode), car cette dernière méthode crée le port ainsi que l’ajout, qui pourrait être une opération longue.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)

