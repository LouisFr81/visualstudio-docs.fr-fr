---
title: Ajout d’Extensions à des définitions DSL | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07e133be-92ab-4936-a02b-45d2012bd0a6
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 9c3e74f66edc0a8b33ad1fe8205cc02cd0e80054
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49866153"
---
# <a name="adding-extensions-to-dsl-definitions"></a>Ajout d'extensions à des définitions DSL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Extension de définition DSL vous permet de créer un package d’extensions à un langage spécifique à un domaine (DSL). L’extension DSL, qui est contenue dans une Extension d’intégration Visual Studio (VSIX), peut être installée sur l’ordinateur d’un utilisateur dans la même manière qu’une solution DSL. Les fonctionnalités supplémentaires peuvent être dynamiquement activées et désactivées au moment de l’exécution. DSL n’ont pas à être explicitement conçu pour l’extension, et extensions peuvent être conçues par des tiers ou ultérieurement sans en altérer le DSL étendue.  
  
 Les fonctionnalités supplémentaires peuvent être les suivants :  
  
- Propriétés des éléments de modèle et de présentation  
  
- Éléments décoratifs pour les formes et connecteurs  
  
- Classes, les relations, formes et connecteurs  
  
- Contraintes de validation  
  
- Onglets et des éléments de boîte à outils  
  
  Un utilisateur d’un langage DSL étendu peut créer et enregistrer un modèle qui contient les instances des fonctionnalités supplémentaires, et ils peuvent être lus par d’autres utilisateurs qui ont installé l’extension appropriée. Les utilisateurs qui n’ont pas installé l’extension ne peut pas utiliser les fonctionnalités supplémentaires, mais ils peuvent mettre à jour et enregistrer un modèle sans perdre les fonctionnalités supplémentaires.  
  
  Pour plus d’exemples de code et plus d’informations sur cette fonctionnalité, consultez le [Visual Studio Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=186128) site Web.  
  
## <a name="see-also"></a>Voir aussi  
 [Visual Studio Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=186128)



