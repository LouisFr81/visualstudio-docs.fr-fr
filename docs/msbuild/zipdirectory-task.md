---
title: ZipDirectory, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ZipDirectory
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ZipDirectory task [MSBuild]
- MSBuild, ZipDirectory task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: Mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b09c98fb41adcf1d094ca3cf35e9415773e5c292
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54963526"
---
# <a name="zipdirectory-task"></a>Tâche ZipDirectory
Crée une archive *.zip* à partir du contenu d’un répertoire.

>[!NOTE]
>La tâche `ZipDirectory` n’est disponible qu’à partir de MSBuild 15.8.
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `ZipDirectory` .  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`DestinationFile`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> obligatoire<br /><br /> Chemin d’accès complet du fichier *.zip* à créer.|
|`Overwrite`|Paramètre `Boolean` facultatif.<br /><br /> Si la valeur est `true`, le fichier de destination est remplacé s’il existe. La valeur par défaut est `false`.|
|`SourceDirectory`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> requis.<br /><br /> Spécifie le répertoire à partir duquel sera créée une archive *.zip*.|
  
## <a name="remarks"></a>Notes  
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée une archive *.zip* à partir du répertoire de sortie après la génération d’un projet.
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="ZipOutputPath" AfterTargets="Build">
        <ZipDirectory
            SourceDirectory="$(OutputPath)"
            DestinationFile="$(MSBuildProjectDirectory)\output.zip" />
    </Target>

</Project>
```
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)
