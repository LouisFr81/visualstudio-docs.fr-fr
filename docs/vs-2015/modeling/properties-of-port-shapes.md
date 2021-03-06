---
title: Propriétés des formes de Port | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.port
helpviewer_keywords:
- Domain-Specific Language, port shape
ms.assetid: 9d69c4c1-4f72-4876-96b6-9b846e0495a4
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: dcb6ad091d0b65e5b368f5822659a909e9f4c42a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49290704"
---
# <a name="properties-of-port-shapes"></a>Propriétés des formes de port
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser des formes de port pour représenter des classes de domaine dans le concepteur généré.  
  
 Pour plus d’informations, consultez [comment définir un langage spécifique à un domaine](../modeling/how-to-define-a-domain-specific-language.md). Pour plus d’informations sur l’utilisation de ces propriétés, consultez [personnalisation et extension d’un langage spécifique à un domaine](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Formes port ont les propriétés qui sont répertoriées dans le tableau suivant.  
  
|Propriété|Description|Par défaut|  
|--------------|-----------------|-------------|  
|Couleur de remplissage|La couleur de remplissage de cette forme.|Blanc|  
|Mode de remplissage dégradé|Le mode de remplissage dégradé de cette forme.|Horizontal|  
|géométrie|La géométrie de cette forme (Rectangle, Rectangle arrondi, Ellipse ou le cercle).|Rectangle|  
|A des Points de connexion par défaut|Si `True`, la forme utilisera haut, bas, gauche et droit connexion pointe dans le concepteur généré.|False|  
|Couleur du contour|La couleur de contour de cette forme.|Noir|  
|Style de tiret de contour|Le style de tiret de contour de cette forme (solide, tiret, point, tiret, DashDotDot ou personnalisé).|Unie|  
|Épaisseur du contour|L’épaisseur du contour de cette forme.|0.03125|  
|Couleur du texte|La couleur qui est utilisée pour les éléments décoratifs de texte qui sont associés à cette forme.|Noir|  
|Modificateur d'accès|Le niveau d’accès de la classe (`public` ou `internal`).|Public|  
|Attributs personnalisés|Utilisé pour ajouter des attributs à la classe de code source qui est générée à partir de cette forme.|\<Aucun >|  
|Génère le Double dérivée|Si `True`, une classe de base et une classe partielle (pour prendre en charge la personnalisation via des substitutions) sont générés. Pour plus d’informations, consultez [substitution et extension des Classes générées](../modeling/overriding-and-extending-the-generated-classes.md)|False|  
|A le constructeur personnalisé|Si `True`, un constructeur personnalisé est fourni dans le code source. Pour plus d’informations, consultez [substitution et extension des Classes générées](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Modificateur d’héritage|Décrit le type d’héritage de la classe de code source qui est générée à partir du port (`none`, `abstract` ou `sealed`).|none|  
|Port de base|La classe de base de cette forme.|(aucune)|  
|Name|Le nom de cette forme.|Nom actuel|  
|Espace de noms|L’espace de noms qui est affilié à cette forme.|Espace de noms actuel|  
|Type d’outil de Conseil|Comment l’info-bulle est définie (fixe, variable, ou aucun). Si fixe, puis la valeur de la `Fixed Tooltip Text` propriété est utilisée en tant que l’info-bulle ; si la variable, l’info-bulle est définie dans du code personnalisé.|none|  
|Notes|Remarques informelles associées à cette forme.|\<Aucun >|  
|Hauteur initiale|La hauteur initiale de cette forme, en pouces.|1|  
|Largeur initiale|Largeur initiale de cette forme, en pouces.|1,5|  
|Couleur de remplissage exposé en tant que propriété<br /><br /> Mode de remplissage exposé dégradé<br /><br /> Exposé de couleur du contour en tant que propriété<br /><br /> Exposé de Style de tiret de contour en tant que propriété<br /><br /> Épaisseur du contour en tant que propriété d’exposées<br /><br /> Expose la couleur du texte|Si `True`, l’utilisateur peut définir la propriété indiquée d’une forme. Pour définir ceci, avec le bouton droit de la définition de forme, puis cliquez sur **ajouter les objets exposés**.|False|  
|Description|Utilisé pour documenter le concepteur généré.|\<Aucun >|  
|Nom complet|Le nom qui s’affichera dans le concepteur généré pour cette forme.|\<Aucun >|  
|Texte fixe d’info-bulle|Le texte qui est utilisé pour une info-bulle fixe.|\<Aucun >|  
|Help Keyword|Le mot clé qui est utilisé pour indexer l’aide F1 pour cette forme.|\<Aucun >|  
  
## <a name="see-also"></a>Voir aussi  
 [Glossaire des outils Domain-Specific Language](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



