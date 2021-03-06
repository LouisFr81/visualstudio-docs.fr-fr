---
title: Énumération PROFILER_SCRIPT_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- PROFILER_SCRIPT_TYPE
apilocation:
- scrobj.dll
ms.assetid: 3ab6633a-6241-44f0-b837-14336f70c71e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ac387af4601ff822982c10e61f9813b2db7e8047
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086904"
---
# <a name="profilerscripttype-enumeration"></a>PROFILER_SCRIPT_TYPE, énumération
Spécifie le type de script.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum {  
    PROFILER_SCRIPT_TYPE_USER,  
    PROFILER_SCRIPT_TYPE_DYNAMIC,  
    PROFILER_SCRIPT_TYPE_NATIVE,  
    PROFILER_SCRIPT_TYPE_DOM  
} PROFILER_SCRIPT_TYPE;  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|PROFILER_SCRIPT_TYPE_USER|Spécifie le code de script écrit par l’utilisateur.|  
|PROFILER_SCRIPT_TYPE_DYNAMIC|Spécifie le code de script qui est généré dynamiquement pendant l’exécution.|  
|PROFILER_SCRIPT_TYPE_NATIVE|Spécifie le type de script pour des fonctions natives et les objets qui sont définis par le moteur de script.|  
|PROFILER_SCRIPT_TYPE_DOM|Spécifie un appel dans le modèle DOM (Document Object) d’Internet Explorer, par exemple, un appel à la `document.getElementById` (méthode).|  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes de Profiler de Script actif, énumérations et structures](../../winscript/reference/active-script-profiler-constants-enumerations-and-structures.md)   
 [IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)   
 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)   
 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)