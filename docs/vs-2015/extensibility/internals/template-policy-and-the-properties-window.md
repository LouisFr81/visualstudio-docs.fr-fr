---
title: Stratégie de modèle et de la fenêtre Propriétés | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 695b65d65d03717dd2c2579584d61227ecf447cb
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51767325"
---
# <a name="template-policy-and-the-properties-window"></a>Stratégie de modèle et fenêtre Propriétés
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Lorsqu’un projet est contenu à l’intérieur d’un projet de modèle d’entreprise, ce projet de modèle d’entreprise peut appliquer la stratégie. Stratégie de modèle devienne un système de contrainte qui peut être utilisé pour définir les valeurs par défaut pour les propriétés, masquer les propriétés, ajouter des propriétés et ainsi de suite.  
  
 À l’aide de la stratégie de modèle pour contrôler l’affichage des informations dans le **propriétés** fenêtre est différente de l’implémentation <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> gère les propriétés de l’objet au niveau du composant, tandis que la stratégie de modèle peut être utilisée pour limiter les propriétés de l’objet au niveau de la solution ou le projet. En d’autres termes  
  
- Implémenter les méthodes sur <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> pour déterminer ce qui est affiché dans le **propriétés** fenêtre pour des objets spécifiques  
  
- Utiliser la stratégie du modèle au niveau du projet et solution pour déterminer ce qui est affiché dans le **propriétés** fenêtre pour des objets précédemment spécifiées  
  
  À l’aide de la stratégie de modèle pour limiter de façon sélective des propriétés spécifiques dans le **propriétés** fenêtre lorsqu’un élément de projet d’un type spécifié est sélectionné dans **l’Explorateur de solutions** peut être utile pour tous les membres de l’équipe de développement travaille sur un projet. Par exemple, à l’aide de la stratégie de modèle, vous pouvez configurer toutes les informations de chaîne de connexion dans une base de données pour vos développeurs et que la chaîne de connexion en lecture seule. De cette façon, vous pouvez fournir un moyen simple de garantir que chaque développeur utilise le chemin d’accès correct pour accéder aux données.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [Extension des propriétés](../../extensibility/internals/extending-properties.md)

