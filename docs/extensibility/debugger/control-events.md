---
title: Événements de contrôle | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8fbe2f3c3835c55fffefe4692c4e8779b48e9c5e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683387"
---
# <a name="control-events"></a>Événements de contrôle
Vous devez envoyer des événements pendant l’exécution contrôlée de votre programme. Tous les événements sont envoyés à l’aide de la [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) interface et ont des attributs qui vous obligent à implémenter le [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) (méthode).

## <a name="additional-methods"></a>Méthodes supplémentaires
 Certains événements nécessitent l’implémentation des méthodes supplémentaires, comme suit :

- Envoi de la [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) interface lorsque le moteur de débogage (dé) est initialisé, vous devez implémenter le [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) (méthode).

- Contrôle de l’exécution nécessite l’implémentation de ces événements de contrôle comme le [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) et[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) interfaces. **IDebugBreakEvent2** est requis uniquement pour les sauts asynchrones.

- Entrer dans les fonctions nécessite l’implémentation de la [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) interface et ses méthodes.

  Dérivation à partir de points d’arrêt des événements requièrent l’implémentation de la [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md), [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), et [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) interfaces, ainsi que le [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) et [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) méthodes.

  Évaluation des expressions asynchrones, vous devez implémenter le [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) interface et sa [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md) [et GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) méthodes.

  Événements synchrones nécessitent la mise en œuvre le [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) (méthode).

  Pour votre moteur écrire la sortie de type chaîne, vous devez implémenter le [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) (méthode).

## <a name="see-also"></a>Voir aussi
- [Évaluation de contrôle et l’état d’exécution](../../extensibility/debugger/execution-control-and-state-evaluation.md)