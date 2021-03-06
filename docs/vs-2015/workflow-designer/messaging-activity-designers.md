---
title: Concepteurs d’activités de messagerie | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 897e63cf-a42f-4edd-876f-c4ccfffaf6d6
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 254b8d819da8cd1d06d21699940c3b118aa75119
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274753"
---
# <a name="messaging-activity-designers"></a>Concepteurs d'activités de messagerie
Les concepteurs d'activités de messagerie permettent de créer et configurer des activités de messagerie qui envoient et reçoivent des messages [!INCLUDE[indigo1](../includes/indigo1-md.md)] à partir d'une application [!INCLUDE[wf](../includes/wf-md.md)]. Le [!INCLUDE[netfx40_long](../includes/netfx40-long-md.md)] introduit cinq activités de messagerie et [!INCLUDE[wfd1](../includes/wfd1-md.md)] fournit deux nouveaux concepteurs de modèles qui vous permettent de gérer la messagerie dans un workflow. Les rubriques contenues dans cette section et répertoriées dans le tableau suivant fournissent des conseils sur la façon d'utiliser les concepteurs d'activités et de modèles [!INCLUDE[wfd2](../includes/wfd2-md.md)].  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Activité de message|Description|  
|----------------------|-----------------|  
|[CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)|Crée et configure une activité <xref:System.ServiceModel.Activities.CorrelationScope> qui fournit une gestion implicite des activités de messagerie enfants avec un objet <xref:System.ServiceModel.Activities.CorrelationHandle>.|  
|[InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)|Crée et configure une activité <xref:System.ServiceModel.Activities.InitializeCorrelation> utilisée pour initialiser la corrélation sans envoyer ou recevoir de message.|  
|[Receive](../workflow-designer/receive-activity-designer.md)|Crée et configure une activité <xref:System.ServiceModel.Activities.Receive> qui reçoit un message d'un service.|  
|[ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)|Crée une paire préconfigurée d'activités <xref:System.ServiceModel.Activities.Send> et <xref:System.ServiceModel.Activities.ReceiveReply> dans une activité <xref:System.Activities.Statements.Sequence>.|  
|[Send](../workflow-designer/send-activity-designer.md)|Crée et configure une activité <xref:System.ServiceModel.Activities.Send> qui envoie un message à un service.|  
|[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)|Crée une paire préconfigurée d'activités <xref:System.ServiceModel.Activities.Receive> et <xref:System.ServiceModel.Activities.SendReply> dans une activité <xref:System.Activities.Statements.Sequence>.|  
|[TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)|Crée et configure une activité <xref:System.ServiceModel.Activities.TransactedReceiveScope> qui active le flux de transactions dans un workflow.|  
  
## <a name="reference"></a>Référence  
 <xref:System.Activities.Activity>  
  
 <xref:System.ServiceModel.Activities.CorrelationScope>  
  
 <xref:System.ServiceModel.Activities.Receive>  
  
 <xref:System.ServiceModel.Activities.Send>  
  
 <xref:System.ServiceModel.Activities.ReceiveReply>  
  
 <xref:System.ServiceModel.Activities.SendReply>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>  
  
## <a name="related-sections"></a>Rubriques connexes  
 Pour les autres types de concepteurs d'activités, consultez les rubriques suivantes.  
  
 [Flux de contrôle](../workflow-designer/control-flow-activity-designers.md)  
  
 [Utilisation des concepteurs d’activités](../workflow-designer/using-the-activity-designers.md)  
  
 [Organigramme](../workflow-designer/flowchart-activity-designers.md)  
  
 [Runtime](../workflow-designer/runtime-activity-designers.md)  
  
 [Primitives](../workflow-designer/primitives-activity-designers.md)  
  
 [Transaction](../workflow-designer/transaction-activity-designers.md)  
  
 [Collection](../workflow-designer/collection-activity-designers.md)  
  
 [Gestion des erreurs](../workflow-designer/error-handling-activity-designers.md)  
  
## <a name="external-resources"></a>Ressources externes  
 [Utilisation des concepteurs d’activités](../workflow-designer/using-the-activity-designers.md)