---
title: Interface IActiveScriptProfilerControl | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1448b394-9743-41b5-8eb9-5026a45773a4
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7caa09f384ce460a3e73b21b10d6d8022182dde7
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349489"
---
# <a name="iactivescriptprofilercontrol-interface"></a>IActiveScriptProfilerControl, interface
Implémenté par le moteur de script qui prend en charge le profilage. En règle générale, un objet qui implémente le `IActiveScriptProfilerControl` implémente également la [IActiveScript](../../winscript/reference/iactivescript.md) interface. Dans ce cas, vous pouvez obtenir un handle vers la `IActiveScriptProfilerControl` interface en appelant le `IUnknown::QueryInterface` méthode sur l’objet. L’interface fournit les méthodes nécessaires pour arrêter et démarrer le profilage sur le moteur de script.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)|Démarre le profilage sur le moteur de script.|  
|[IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)|Définit le profileur de masque d’événement dans le moteur de script.|  
|[IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)|Arrête le profilage sur le moteur de script.|  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces de profiler de script actif](../../winscript/reference/active-script-profiler-interfaces.md)