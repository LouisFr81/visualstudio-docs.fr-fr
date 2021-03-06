---
title: Boîte de dialogue Pages de propriété de Source des fichiers, les propriétés communes, Solution de débogage | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 84bf975065d73cd2d25994855a4c8a236f706e3b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51744680"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>Fichiers sources pour le débogage, Propriétés communes, boîte de dialogue Pages de propriétés de Solution
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette page de propriétés spécifie à quel endroit le débogueur recherchera les fichiers sources lors du débogage de la solution.  
  
 Pour accéder à la **déboguer les fichiers sources** page de propriétés, avec le bouton droit sur votre Solution dans **l’Explorateur de solutions** et sélectionnez **propriétés** dans le menu contextuel. Développez le **propriétés communes** dossier, puis cliquez sur le **déboguer les fichiers sources** page.  
  
 **Répertoires contenant du code source**  
 Contient la liste des répertoires dans lesquels le débogueur recherche les fichiers sources lors du débogage de la solution. Les sous-répertoires des dossiers spécifiés sont également récupérés.  
  
 **Ne pas rechercher ces fichiers source**  
 Entrez le nom des fichiers que vous souhaitez soustraire à la lecture du débogueur. Si le débogueur trouve un de ces fichiers dans un des répertoires spécifiés précédemment, il l'ignore. Si le **rechercher la Source** boîte de dialogue s’affiche pendant que vous déboguez et que vous cliquez sur **Annuler**, le fichier que vous recherchiez est ajouté à cette liste afin que le débogueur ne continue pas à rechercher ce fichier.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité du débogueur](../debugger/debugger-security.md)   
 [Paramètres et préparation du débogueur](../debugger/debugger-settings-and-preparation.md)



