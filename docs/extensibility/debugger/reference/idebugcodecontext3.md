---
title: IDebugCodeContext3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 911869a1d727e466cbf2d43557946efaba1f7dd4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56687872"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
Étend la [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) interface pour permettre l’extraction des interfaces de module et de processus.

## <a name="syntax"></a>Syntaxe

```
IDebugCodeContext3 : IDebugCodeContext2
```

## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs
 Implémenté par les moteurs de débogage et consommé par le [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] déboguer le package.

## <a name="methods"></a>Méthodes
 Outre les méthodes sur le `IDebugCodeContext2` interface, cette interface implémente les méthodes suivantes :

|Méthode|Description|
|------------|-----------------|
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Récupère une référence à l’interface du module de débogage.|
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Récupère une référence à l’interface du processus de débogage.|

## <a name="remarks"></a>Notes
 Il s’agit d’une interface facultative qui n’a généralement pas être implémentée.

## <a name="requirements"></a>Spécifications
 En-tête : Msdbg.h

 Espace de noms : Microsoft.VisualStudio.Debugger.Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll