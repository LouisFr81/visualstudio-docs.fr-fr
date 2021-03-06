---
title: IDebugStopCompleteEvent2 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b64c9719c6d2975829451dbf11cf584f98805c1b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51780475"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Le moteur de débogage (dé) peut envoyer cet événement facultatif le Gestionnaire de session de débogage (SDM) lorsqu’un programme s’est arrêté.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Il s’agit d’une nouvelle interface pour [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]. Les versions antérieures ne prenaient pas en charge l’arrêt asynchrone.  
  
 [Arrêter](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) est appelée par le SDM dans les scénarios à plusieurs processus ou programme multiples. Lorsqu’un programme envoie un événement d’arrêt pour le SDM, le SDM demande arrêter trop d’autres programmes.  
  
 Il est utilisé pour informer de manière asynchrone le SDM un programme s’est arrêté. Cela est utile pour un moteur de débogage interpréteur, où parfois aucun code n’est en cours d’exécution à l’intérieur du programme débogué, donc [arrêter](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) ne peut pas être effectuée de façon synchrone. Si un moteur de débogage veut employer cette notification asynchrone, elle doit retourner `S_ASYNC_STOP` de [arrêter](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

