---
title: IDebugEngine2::SetRegistryRoot | Microsoft Docs
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
- IDebugEngine2::SetRegistryRoot
helpviewer_keywords:
- IDebugEngine2::SetRegistryRoot
ms.assetid: d0d81202-8a4a-4bc3-b297-30a047c5ec60
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa1e67c1d2c513fb4bc30c3daf064f4555172741
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816422"
---
# <a name="idebugengine2setregistryroot"></a>IDebugEngine2::SetRegistryRoot
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Définit la racine du Registre pour le moteur de débogage (dé).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT SetRegistryRoot(   
   LPCOLESTR pszRegistryRoot  
);  
```  
  
```csharp  
int SetRegistryRoot(   
   string pszRegistryRoot  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszRegistryRoot`  
 [in] La racine de Registre à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Cette méthode permet de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pour spécifier une racine de Registre autre que l’Allemagne doit utiliser pour obtenir les paramètres de Registre ; par exemple, « HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp ».  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)

