---
title: Concepteur de flux de travail - Concepteur d’activités DoWhile
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a0069d352897d2d98288988d549d9733a39b2c35
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918362"
---
# <a name="dowhile-activity-designer"></a>Concepteur d'activités DoWhile

Le <xref:System.Activities.Statements.DoWhile> activité s’exécute l’activité contenue dans son <xref:System.Activities.Statements.DoWhile.Body%2A> au moins une fois, jusqu'à ce qu’une condition spécifiée a la valeur **false**. Si vous devez exécuter zéro ou plusieurs fois l'activité contenue dans le corps d'une boucle, utilisez plutôt l'activité <xref:System.Activities.Statements.While>.

## <a name="dowhile-properties-in-the-workflow-designer"></a>Propriétés de DoWhile dans Workflow Designer

Le tableau suivant présente les plus utiles <xref:System.Activities.Statements.DoWhile> propriétés d’activité et décrit comment les utiliser dans le concepteur :

|Nom de la propriété|Obligatoire|Utilisation|
|-|--------------|-|
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|L’activité à exécuter pendant que la condition est **true**. Pour ajouter le <xref:System.Activities.Statements.DoWhile.Body%2A> activité, déposez une activité à partir de la boîte à outils dans le **corps** zone sur le **DoWhile** Concepteur d’activités avec le texte d’indication « Déposer l’activité ici ».|
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|True|Condition à évaluer après chaque itération de la boucle. Pour définir le <xref:System.Activities.Statements.DoWhile.Condition%2A>, tapez une expression Visual Basic dans le **Condition** zone sur le **DoWhile** activité concepteur ou dans la grille des propriétés.|

## <a name="see-also"></a>Voir aussi

- [While](../workflow-designer/while-activity-designer.md)
- [Flux de contrôle](../workflow-designer/control-flow-activity-designers.md)