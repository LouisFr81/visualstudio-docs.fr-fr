---
title: IDebugPortSupplier3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3
helpviewer_keywords:
- IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ca7113a1b108713b5dd7cf0f17511cec39a1b8b6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695490"
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
Cette interface permet à un appelant déterminer si un fournisseur de port peut conserver les ports (en les écrivant sur le disque) entre les appels du débogueur, puis d’obtenir une liste de ces ports conservés.

## <a name="syntax"></a>Syntaxe

```
IDebugPortSupplier3 : IDebugPortSupplier2
```

## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs
 Un fournisseur de port personnalisé implémente cette interface pour prendre en charge la persistance ou de l’enregistrement des informations sur le port sur le disque. Cette interface doit être implémentée sur le même objet que le [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) interface.

## <a name="notes-for-callers"></a>Notes de publication pour les appelants
 Appelez [QueryInterface](/cpp/atl/queryinterface) sur la `IDebugPortSupplier2` interface pour obtenir cette interface.

## <a name="methods-in-vtable-order"></a>Méthodes dans l’ordre Vtable
 Outre les méthodes héritées de la [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) interface, cette interface prend en charge les éléments suivants :

|Méthode|Description|
|------------|-----------------|
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|Retourne si le fournisseur de port peut conserver les ports (en les écrivant sur le disque) entre les appels du débogueur.|
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|Retourne un objet qui peut être utilisé pour énumérer par tous les ports qui ont été écrites sur le disque par ce fournisseur de port.|

## <a name="remarks"></a>Notes
 Si un fournisseur de port peut conserver les ports entre les appels, il doit implémenter cette interface. Ports doivent être chargés lorsque le fournisseur de port est instancié et écrit sur le disque lorsque le fournisseur de port est détruit.

 En règle générale, un moteur de débogage n’interagit pas avec un fournisseur de port et sera d’aucune utilité pour cette interface.

## <a name="requirements"></a>Spécifications
 En-tête : msdbg.h

 Espace de noms : Microsoft.VisualStudio.Debugger.Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)