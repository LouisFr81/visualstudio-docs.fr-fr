---
title: WriteCodeFragment, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, WriteCodeFragment task
- WriteCodeFragment task [MSBuild]
ms.assetid: 1d2514b4-5bef-43bb-bebe-496da8ef063c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6c99a5c953238498e5a780c2cd731500af2f5c23
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54963513"
---
# <a name="writecodefragment-task"></a>WriteCodeFragment (tâche)
Génère un fichier de code temporaire à partir du fragment de code généré spécifié. Ne supprime pas le fichier.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `WriteCodeFragment` .  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`AssemblyAttributes`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem>`[]` facultatif.<br /><br /> Description des attributs à écrire. La valeur `Include` de l’élément correspond au nom de type complet de l’attribut, par exemple, « System.AssemblyVersionAttribute ».<br /><br /> Chaque métadonnée correspond à la paire nom-valeur d’un paramètre, qui doit être de type `String`. Certains attributs autorisent uniquement les arguments de constructeur. Toutefois, vous pouvez utiliser ces arguments dans n’importe quel attribut. Pour définir les attributs de constructeur positionnel, utilisez les noms de métadonnées qui ressemblent à « _Parameter1 », « _Parameter2 » , etc.<br /><br /> Vous ne pouvez pas ignorer un index de paramètre.|  
|`Language`|Paramètre `String` requis.<br /><br /> Spécifie le langage du code à générer.<br /><br /> `Language` peut être n’importe quel langage disposant d’un fournisseur CodeDom, par exemple, « C# » ou « VisualBasic ». Le fichier émis porte l’extension de nom de fichier par défaut du langage en question.|  
|`OutputDirectory`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le dossier de destination du code généré, en général le dossier intermédiaire.|  
|`OutputFile`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le chemin du fichier qui a été généré. Si ce paramètre est défini à l’aide d’un nom de fichier, le dossier de destination est ajouté devant le nom de fichier. S’il est défini à l’aide d’une racine, le dossier de destination est ignoré.<br /><br /> Si ce paramètre n’est pas défini, le nom du fichier de sortie est constitué du nom du dossier de destination, d’un nom de fichier arbitraire et de l’extension de nom de fichier par défaut du langage spécifié.|  
  
## <a name="remarks"></a>Notes  
 En plus des paramètres répertoriés dans le tableau, cette tâche comprend des paramètres qu’elle hérite de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches](../msbuild/msbuild-tasks.md)   
 [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)