---
title: Appbreakflags, énumération | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- APPBREAKFLAGS
apilocation:
- scrobj.dll
helpviewer_keywords:
- APPBREAKFLAGS constants
ms.assetid: ea8ed80f-2ddb-4800-bb3b-52b76ba6c7a0
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49d9cef3583def8cd23e135b960e46979446b3bb
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349021"
---
# <a name="appbreakflags-enumeration"></a>APPBREAKFLAGS, énumération
Indique l'état actuel du débogage des applications et des threads.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_APPBREAKFLAGS{APPBREAKFLAG_DEBUGGER_BLOCK= 0x00000001,APPBREAKFLAG_DEBUGGER_HALT= 0x00000002,APPBREAKFLAG_STEP= 0x00010000,APPBREAKFLAG_NESTED= 0x00020000,APPBREAKFLAG_STEPTYPE_SOURCE= 0x00000000,APPBREAKFLAG_STEPTYPE_BYTECODE= 0x00100000,APPBREAKFLAG_STEPTYPE_MACHINE= 0x00200000,APPBREAKFLAG_STEPTYPE_MASK= 0x00F00000,APPBREAKFLAG_IN_BREAKPOINT= 0x80000000};  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Value|Description|  
|------------|-----------|-----------------|  
|APPBREAKFLAG_DEBUGGER_BLOCK|0x00000001|Moteur de langage doit s’arrêter immédiatement sur tous les threads avec BREAKREASON_DEBUGGER_BLOCK.|  
|APPBREAKFLAG_DEBUGGER_HALT|0x00000002|Moteur de langage doit s’arrêter immédiatement avec BREAKREASON_DEBUGGER_HALT.|  
|APPBREAKFLAG_STEP|0x00010000|Moteur de langage doit s’arrêter immédiatement dans le thread d’exécution pas à pas avec BREAKREASON_STEP.|  
|APPBREAKFLAG_NESTED|0x00020000|L’application est dans une exécution imbriquée sur un point d’arrêt.|  
|APPBREAKFLAG_STEPTYPE_SOURCE|0x00000000|Le débogueur à passer au niveau de la source.|  
|APPBREAKFLAG_STEPTYPE_BYTECODE|0x00100000|Le débogueur à passer au niveau du code d’octet.|  
|APPBREAKFLAG_STEPTYPE_MACHINE|0x00200000|Le débogueur à passer au niveau de l’ordinateur.|  
|APPBREAKFLAG_STEPTYPE_MASK|0x00F00000|Masque de factoriser les types d’étapes.|  
|APPBREAKFLAG_IN_BREAKPOINT|0x80000000|Un point d’arrêt est en cours.|  
  
## <a name="remarks"></a>Notes  
 Certains indicateurs de spécifient que les moteurs de langage doivent s’arrêter à la prochaine occasion, tandis que les autres indicateurs de spécifient le mode d’exécution pas à pas du débogueur.  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, énumérations et constantes de débogueur de Script actif](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)   
 [Énumération BREAKREASON](../../winscript/reference/breakreason-enumeration.md)