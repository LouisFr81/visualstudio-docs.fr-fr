---
title: Vue Résumé | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.summary
helpviewer_keywords:
- performance reports, summary view
- profiling tools reports, Summary view
- profiling tools, Summary view
- Summary view
ms.assetid: 98a1eb71-bbf5-4ce7-8559-cdc29f082c4b
caps.latest.revision: 42
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bfba1981fb6becea34fb567a2f7ae2e6c06896d2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767855"
---
# <a name="summary-view"></a>Vue Résumé
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La vue Résumé affiche des informations sur les fonctions ou les objets dont le coût est le plus pénalisant quant aux performances lors d’une exécution du profilage. Cette vue fournit un graphique chronologique et plusieurs listes de fonctions ou d’objets dont le coût est le plus pénalisant quant aux métriques de performances de la méthode de profilage. Les données de cette vue dépendent de la méthode de profilage qui a été utilisée (échantillonnage, instrumentation ou concurrence) et de l’allocation de mémoire .NET si elle a été collectée ou non.  
  
 Dans toutes les vues Résumé, à l’exception de la vue Résumé des données de concurrence, le graphique chronologique de la vue Résumé montre le pourcentage d’utilisation de l’UC de l’application profilée pendant la durée du profilage.  
  
-   Si vous spécifiez un segment de temps sur le graphique, vous pouvez réanalyser les données pour ce segment ou effectuer un zoom de l’affichage de la chronologie sur le segment que vous avez spécifié. Pour plus d’informations, consultez [Guide pratique pour filtrer les vues de rapport à partir de la chronologie Résumé](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
-   Vous pouvez cliquer sur une fonction de la liste de la vue Résumé pour afficher la vue Détails de la fonction. Vous pouvez également cliquer avec le bouton droit sur la fonction pour d’autres options d’affichage.  
  
-   Pour modifier le nombre d’éléments qui apparaissent dans les listes de la vue Résumé, ouvrez le menu **Outils**, pointez sur **Options**, puis cliquez sur **Outils d’analyse des performances**. Sous **Paramètres généraux**, modifiez le paramètre **Nombre de fonctions en mode Résumé**.  
  
## <a name="notifications-links"></a>Liens Notifications  
 Vous pouvez cliquer sur les liens dans la liste Notification pour définir les options d’affichage pour le rapport. La liste est à droite du graphique chronologique.  
  
|||  
|-|-|  
|**Afficher le code autre que le code utilisateur**<br /><br /> **Afficher Uniquement mon code**|Non disponible pour le code natif ou pour les données de profilage qui ont été collectées avec la méthode d’instrumentation. Bascule entre l’affichage des données du code utilisateur uniquement (**Afficher Uniquement mon code**) et l’affichage des données de tout le code, notamment le code système (**Afficher le code autre que le code utilisateur**). Par défaut, les données sont limitées au code utilisateur. Pour changer le paramètre, consultez [Guide pratique pour filtrer les vues de rapport des outils de profilage de façon à afficher Uniquement mon code](../profiling/how-to-filter-profiling-tools-report-views-to-display-just-my-code.md).|  
|**Afficher l’aide**|Affiche les avertissements des règles de performance dans la fenêtre **Liste d’erreurs**. Pour plus d’informations, consultez [Utilisation des règles de performance pour analyser des données](../profiling/using-performance-rules-to-analyze-data.md)|  
  
## <a name="report"></a>Rapport  
 Vous pouvez cliquer sur les liens dans la liste Rapport pour ouvrir différentes vues et pour comparer, enregistrer ou filtrer le rapport. La liste est à droite du graphique chronologique.  
  
|||  
|-|-|  
|**Afficher une arborescence des appels tronquée**|Affiche les chemins d’exécution les plus consommateurs dans la vue Arborescence des appels. Pour plus d’informations, consultez [Arborescence des appels, vue](../profiling/call-tree-view.md).|  
|**Afficher les hotlines**|Non disponible pour les données de profilage qui ont été collectées avec la méthode d’instrumentation. Affiche les lignes de code source les plus consommatrices dans la vue Lignes. Pour plus d’informations, consultez [Lignes, vue](../profiling/lines-view.md).|  
|**Comparer des rapports**|Affiche la boîte de dialogue **Sélectionner des fichiers d’analyse à comparer**, où vous pouvez spécifier un autre fichier de données de profilage à comparer au fichier actif. Pour plus d’informations, consultez [Comparaison des fichiers de données de performances](../profiling/comparing-performance-data-files.md).|  
|**Exporter les données du rapport**|Affiche la boîte de dialogue **Exporter le rapport**, où vous pouvez spécifier une ou plusieurs vues de rapport à enregistrer comme fichiers .csv (valeurs séparées par des virgules) ou .xml. Pour plus d’informations, consultez [Guide pratique pour exporter les rapports des outils de profilage](http://msdn.microsoft.com/174b5bd3-df9b-4fd4-88d4-76032ab90451).|  
|**Enregistrer le rapport analysé**|Enregistre le fichier de données de profilage actif dans un fichier .vsps, qui s’ouvre plus rapidement dans l’interface pour [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Pour plus d’informations, consultez [Guide pratique pour enregistrer des fichiers de données de profilage analysés](http://msdn.microsoft.com/0340ddde-caf4-48ac-8af3-d15dcdade556).|  
|**Filtrer les données du rapport**|Affiche le volet de filtrage du rapport de profilage où vous pouvez spécifier des critères pour limiter les données de la vue Rapport. Pour plus d’informations, consultez [Filtre de la vue Rapport de performances](../profiling/performance-report-view-filter.md).|  
|**Plein écran**|Active ou désactive le mode Plein écran pour la vue Rapport.|  
  
## <a name="see-also"></a>Voir aussi  
 [Mode Résumé](../profiling/summary-view-sampling-data.md)   
 [Mode Résumé](../profiling/summary-view-instrumentation-data.md)   
 [Mode Résumé](../profiling/summary-view-dotnet-memory-data.md)
