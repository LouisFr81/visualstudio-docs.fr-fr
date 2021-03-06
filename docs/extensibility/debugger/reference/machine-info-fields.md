---
title: MACHINE_INFO_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MACHINE_INFO_FIELDS
helpviewer_keywords:
- MACHINE_INFO_FIELDS enumeration
ms.assetid: 2d61d206-7d40-4df1-8c88-1b3c9c78821e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 61a22a1868a47fd4b54b19cf224f995897775b4f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708405"
---
# <a name="machineinfofields"></a>MACHINE_INFO_FIELDS
Spécifie le genre d’informations à récupérer pour un ordinateur particulier.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_MACHINE_INFO_FIELDS { 
   MCIF_NAME  = 0x00000001,
   MCIF_FLAGS = 0x00000002,
   MCIF_ALL   = 0x00000003
};
typedef DWORD MACHINE_INFO_FIELDS;
```

```csharp
public enum enum_MACHINE_INFO_FIELDS { 
   MCIF_NAME  = 0x00000001,
   MCIF_FLAGS = 0x00000002,
   MCIF_ALL   = 0x00000003
};
```

## <a name="members"></a>Membres
 MCIF_NAME Initialize/utiliser le `bstrName` champ dans la structure.

 MCIF_FLAGS Initialize/utiliser le `Flags` champ dans la structure.

 MIF_ALL Initialize/utiliser tous les champs dans la structure.

## <a name="remarks"></a>Notes
 Ces valeurs sont passées à la [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md) méthode pour indiquer quels membres de la [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) structure doivent être initialisées.

 Également utilisé dans le `Fields` membre de la `MACHINE_INFO` structure pour indiquer quels champs sont utilisés et valide.

 Ces indicateurs peuvent être combinées avec un opérateur de bits `OR`.

## <a name="requirements"></a>Spécifications
 En-tête : msdbg.h

 Espace de noms : Microsoft.VisualStudio.Debugger.Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md)
- [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)