---
title: TaskExtension, classe de base | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, tool task base class
- tool task base class [MSBuild]
ms.assetid: 08bb8059-b7e2-4565-89ba-d9034d4f0e16
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f21bc2eacdc6886410e03ea80fad451c32abfc3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949400"
---
# <a name="taskextension-base-class"></a>Classe de base TaskExtension
De nombreuses tâches héritent de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, laquelle hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Cette chaîne d'héritage ajoute plusieurs paramètres aux tâches qui en dérivent. Ces paramètres sont répertoriés dans ce document.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres des classes de base.  
  
|Paramètre|Description|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Paramètre <xref:Microsoft.Build.Framework.IBuildEngine> facultatif.<br /><br /> Spécifie l'interface du moteur de génération disponible pour les tâches. Le moteur de génération définit automatiquement ce paramètre pour permettre aux tâches d’être rappelées.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Paramètre <xref:Microsoft.Build.Framework.IBuildEngine2> facultatif.<br /><br /> Spécifie l'interface du moteur de génération disponible pour les tâches. Le moteur de génération définit automatiquement ce paramètre pour permettre aux tâches d’être rappelées.<br /><br /> Il s’agit d’une propriété de convenance qui permet aux auteurs de tâches qui héritent de cette classe de ne pas avoir à effectuer un cast de la valeur de `IBuildEngine` vers `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Paramètre <xref:Microsoft.Build.Framework.IBuildEngine3> facultatif.<br /><br /> Spécifie l'interface du moteur de génération fournie par l'hôte.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Paramètre <xref:Microsoft.Build.Framework.ITaskHost> facultatif.<br /><br /> Spécifie l'instance de l'objet hôte (peut être null). Le moteur de génération définit cette propriété si l’IDE hôte a associé un objet hôte à cette tâche particulière.|  
|<xref:Microsoft.Build.Tasks.TaskExtension.Log%2A>|Paramètre en lecture seule <xref:Microsoft.Build.Utilities.TaskLoggingHelper> facultatif.<br /><br /> Obtient un objet `TaskLoggingHelperExtension` qui contient des méthodes de journalisation des tâches.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)   
 [Tâches](../msbuild/msbuild-tasks.md)