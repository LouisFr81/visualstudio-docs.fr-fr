---
title: -Project (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- project Devenv switch (/project)
- Devenv, /project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d048edd60d41c3f08a8bd0b731beddb3619a1887
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54776067"
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Identifie un projet unique dans la configuration de solution spécifiée à générer, nettoyer, regénérer ou déployer.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName   
[/project ProjName] [/projectconfig ProjConfigName]   
```  
  
## <a name="arguments"></a>Arguments  
 /build  
 Génère le projet spécifié par `/project` `ProjName`.  
  
 /clean  
 Nettoie tous les fichiers intermédiaires et répertoires de sortie créés pendant une génération.  
  
 /rebuild  
 Nettoie puis génère le projet spécifié par `/project` `ProjName`.  
  
 /deploy  
 Spécifie que le projet doit être déployé après une génération ou une régénération.  
  
 `SolnConfigName`  
 Obligatoire. Nom de la configuration de solution à appliquer à la solution nommée dans `SolutionName`.  
  
 `SolutionName`  
 Obligatoire. Chemin complet et nom du fichier solution.  
  
 /project `ProjName`  
 Optionnel. Chemin et nom d’un fichier projet dans la solution. Vous pouvez entrer un chemin relatif du dossier `SolutionName` vers le fichier projet, le nom d’affichage du projet ou encore le chemin complet et le nom du fichier projet.  
  
 /projectconfig `ProjConfigName`  
 Optionnel. Nom d’une configuration de build de projet à appliquer au `/project` nommé.  
  
## <a name="remarks"></a>Remarques  
  
-   Doit être utilisé dans le cadre d’une commande `devenv /build`, /`clean`, `/rebuild` ou `/deploy`.  
  
-   Placez entre guillemets doubles les chaînes contenant des espaces.  
  
-   Vous pouvez afficher des informations récapitulatives sur les builds, y compris sur les erreurs, dans la fenêtre **Commande** ou dans tout fichier journal spécifié avec le commutateur `/out`.  
  
## <a name="example"></a>Exemple  
 Cet exemple génère le projet `CSharpConsoleApp` en utilisant la configuration de génération de projet `Debug` présente dans la configuration de solution `Debug` de `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Voir aussi  
 [Commutateurs de la ligne de commande Devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)   
 [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Deploy (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
