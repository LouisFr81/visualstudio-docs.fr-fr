---
title: 'CA1819 : Les propriétés ne doivent pas retourner des tableaux'
ms.date: 09/28/2018
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: af31c925420602329eb20b803c92879210518ebd
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55919207"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819 : Les propriétés ne doivent pas retourner des tableaux

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|Category|Microsoft.Performance|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause

Une propriété publique ou protégée dans un type public retourne un tableau.

## <a name="rule-description"></a>Description de la règle

Les tableaux retournés par les propriétés ne sont pas protégés en écriture, même si la propriété est en lecture seule. Pour protéger le tableau de toute falsification, la propriété doit retourner une copie du tableau. En règle générale, les utilisateurs ne comprennent les implications de performances négatif de l’appel d’une telle propriété. Plus précisément, ils peuvent utiliser la propriété comme une propriété indexée.

## <a name="how-to-fix-violations"></a>Comment corriger les violations

Pour corriger une violation de cette règle, modifiez la propriété une méthode ou modifier la propriété pour retourner une collection.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements

Vous pouvez supprimer un avertissement est déclenché pour une propriété d’un attribut qui est dérivé de la <xref:System.Attribute> classe. Les attributs peuvent contenir des propriétés qui retournent des tableaux, mais ne peut pas contenir des propriétés qui retournent des collections.

Vous pouvez supprimer l’avertissement si la propriété fait partie d’un [objet de transfert de données (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) classe.

Sinon, ne supprimez aucun avertissement de cette règle.

## <a name="example-violation"></a>Exemple de violation

L’exemple suivant illustre une propriété qui enfreint cette règle :

[!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
[!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

Pour corriger une violation de cette règle, modifiez la propriété une méthode ou modifier la propriété pour retourner une collection plutôt qu’un tableau.

### <a name="change-the-property-to-a-method"></a>Modifiez la propriété à une méthode

L’exemple suivant résout la violation en modifiant la propriété à une méthode :

[!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
[!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

### <a name="change-the-property-to-return-a-collection"></a>Modifiez la propriété pour retourner une collection

L’exemple suivant résout la violation en modifiant la propriété à retourner un <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>:

[!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
[!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allow-users-to-modify-a-property"></a>Permettre aux utilisateurs de modifier une propriété

Vous souhaiterez peut-être permettre au consommateur de la classe modifier une propriété. L’exemple suivant montre une propriété en lecture/écriture qui enfreint cette règle :

[!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
[!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

L’exemple suivant résout la violation en modifiant la propriété à retourner un <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>:

[!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
[!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>Règles associées

- [CA1024 : Utiliser des propriétés lorsque nécessaire](../code-quality/ca1024-use-properties-where-appropriate.md)