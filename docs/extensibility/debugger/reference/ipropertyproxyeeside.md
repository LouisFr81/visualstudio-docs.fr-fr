---
title: IPropertyProxyEESide | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide
helpviewer_keywords:
- IPropertyProxyEESide interface
ms.assetid: cf227cf8-39d9-4758-8f7e-a697aebb1926
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bdd9b804556cd748c921a0c21729daee56e9499b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708457"
---
# <a name="ipropertyproxyeeside"></a>IPropertyProxyEESide
Cette interface fournit des méthodes pour afficher les données sur l’objet associé. Cette interface fait partie de la prise en charge des visualiseurs de type.

## <a name="syntax"></a>Syntaxe

```
IPropertyProxyEESide : IUnknown
```

## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs
 Un évaluateur d’expression implémente cette interface pour prendre en charge les visualiseurs de type.

## <a name="notes-for-callers"></a>Notes de publication pour les appelants
 Appelez [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) pour obtenir cette interface. Appelez [QueryInterface](/cpp/atl/queryinterface) sur un [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) interface pour obtenir le [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) interface.

## <a name="methods-in-vtable-order"></a>Méthodes dans l’ordre Vtable
 Les méthodes suivantes sont implémentées par cette interface :

|Méthode|Description|
|------------|-----------------|
|[InitSourceDataProvider](../../../extensibility/debugger/reference/ipropertyproxyeeside-initsourcedataprovider.md)|Initialise un fournisseur de source de données afin que les données de l’objet est accessible.|
|[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)|Récupère les informations relatives à assembly l’objet.|
|[GetInitialData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getinitialdata.md)|Obtient les données initiales pour l’objet.|
|[CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)|Crée une copie d’un stockage de données existante.|
|[InPlaceUpdateObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md)|Crée une référence à un stockage de données existant.|
|[ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)|Récupère des informations sur un assembly spécifique dans le contexte de l’assembly contenant cet objet.|

## <a name="remarks"></a>Notes
 Un visualiseur de type utilise cette interface pour accéder aux valeurs associées à l’objet faisant partie de cette interface. Les données sont accessibles via le [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) interface, qui fournit une vue en lecture seule des données.

## <a name="requirements"></a>Spécifications
 En-tête : msdbg.h

 Espace de noms : Microsoft.VisualStudio.Debugger.Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [Visualiseur de type et visionneuse personnalisée](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)