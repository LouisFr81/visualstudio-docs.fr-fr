---
title: IDebugDefaultPort2::QueryIsLocal | Microsoft Docs
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
- IDebugDefaultPort2::QueryIsLocal
helpviewer_keywords:
- IDebugDefaultPort2::QueryIsLocal
ms.assetid: 1a42e774-c6ed-419a-a0e3-cab5778652ca
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6d1df7e3af294e3e517dd4121b03ca3465946908
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51750523"
---
# <a name="idebugdefaultport2queryislocal"></a>IDebugDefaultPort2::QueryIsLocal
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette méthode détermine si ce port est sur l’ordinateur local.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` si ce port est local (sur le même ordinateur que l’appelant) ou `S_FALSE` si le port est sur un autre ordinateur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)

