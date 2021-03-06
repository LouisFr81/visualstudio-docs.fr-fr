---
title: Propagation des modifications et réponse aux | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, events
ms.assetid: fc2e9ac5-7a84-44ed-9945-94e45f89c227
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 32deaa75ed09ad1a1320ec72d95d75adc92c12b2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49280382"
---
# <a name="responding-to-and-propagating-changes"></a>Propagation et réponse aux modifications en attente
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lorsqu’un élément est créé, supprimé ou mis à jour, vous pouvez écrire du code qui propage la modification aux autres parties du modèle, ou à des ressources externes telles que des fichiers, de bases de données ou d’autres composants.  
  
## <a name="in-this-section"></a>Dans cette section  
 En règle générale, prenez en compte ces techniques dans l’ordre suivant :  
  
|Technique|Scénarios|Pour plus d'informations|  
|---------------|---------------|--------------------------|  
|Définir une propriété de domaine calculée.|Une propriété de domaine dont la valeur est calculée à partir d’autres propriétés dans le modèle. Par exemple, un prix qui est la somme des prix des éléments connexes.|[Propriétés de stockage calculées et personnalisées](../modeling/calculated-and-custom-storage-properties.md)|  
|Définir une propriété de domaine personnalisé stockage.|Une propriété de domaine stockée dans d’autres parties du modèle ou en externe. Par exemple, vous pourrez analyser une chaîne d’expression dans une arborescence dans le modèle.|[Propriétés de stockage calculées et personnalisées](../modeling/calculated-and-custom-storage-properties.md)|  
|Substituer des gestionnaires de modification telles que OnValueChanging et OnDeleting|Synchroniser les différents éléments et synchroniser les valeurs externes avec le modèle.<br /><br /> Limiter les valeurs pour les plages définies.<br /><br /> Appelé juste avant et après la valeur de propriété et d’autres modifications. Vous pouvez mettre fin à la modification en levant une exception.|[Gestionnaires de modification de la valeur de propriété du domaine](../modeling/domain-property-value-change-handlers.md)|  
|Règles|Vous pouvez définir des règles qui sont en file d’attente pour l’exécution juste avant la fin d’une transaction dans laquelle une modification s’est produit. Ils ne sont pas exécutés sur l’annulation ou de rétablissement. Utilisez-les pour qu’une partie du magasin reste synchronisé avec un autre.|[Propagation de modifications dans le modèle par des règles](../modeling/rules-propagate-changes-within-the-model.md)|  
|Événements de Store|Le magasin de modélisation fournit des notifications d’événements tels que l’ajout ou la suppression d’un élément ou un lien ou la modification de la valeur d’une propriété. L’événement est également exécutée sur Annuler et rétablir. Utiliser des événements de stockage pour mettre à jour les valeurs qui ne sont pas dans le magasin.|[Propagation de modifications en dehors du modèle par des gestionnaires d’événements](../modeling/event-handlers-propagate-changes-outside-the-model.md)|  
|Événements .NET|Les formes ont des gestionnaires d’événements qui répondent aux clics de souris et d’autres manipulations. Vous devez inscrire ces événements pour chaque objet. L’inscription s’effectue généralement dans une substitution de InitializeInstanceResources et doit être effectuée pour chaque élément.<br /><br /> Ces événements se produisent généralement en dehors d’une transaction.|[Guide pratique pour intercepter un événement de clic sur une forme ou un décorateur](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)|  
|Règles de limites|Une règle de limites est utilisée spécifiquement pour contraindre les limites d’une forme.|[Emplacement et de la taille de la forme contrainte par BoundsRules](../modeling/boundsrules-constrain-shape-location-and-size.md)|  
|Règles de sélection|Règles de sélection restreindre ce que l’utilisateur peut sélectionner.|[Guide pratique pour accéder à et contraindre la sélection actuelle](../modeling/how-to-access-and-constrain-the-current-selection.md)|  
|OnAssocatedPropertyChanged|Indiquer les États des éléments de modèle à l’aide des fonctionnalités de formes et connecteurs tels que les clichés instantanés, pointes de flèche, couleur et les largeurs de ligne et le style.|[Mise à jour des formes et des connecteurs pour refléter le modèle](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md)|  
  
## <a name="comparing-rules-and-store-events"></a>**Comparaison des règles et des événements de Store**  
 Utilitaires de notification de modification, les règles et les événements sont exécutés lorsque des modifications se produisent dans un modèle.  
  
 Les règles sont généralement appliquées à la transaction finale dans lequel la modification s’est produite, et les événements sont appliqués après que les modifications dans une transaction sont validées.  
  
 Événements de stockage permet de synchroniser le modèle avec des objets en dehors de Store, les règles de maintenir la cohérence dans le Store.  
  
-   **Création de règles personnalisées** vous créez une règle personnalisée comme une classe dérivée à partir d’une règle abstraite. Vous devez également informer l’infrastructure sur la règle personnalisée. Pour plus d’informations, consultez [propager les modifications dans le modèle de règles](../modeling/rules-propagate-changes-within-the-model.md).  
  
-   **S’abonner aux événements** avant de vous abonner à un événement, créez un gestionnaire d’événements et le délégué. Utilisez ensuite le <xref:Microsoft.VisualStudio.Modeling.Store.EventManagerDirectory%2A>propriété pour vous abonner à l’événement. Pour plus d’informations, consultez [gestionnaires propager les modifications en dehors le modèle d’événement](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
-   **Annulation des modifications** lorsque vous annulez une transaction, les événements sont déclenchés, mais les règles ne sont pas appliquées. Si une règle modifie une valeur, vous annulez la modification, la valeur est réinitialisée à la valeur d’origine pendant l’opération d’annulation. Lorsqu’un événement est déclenché, vous devez modifier manuellement la valeur à sa valeur d’origine. Pour en savoir plus sur transactons et d’annulation, consultez [Comment : utiliser les Transactions pour mettre à jour le modèle](../modeling/how-to-use-transactions-to-update-the-model.md).  
  
-   **Passage des Arguments d’événement à des règles et des événements** les deux événements et règles sont transmis un `EventArgs` paramètre qui contient des informations sur la façon le modèle modifié.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : intercepter un événement Click sur une forme ou un décorateur](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)   
 [Écriture de code pour personnaliser un langage spécifique à un domaine](../modeling/writing-code-to-customise-a-domain-specific-language.md)



