---
title: DisplayKind | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DisplayKind enumeration
ms.assetid: 940968c5-6065-4bda-8ee6-c31597db4d71
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: afe6f0d4a77b841a1c0d696bf90502df8cb0fee1
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51773663"
---
# <a name="displaykind"></a>DisplayKind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Énumère les valeurs valides qui représentent les types d’informations à prendre dans un [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) de l’objet et l’afficher à l’utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
typedef DWORD DisplayKind;  
```  
  
```csharp  
public enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 DisplayKind_Value  
 Valeur du champ.  
  
 DisplayKind_Name  
 Nom du champ.  
  
 DisplayKind_Type  
 Type de champ.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : Ee.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)

