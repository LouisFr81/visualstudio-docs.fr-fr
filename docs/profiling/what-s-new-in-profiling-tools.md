---
title: Nouveautés du profilage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling
- what's new
ms.assetid: d4736cc8-8961-4089-be9e-d5190ce8353c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1822ec74903c8baa75ce437b0115cecdfb911c3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55026943"
---
# <a name="whats-new-in-profiling-tools-in-includevsdev15miscincludesvsdev15mdmd"></a>Nouveautés des outils de profilage dans [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Les outils de diagnostics incluent de nouvelles visualisations pour vous aider à identifier dans votre application les problèmes devant être résolus. Les outils de diagnostics incluent désormais la prise en charge des applications ASP.NET.

Pour plus d’informations, consultez les [Notes de publication pour [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]](/visualstudio/releasenotes/vs2017-relnotes#debuggingdiag).

Un onglet **Résumé** a été ajouté aux outils pour vous permettre de vous concentrer sur les domaines clés pour l’analyse des performances. Cet onglet affiche le nombre d’événements qui se sont produits et vous permet de prendre des instantanés du tas et d’autoriser une collecte rapide des données d’utilisation du processeur. Cette vue présente tous les événements [Application Insights](/azure/azure-monitor/app/visual-studio) ou d’[analyse de l’interface utilisateur](/visualstudio/releasenotes/vs2017-relnotes#UIAnalysis). Pour Visual Studio Enterprise, cette vue affiche en plus les événements IntelliTrace.

![Onglet Résumé des outils de diagnostics](../profiling/media/DiagToolsSummaryTab-2.png "DiagToolsSummaryTab")

L’outil d’utilisation du processeur a de [nouvelles visualisations](../profiling/Beginners-Guide-to-Performance-Profiling.md) pour vous aider à identifier les fonctions qui sont susceptibles de causer des problèmes de performances. La nouvelle vue **Appelant/Appelé** vous permet d’examiner les coûts des appels de fonction effectués vers et depuis une fonction sélectionnée.

![Outils de diagnostics - Vue Appelant/appelé](../profiling/media/DiagToolsCallerCallee.png "DiagToolsCallerCallee")

## <a name="see-also"></a>Voir aussi

- [Profiler dans Visual Studio](../profiling/index.md)
- [Découvrir les outils de profilage](../profiling/profiling-feature-tour.md)