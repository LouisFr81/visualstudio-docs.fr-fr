---
title: 'Comment : ignorer des erreurs dans des tâches | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, ignoring errors
- ContinueOnError attribute [MSBuild]
ms.assetid: e2f1ca4f-787b-44bd-bc64-81a036025e96
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 186662f9c9bca72ca7ee840d1f2efc6437a7ccc4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47502690"
---
# <a name="how-to-ignore-errors-in-tasks"></a>Comment : ignorer des erreurs dans des tâches
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Comment : ignorer des erreurs dans des tâches](https://docs.microsoft.com/visualstudio/msbuild/how-to-ignore-errors-in-tasks).  
  
  
Vous souhaiterez parfois qu’une génération soit à tolérance de panne dans certaines tâches. En cas d’échec de ces tâches non critiques, vous souhaiterez continuer la génération, car elle peut toujours produire la sortie requise. Par exemple, si un projet utilise une tâche `SendMail` pour envoyer un message électronique après la génération de chaque composant, vous pouvez juger acceptable de poursuivre la génération jusqu’à son achèvement, même si les serveurs de messagerie ne sont pas disponibles et que les messages d’état ne peuvent pas être envoyés. Si des fichiers intermédiaires sont habituellement supprimés pendant la génération, vous pouvez également estimer que la génération peut se poursuivre jusqu’à son achèvement, même si ces fichiers ne peuvent pas être supprimés.  
  
## <a name="using-the-continueonerror-attribute"></a>Utilisation de l’attribut ContinueOnError  
 L’attribut `ContinueOnError` de l’élément `Task` contrôle si une génération s’arrête ou se poursuit en cas d’échec d’une tâche. Cet attribut détermine également si les erreurs sont considérées comme des erreurs ou des avertissements si la génération se poursuit.  
  
 L’attribut `ContinueOnError` peut contenir l’une des valeurs suivantes :  
  
-   **WarnAndContinue** ou **true**. En cas d’échec d’une tâche, l’exécution des tâches suivantes de l’élément [Target](../msbuild/target-element-msbuild.md) et de la génération se poursuit, et toutes les erreurs de la tâche sont considérées comme des avertissements.  
  
-   **ErrorAndContinue**. En cas d’échec d’une tâche, l’exécution des tâches suivantes de l’élément `Target` et de la génération se poursuit, et toutes les erreurs de la tâche sont considérées comme des erreurs.  
  
-   **ErrorAndStop** ou **false** (par défaut). En cas d’échec d’une tâche, les tâches restantes de l’élément `Target` et de la génération ne sont pas exécutées, et tout l’élément `Target` ainsi que la génération sont considérés comme étant en échec.  
  
 Les versions de .NET Framework antérieures à 4.5 prenaient en charge uniquement les valeurs `true` et `false`.  
  
 La valeur par défaut de `ContinueOnError` est `ErrorAndStop`. Si vous définissez l’attribut sur `ErrorAndStop`, vous rendez le comportement explicite pour tout lecteur du fichier projet.  
  
#### <a name="to-ignore-an-error-in-a-task"></a>Pour ignorer une erreur dans une tâche  
  
-   Utilisez l’attribut `ContinueOnError` de la tâche. Exemple :  
  
     `<Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>`  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant montre que la cible `Build` continue de s’exécuter, et la génération est considérée comme un succès, même en cas d’échec de la tâche `Delete`.  
  
```  
<Project DefaultTargets="FakeBuild"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Files Include="*.obj"/>  
    </ItemGroup>  
    <Target Name="Clean">  
        <Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>  
    </Target>  
  
    <Target Name="FakeBuild" DependsOnTargets="Clean">  
        <Message Text="Building after cleaning..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi
[MSBuild](msbuild.md)  
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)   
 [Tâches](../msbuild/msbuild-tasks.md)

