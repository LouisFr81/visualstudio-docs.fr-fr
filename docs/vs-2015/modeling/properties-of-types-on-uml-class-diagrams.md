---
title: Propriétés de types UML sur les diagrammes de classes | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.logicalclassdiagram.shapes.properties
helpviewer_keywords:
- UML, element properties
ms.assetid: 6e1ef2d0-d67a-401a-bd64-d5e034decd2c
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e8baad41658cc6144f08d0b6b4d415aa4ff6e499
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51750115"
---
# <a name="properties-of-types-on-uml-class-diagrams"></a>Propriétés de types dans des diagrammes de classes UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans un diagramme de classes UML, un *type* est une classe, une interface ou une énumération.  
  
> [!NOTE]
>  Cette rubrique traite des propriétés de types dans les diagrammes de classes UML Pour plus d’informations, consultez les rubriques suivantes :  
  
-   [Informations de référence sur les diagrammes de classes UML](../modeling/uml-class-diagrams-reference.md)  
  
-   [Diagrammes de classes UML : recommandations](../modeling/uml-class-diagrams-guidelines.md)  
  
-   [Propriétés d’attributs dans des diagrammes de classes UML](../modeling/properties-of-attributes-on-uml-class-diagrams.md)  
  
-   [Propriétés d’opérations dans des diagrammes de classes UML](../modeling/properties-of-operations-on-uml-class-diagrams.md)  
  
-   [Propriétés des associations dans les diagrammes de classes UML](../modeling/properties-of-associations-on-uml-class-diagrams.md)  
  
## <a name="properties"></a>Properties  
 Il s'agit des propriétés d'une classe, interface ou énumération.  
  
 Pour afficher les propriétés d’un type, cliquez sur le type dans le diagramme ou dans **Explorateur de modèles UML**, puis cliquez sur **propriétés**. Les propriétés s’affichent dans le **propriétés** fenêtre.  
  
|**Property**|**Default**|Apparaît dans|Description|  
|------------------|-----------------|----------------|-----------------|  
|**Name**|Nom par défaut|Tous les éléments|Identifie l'élément.|  
|**Nom qualifié**|Package conteneur :: Nom du type|Tous les éléments|Identifie l'élément de manière unique. A pour préfixe le nom qualifié du package qui le contient.|  
|**Couleur**|Par défaut pour le genre de type|Tous les éléments|Couleur de cette forme. Contrairement aux autres propriétés, il ne s'agit pas d'une propriété de l'élément de modèle sous-jacent. Différentes vues du même type peuvent avoir différentes couleurs.|  
|**Est abstrait**|False|Classe|Si la valeur est true, la classe ne peut pas être instanciée et est destinée à être utilisée comme classe de base.|  
|**Est une feuille**|False|Classe, Interface|Si la valeur est true, le type n'est pas destiné à avoir des types dérivés.|  
|**Est actif**|False|Classe|Si la valeur est true, chaque instance de ce type est associée à un thread de contrôle.|  
|**Visibilité**|Public|Classe, Interface, Énumération|-Public - visible globalement.<br />-Private : ce type est visible dans le package auquel il appartient.<br />-Package - visible dans le package.|  
|**Éléments de travail**|{0} associé|Tous les éléments|Nombre d'éléments de travail associés à cet élément. Pour associer des éléments de travail, consultez [lier des éléments de modèle et des éléments de travail](../modeling/link-model-elements-and-work-items.md).|  
|**Description**|(vide)|Tous les éléments|Vous pouvez consigner des remarques générales concernant l'élément.|  
|**Liaison de modèle**|(aucune)|Classe, Interface, Énumération|Si la valeur n'est pas vide, ce type est défini en liant des valeurs de paramètres à cette classe de modèle. Développez la propriété pour afficher les liaisons des paramètres du modèle.|  
|**Paramètres de modèle**|(aucune)|Classe, Interface, Énumération|Si la valeur n'est pas vide, il s'agit d'une classe de modèle qui a les paramètres répertoriés ici. Pour ajouter des paramètres ou afficher les propriétés de paramètres individuels, cliquez sur **[...]** .|  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés d’attributs dans des diagrammes de classes UML](../modeling/properties-of-attributes-on-uml-class-diagrams.md)   
 [Propriétés d’opérations sur les diagrammes de classes UML](../modeling/properties-of-operations-on-uml-class-diagrams.md)   
 [Propriétés des associations dans des diagrammes de classes UML](../modeling/properties-of-associations-on-uml-class-diagrams.md)   
 [Diagrammes de classes UML : recommandations](../modeling/uml-class-diagrams-guidelines.md)



