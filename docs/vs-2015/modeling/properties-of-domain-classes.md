---
title: Propriétés des Classes de domaine | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain class
ms.assetid: a3993995-19e7-4761-a972-b1de89131a1b
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: f9f84290ca8155cb2cf2b48a5d9b3f5f68c7ce9a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49172625"
---
# <a name="properties-of-domain-classes"></a>Propriétés des classes de domaine
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Classes de domaine ont les propriétés dans le tableau suivant. Pour plus d’informations sur les classes de domaine, consultez [présentation des modèles, des Classes et des relations](../modeling/understanding-models-classes-and-relationships.md). Pour plus d’informations sur l’utilisation de ces propriétés, consultez [personnalisation et extension d’un langage spécifique à un domaine](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Propriété|Description|Par défaut|  
|--------------|-----------------|-------------|  
|Modificateur d'accès|Niveau d'accès de la classe de domaine (`public` ou `internal`).|`public`|  
|Attributs personnalisés|Utilisé pour ajouter des attributs à la classe de code source qui est générée à partir de cette classe de domaine.|\<Aucun >|  
|Génère le Double dérivée|Si `True`, une classe de base et une classe partielle (pour prendre en charge la personnalisation via des substitutions) sont générés. Pour plus d’informations, consultez [substitution et extension des Classes générées](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|A le constructeur personnalisé|Si `True`, un constructeur personnalisé est fourni dans le code source. Pour plus d’informations, consultez [substitution et extension des Classes générées](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Modificateur d’héritage|Décrit le type d’héritage de la classe de code source qui est générée à partir de la classe de domaine (`none`, `abstract` ou `sealed`).|`none`|  
|Classe de base|Si cette classe de domaine est dérivée, le nom de la classe de base.|\<Aucun >|  
|Name|Le nom de cette classe de domaine.|Nom actuel|  
|Espace de noms|L’espace de noms de cette classe de domaine.|Espace de noms actuel|  
|Notes|Remarques informelles associées à cette classe de domaine.|\<Aucun >|  
|Description|La description est utilisée pour documenter l’interface utilisateur du concepteur généré.|\<Aucun >|  
|Nom complet|Le nom qui s’affichera dans le concepteur généré pour cette classe de domaine.|\<Aucun >|  
|Help Keyword|Le mot clé facultatif qui est utilisé pour indexer l’aide F1 pour cette classe de domaine.|\<Aucun >|  
  
## <a name="see-also"></a>Voir aussi  
 [Glossaire des outils Domain-Specific Language](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



