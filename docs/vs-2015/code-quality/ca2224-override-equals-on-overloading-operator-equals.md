---
title: 'CA2224 : Remplacez equals lors de la surcharge l’opérateur égal | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2224
- OverrideEqualsOnOverloadingOperatorEquals
- OverrideEqualsOnOverridingOperatorEquals
helpviewer_keywords:
- OverrideEqualsOnOverloadingOperatorEquals
- CA2224
ms.assetid: 7312afd9-84ba-417f-923e-7a159b53bf70
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 66f4b4bcc7c2c1d359f5d8fa91227fb51a27adc4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49815232"
---
# <a name="ca2224-override-equals-on-overloading-operator-equals"></a>CA2224 : Remplacez Equals au moment de surcharger l'opérateur égal
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OverrideEqualsOnOverloadingOperatorEquals|
|CheckId|CA2224|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un type public implémente l’opérateur d’égalité, mais ne remplace pas <xref:System.Object.Equals%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Description de la règle
 L’opérateur d’égalité est destinée à être un point de vue syntaxique pour accéder facilement les fonctionnalités de la <xref:System.Object.Equals%2A> (méthode). Si vous implémentez l’opérateur d’égalité, sa logique doit être identique à celle de <xref:System.Object.Equals%2A>.

 Le compilateur c# émet un avertissement si votre code ne respecte pas cette règle.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, vous devez supprimer l’implémentation de l’opérateur d’égalité ou substituer <xref:System.Object.Equals%2A> et avoir les deux méthodes retournent les mêmes valeurs. Si l’opérateur d’égalité n’introduit pas de comportement incohérent, vous pouvez corriger la violation en fournissant une implémentation de <xref:System.Object.Equals%2A> qui appelle le <xref:System.Object.Equals%2A> méthode dans la classe de base.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer un avertissement de cette règle si l’opérateur d’égalité retourne la même valeur que l’implémentation héritée de <xref:System.Object.Equals%2A>. La section exemple inclut un type qui pourrait supprimer sans risque un avertissement de cette règle.

## <a name="examples-of-inconsistent-equality-definitions"></a>Exemples de définitions d’égalité incohérentes

### <a name="description"></a>Description
 L’exemple suivant illustre un type avec des définitions d’égalité incohérentes. `BadPoint` Modifie la signification de l’égalité en fournissant une implémentation personnalisée de l’opérateur d’égalité, mais ne se substitue pas <xref:System.Object.Equals%2A> afin qu’il a un comportement identique.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Usage.OperatorEqualsRequiresEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OperatorEqualsRequiresEquals/cs/FxCop.Usage.OperatorEqualsRequiresEquals.cs#1)]

## <a name="example"></a>Exemple
 Le code suivant teste le comportement de `BadPoint`.

 [!code-csharp[FxCop.Usage.TestOperatorEqualsRequiresEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestOperatorEqualsRequiresEquals/cs/FxCop.Usage.TestOperatorEqualsRequiresEquals.cs#1)]

 Cet exemple produit la sortie suivante.

 **a = ([0] 1,1) et b = ([1] 2,2) sont égaux ? Ne**
**un == b ? Ne**
**a1 et a sont égaux ? Oui**
**a1 == un ? Oui**
**b et b copie sont égales ? Ne**
**b == bcopy ? Oui**
## <a name="example"></a>Exemple
 L’exemple suivant illustre un type qui techniquement enfreint cette règle, mais ne se comporte pas de façon incohérente.

 [!code-csharp[FxCop.Usage.ValueTypeEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ValueTypeEquals/cs/FxCop.Usage.ValueTypeEquals.cs#1)]

## <a name="example"></a>Exemple
 Le code suivant teste le comportement de `GoodPoint`.

 [!code-csharp[FxCop.Usage.TestValueTypeEquals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestValueTypeEquals/cs/FxCop.Usage.TestValueTypeEquals.cs#1)]

 Cet exemple produit la sortie suivante.

 **a = (1,1) et b = (2,2) sont égaux ? Ne**
**un == b ? Ne**
**a1 et a sont égaux ? Oui**
**a1 == un ? Oui**
**b et b copie sont égales ? Oui**
**b == bcopy ? Oui**
## <a name="class-example"></a>Exemple de classe

### <a name="description"></a>Description
 L’exemple suivant montre une classe (type référence) qui enfreint cette règle.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Usage.OverrideEqualsClassViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsClassViolation/cs/FxCop.Usage.OverrideEqualsClassViolation.cs#1)]

## <a name="example"></a>Exemple
 L’exemple suivant résout la violation en substituant <xref:System.Object.Equals%2A?displayProperty=fullName>.

 [!code-csharp[FxCop.Usage.OverrideEqualsClassFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsClassFixed/cs/FxCop.Usage.OverrideEqualsClassFixed.cs#1)]

## <a name="structure-example"></a>Exemple de structure

### <a name="description"></a>Description
 L’exemple suivant montre une structure (type valeur) qui enfreint cette règle.

### <a name="code"></a>Code
 [!code-csharp[FxCop.Usage.OverrideEqualsStructViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsStructViolation/cs/FxCop.Usage.OverrideEqualsStructViolation.cs#1)]

## <a name="example"></a>Exemple
 L’exemple suivant résout la violation en substituant <xref:System.ValueType.Equals%2A?displayProperty=fullName>.

 [!code-csharp[FxCop.Usage.OverrideEqualsStructFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OverrideEqualsStructFixed/cs/FxCop.Usage.OverrideEqualsStructFixed.cs#1)]

## <a name="related-rules"></a>Règles associées
 [CA1046 : Ne pas surcharger l’opérateur égal sur les types de référence](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225 : Les surcharges d’opérateur ont d’autres méthodes nommées](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226 : Les opérateurs doivent avoir des surcharges symétriques](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2218 : Remplacez GetHashCode lors du remplacement de Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231 : Surchargez l’opérateur égal (equals) en remplaçant ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)



