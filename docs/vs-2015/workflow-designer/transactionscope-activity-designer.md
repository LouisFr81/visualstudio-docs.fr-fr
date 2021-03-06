---
title: Concepteur d’activités TransactionScope | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 5ea9f0860bf1794ff8c5a4824a60b28aefd4c54d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49238483"
---
# <a name="transactionscope-activity-designer"></a>Concepteur d’activités TransactionScope
Le **TransactionScope** ActivityDesigner est utilisé pour créer et configurer un <xref:System.Activities.Statements.TransactionScope> activité.  
  
## <a name="the-transactionscope-activity"></a>Activité TransactionScope  
 L'activité <xref:System.Activities.Statements.TransactionScope> exécute l'activité contenue dans une transaction unique. La transaction est validée lorsque l'activité <xref:System.Activities.Statements.TransactionScope.Body%2A> et tous les autres participants de la transaction sont terminés.  
  
### <a name="using-the-transactionscope-activity-designer"></a>Utilisation du concepteur d’activités TransactionScope  
 Le **TransactionScope** Concepteur d’activités peut être trouvé dans le **Transaction** catégorie de la **boîte à outils**, qui est accessible en cliquant sur le **boîte à outils**  onglet de [!INCLUDE[wfd2](../includes/wfd2-md.md)] (ou bien, sélectionnez **barre d’outils** à partir de la **vue** menu ou CTRL + ALT + X.)  
  
 Le **TransactionScope** Concepteur d’activités peut être déplacé de la **boîte à outils** et déposé dans le [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface, là où les activités sont généralement placées, par exemple dans un <xref:System.Activities.Statements.Sequence>. Cette action crée une activité <xref:System.Activities.Statements.TransactionScope> avec TransactionScope comme <xref:System.Activities.Activity.DisplayName%2A> par défaut. Le <xref:System.Activities.Activity.DisplayName%2A> valeur peut être modifiée dans l’en-tête de la **TransactionScope** Concepteur d’activités ou dans le **DisplayName** case de la grille des propriétés.  
  
### <a name="the-transactionscope-properties"></a>Propriétés de TransactionScope  
 Le tableau suivant présente les propriétés de <xref:System.Activities.Statements.TransactionScope> et décrit comment elles sont utilisées dans le concepteur. Les propriétés <xref:System.Activities.Activity.DisplayName%2A> et <xref:System.Activities.Statements.TransactionScope.Body%2A> peuvent être modifiées dans l'aire de conception [!INCLUDE[wfd2](../includes/wfd2-md.md)]. En revanche, les autres propriétés doivent être modifiées dans la grille des propriétés.  
  
|Nom de la propriété|Obligatoire|Utilisation|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Nom convivial facultatif de l'activité <xref:System.Activities.Statements.TransactionScope>. La valeur par défaut est TransactionScope. Bien que la valeur de la propriété <xref:System.Activities.Activity.DisplayName%2A> ne soit pas strictement obligatoire, il est recommandé d'en utiliser une.|  
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|True|Spécifie l’activité à exécuter dans une transaction unique. Pour ajouter le <xref:System.Activities.Statements.TransactionScope.Body%2A> activité, déposez une activité de la **boîte à outils** dans le **corps** zone sur le **TransactionScope** Concepteur d’activités avec le texte d’indication « déposer l’activité « ici ».|  
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|True|Spécifie la valeur <xref:System.Transactions.IsolationLevel> de cet objet <xref:System.Activities.Statements.TransactionScope>.|  
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|Spécifie l'intervalle de temps (au format 00:00:00, qui correspond à heures:minutes:secondes) dont dispose la transaction pour se terminer. La valeur par défaut est égale à 1 minute (00:01:00).|  
|<xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure?qualifyHint=False&autoUpgrade=True>|True|Spécifie la valeur qui indique si le flux de travail doit être abandonné en cas d’abandon de la transaction.|  
  
## <a name="see-also"></a>Voir aussi  
 [Transaction](../workflow-designer/transaction-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Compenser](../workflow-designer/compensate-activity-designer.md)   
 [Confirm](../workflow-designer/confirm-activity-designer.md)