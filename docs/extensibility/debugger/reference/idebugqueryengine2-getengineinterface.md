---
title: IDebugQueryEngine2::GetEngineInterface | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5b5ac40af5f508a00b010025f9851ee2a8933dfa
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720968"
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
Obtient une interface de (dé) de moteur de débogage personnalisé.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEngineInterface( 
   IUnknown** ppUnk
);
```

```csharp
int GetEngineInterface( 
   out object ppUnk
);
```

#### <a name="parameters"></a>Paramètres
 `ppUnk`

 [out] Retourne un `IUnknown` objet représente le moteur de débogage (DE), et qui peut être interrogée pour toute autre interface valide associée à un DE (par exemple [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) ou [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)).

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 L’interface qui en résulte doit être utilisée avec précaution, car l’appel des interfaces récupérées à partir de cette méthode contourne le traitement du Gestionnaire de débogage de session et peut entraîner le SDM bien dans un état incorrect ou en générant des erreurs pendant le débogage.

## <a name="see-also"></a>Voir aussi
- [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)