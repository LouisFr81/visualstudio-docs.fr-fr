---
title: 'Comment : obtenir une vue d’ensemble d’un jeu de schémas à l’aide de la vue du graphique | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3722af4aef2f56d6da1c2a79840c05edd2a87b65
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49181361"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Procédure : obtenir une vue d'ensemble d'un jeu de schémas à l'aide de la vue du graphique
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Cette rubrique explique comment utiliser le [vue du graphique](../xml-tools/graph-view.md) pour afficher une vue d’ensemble des nœuds dans un jeu de schémas et les relations entre les nœuds.  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Pour créer un fichier XSD et afficher l'élément racine dans la vue de modèle de contenu  
  
1.  Créez un fichier de schéma XML et enregistrez le fichier sous Relationships.xsd.  
  
2.  Cliquez sur le **utiliser l’éditeur XML pour afficher et modifier le fichier de schéma XML sous-jacent** lien sur la vue de départ.  
  
3.  Copiez le code d’exemple de schéma XML à partir de [exemple de schéma XML : relations](../xml-tools/sample-xsd-file-relationships.md) et collez-le pour remplacer le code qui a été ajouté au nouveau fichier XSD par défaut.  
  
4.  Cliquez n’importe où dans l’éditeur XML et sélectionnez **Concepteur de vues**.  
  
5.  Sélectionnez la vue du graphique dans la barre d'outils XSD.  
  
6.  Sélectionnez **jeu de schémas** nœud dans l’Explorateur de schémas XML et faites glisser le nœud de la vue du graphique sur l’aire de conception. Tous les nœuds globaux doivent apparaître, ainsi que les flèches connectant les nœuds qui ont des relations.  
  
     ![Vue graphique](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")  
  
7.  Cliquez sur n'importe quel nœud sur l'aire de conception, puis examinez la barre de fil d'Ariane (breadcrumb) pour déterminer l'emplacement du nœud sélectionné dans le jeu de schémas.  
  
8.  Cliquez sur n’importe quel nœud d’élément sur l’avec aire de conception et sélectionnez **générer un exemple de code XML** pour voir le document d’instance XML.



