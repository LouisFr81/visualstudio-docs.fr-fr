---
title: Guide pratique pour comparer des fichiers de données de performances | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vsperf.choosediffbinaries
helpviewer_keywords:
- profiling tools, how to compare profiler result files
- profiler result files, how to compare
ms.assetid: 1905b45d-c6b3-43c8-87b1-1aee734f37f9
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0574c518342ea24ad2bd3aaf4fd3df9a4ee34a03
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508605"
---
# <a name="how-to-compare-performance-data-files"></a>Guide pratique pour comparer des fichiers de données de performances
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [Comment : comparer des fichiers de données de performances](https://docs.microsoft.com/visualstudio/profiling/how-to-compare-performance-data-files).  
  
Vous pouvez comparer les résultats de deux fichiers de données du profileur (.vsp ou .vsps) en créant un rapport ou une vue de comparaison (« Différences »). Le rapport de comparaison montre les différences, les régressions de performances et les améliorations qui se sont produites d’une session de profilage à l’autre.  
  
 Le rapport Différences présente les données sous forme de tableau. Le tableau présente les données delta, c’est-à-dire ce qui a été modifié par rapport à la base de référence. Ces données sont calculées en déterminant la différence entre l’ancienne valeur, la valeur de base de référence et la valeur résultante de la nouvelle analyse.  
  
 Les comparaisons des données du profileur peuvent être basées sur les fonctions du code, les modules de l’application, les lignes, les pointeurs d’instruction et les types.  
  
 Vous pouvez définir un seuil pour réduire le bruit et exclure de l’affichage les lignes du tableau dont la valeur n’a pas changé de manière significative.  
  
### <a name="to-create-comparison-file-view-for-a-project-in-performance-explorer"></a>Pour créer une vue de comparaison de fichiers pour un projet dans l’Explorateur de performances  
  
1.  Dans l’**Explorateur de performances**, sous **Rapports**, sélectionnez le fichier de rapport .vsp ou .vsps dont vous voulez utiliser les données comme base de référence pour la comparaison.  
  
2.  Sélectionnez les fichiers de rapport .vsp ou .vsps que vous voulez comparer.  
  
3.  Cliquez sur l’un des fichiers sélectionnés, puis cliquez sur **Comparer les rapports**.  
  
### <a name="to-compare-values"></a>Pour comparer des valeurs  
  
1.  Sélectionnez l’onglet **Rapport de comparaison** dans la vue Rapport.  
  
2.  Dans la liste déroulante **Table**, sélectionnez les fonctions ou les modules à comparer.  
  
3.  Dans la liste déroulante **Colonne**, sélectionnez la valeur à comparer.  
  
4.  (facultatif) Tapez une valeur pour **Seuil**.  
  
5.  Cliquez sur **Appliquer**.  
  
### <a name="to-compare-report-files"></a>Pour comparer des fichiers de rapport  
  
1.  Dans le menu **Analyser**, sélectionnez **Comparer les rapports de performances**.  
  
2.  Dans la fenêtre **Sélectionner les fichiers d’analyse à des fins de comparaison**, sélectionnez le fichier d’analyse **Fichier de base** (.vsp ou .vsps) et le **Fichier de comparaison** (.vsp ou .vsps).  
  
3.  Cliquez sur **OK**.


