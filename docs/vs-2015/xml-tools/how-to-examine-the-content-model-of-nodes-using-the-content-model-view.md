---
title: 'Comment : examiner le modèle de contenu de nœuds à l’aide de la vue de modèle de contenu | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c42ddac8-b0e3-48d6-9832-112a19d6c104
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca6c86772cc3ad27b537052961afea50fad7b876
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49245945"
---
# <a name="how-to-examine-the-content-model-of-nodes-using-the-content-model-view"></a>Procédure : examiner le modèle de contenu de nœuds à l'aide de la vue de modèle de contenu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Cette rubrique explique comment Explorer vos nœuds à l’aide de la [affichage du modèle de contenu](../xml-tools/content-model-view.md).  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Pour créer un fichier XSD et afficher l'élément racine dans la vue de modèle de contenu  
  
1.  Créez un fichier de schéma XML.  
  
2.  Cliquez sur **utiliser l’éditeur XML pour afficher et modifier le fichier de schéma XML sous-jacent** sur la vue de départ.  
  
3.  Copiez le code d’exemple de schéma XML à partir de [exemple de schéma XML : schéma de bon de commande](../xml-tools/sample-xsd-file-purchase-order-schema.md) et collez-le pour remplacer le code qui a été ajouté au nouveau fichier XSD par défaut.  
  
4.  Sélectionnez le `purchaseOrder` élément dans l’Explorateur de schémas en double-cliquant sur le `purchaseOrder` élément dans l’éditeur XML et en sélectionnant **afficher dans l’Explorateur XML**.  
  
5.  Cliquez sur le `purchaseOrder` dans l’Explorateur de XML et sélectionnez **afficher en vue de modèle de contenu**.  
  
     La vue de modèle de contenu affiche l'élément `purchaseOrder` sur son aire de conception.  
  
6.  Développez les nœuds`shipTo`, `billTo` et `items` en double-cliquant sur chaque nœud ou en cliquant sur la flèche double à droite de chaque nœud.  
  
     Les nœuds de l'élément `purchaseOrder` sont maintenant développés et vous pouvez consulter le modèle de contenu de l'élément.  
  
7.  Cliquez sur n'importe quel nœud sous l'élément `purchaseOrder`, puis examinez la barre de fil d'Ariane (breadcrumb) pour déterminer l'emplacement du nœud sélectionné dans le jeu de schémas.  
  
8.  Cliquez sur le **afficher la Documentation** bouton dans la barre d’outils XSD pour basculer vers la documentation. Vous pouvez également cliquer avec le bouton droit sur l'aire de conception pour basculer vers la documentation.  
  
9. Cliquez le `purchaseOrder` nœud et sélectionnez **générer un exemple de code XML** pour voir le document d’instance XML.



