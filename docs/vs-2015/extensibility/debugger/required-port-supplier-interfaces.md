---
title: Interfaces de fournisseur de Port requises | Microsoft Docs
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
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 485c295e7258f09aaf4114d5945f8136057447e6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51782802"
---
# <a name="required-port-supplier-interfaces"></a>Interfaces de fournisseur de ports nécessaires
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un fournisseur de port doit implémenter le [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) interface.[ IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 La mesure où un fournisseur de port fournit des ports, il doit également implémenter les. Par conséquent, il doit implémenter les interfaces suivantes :  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     Décrit le port et pouvez énumérer tous les processus en cours d’exécution sur le port.  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     Fournit pour lancer et arrêter les processus sur le port.  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     Fournit un mécanisme pour les programmes en cours d’exécution dans le contexte de ce port pour l’informer de la création de nœuds de programme et la destruction. Pour plus d’informations, consultez [programme nœuds](../../extensibility/debugger/program-nodes.md).  
  
-   `IConnectionPointContainer`  
  
     Fournit un point de connexion pour [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md).  
  
## <a name="port-supplier-operation"></a>Opération de fournisseur de port  
 Le [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md) récepteur reçoit des notifications lorsque le processus et les programmes sont créés et détruits sur un port. Un port est requis pour envoyer [IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md) lors de la création d’un processus et [IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md) quand un processus sont détruit sur le port. Un port est également nécessaire pour envoyer [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) lors de la création d’un programme et [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) quand un programme est détruit dans un processus en cours d’exécution sur le port.  
  
 Un port généralement envoie programme créer et détruire les événements en réponse à la [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) et [RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) méthodes, respectivement.  
  
 Comme un port peut lancer et terminer le processus physiques et logiques programmes, ces interfaces doivent également être implémentées par le moteur de débogage :  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     Décrit le processus physique. Au moins les méthodes suivantes doivent être implémentées :  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [GetProcessId](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     Fournit un moyen pour le SDM attacher et détacher lui-même d’un processus.  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     Décrit le programme logique. Au moins les méthodes suivantes doivent être implémentées :  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     Fournit un moyen pour le SDM attacher à ce programme.  
  
## <a name="see-also"></a>Voir aussi  
 [Implémentation d’un fournisseur de port](../../extensibility/debugger/implementing-a-port-supplier.md)

