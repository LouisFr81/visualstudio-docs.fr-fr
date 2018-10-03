---
title: Évaluation de l’expression (Kit de développement logiciel de débogage de Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation
ms.assetid: 5044ced5-c18c-4534-b0bf-cc3e50cd57ac
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bd5fb9ac88b2535c897978cdd63f9cf0716d53a1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47502603"
---
# <a name="expression-evaluation-visual-studio-debugging-sdk"></a>Évaluation d’expression (SDK de débogage Visual Studio)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [évaluation des expressions (débogage SDK Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk).  
  
En mode arrêt, l’IDE doit être en mesure d’évaluer des expressions simples impliquant plusieurs variables de votre programme. Pour ce faire, le moteur de débogage (dé) doit être en mesure d’analyser et évaluer une expression qui est entrée dans une des fenêtres de l’IDE.  
  
 Les expressions sont créées à l’aide de la [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) (méthode) et sont représentées par résultant [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) interface.  
  
 Le **IDebugExpression2** interface est implémentée par les appels DE son **EvalAsync** méthode pour retourner un [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) interface à l’IDE, afin d’afficher le résultats de l’évaluation d’expression dans l’IDE. [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) retourne une structure qui peut être utilisée pour mettre la valeur d’une expression dans une fenêtre Espion ou dans la fenêtre variables locales.  
  
 Le package ou la session de débogage Gestionnaire de débogage (SDM) appelle [IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ou [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) pour obtenir un [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) interface qui représente le résultat de l’évaluation. `IDebugProperty2` a des méthodes qui retournent le nom, le type et la valeur de l’expression. Ces informations sont affichées dans les différentes fenêtres du débogueur.  
  
## <a name="using-expression-evaluation"></a>Avec l’évaluation d’Expression  
 Pour utiliser la version d’évaluation de l’expression, vous devez implémenter le [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) (méthode) et toutes les méthodes de la [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) interface, comme indiqué dans le tableau suivant.  
  
|Méthode|Description|  
|------------|-----------------|  
|[EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|Évalue une expression de façon asynchrone.|  
|[Abort](../../extensibility/debugger/reference/idebugexpression2-abort.md)|Termine l’évaluation de l’expression asynchrone.|  
|[EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|Évalue une expression de façon synchrone.|  
  
 Évaluation synchrone et asynchrone requièrent l’implémentation de la [IDebugProperty2::GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) (méthode). Évaluation des expressions asynchrones nécessite l’implémentation de [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de l’exécution et évaluation de l’état](../../extensibility/debugger/execution-control-and-state-evaluation.md)
