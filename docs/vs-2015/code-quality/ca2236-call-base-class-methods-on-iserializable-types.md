---
title: 'CA2236 : Appelez les méthodes de classe de base sur les types ISerializable | Microsoft Docs'
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
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: bcde222020ca18b918ad694abe42c2c76a4a613c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49886680"
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236 : Appelez les méthodes de la classe de base sur les types ISerializable
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un type dérive d’un type qui implémente le <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> interface et une des conditions suivantes est vraie :

-   Le type implémente le constructeur de sérialisation, autrement dit, un constructeur avec le <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> signature de paramètre, mais n’appelle ne pas le constructeur de sérialisation du type de base.

-   Le type implémente le <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> méthode mais n’appelle pas la <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> méthode du type de base.

## <a name="rule-description"></a>Description de la règle
 Dans un processus de sérialisation personnalisé, un type implémente le <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> méthode pour sérialiser ses champs et le constructeur de sérialisation pour désérialiser les champs. Si le type dérive d’un type qui implémente le <xref:System.Runtime.Serialization.ISerializable> interface, le type de base <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> constructeur de sérialisation et de la méthode doit être appelé pour sérialiser/désérialiser les champs du type de base. Sinon, le type ne sera pas sérialisé et désérialisé correctement. Notez que si le type dérivé n’ajoute pas tous les nouveaux champs, le type n’a pas besoin d’implémenter le <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> méthode, ni le constructeur de sérialisation ou d’appeler les équivalents de type de base.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, appelez le type de base <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> constructeur de sérialisation ou de la méthode à partir de le correspondantes dérivée de méthode de type ou le constructeur.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant montre un type dérivé qui satisfait la règle en appelant le constructeur de sérialisation et <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> méthode de la classe de base.

 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallBaseISerializable/cs/FxCop.Usage.CallBaseISerializable.cs#1)]
 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallBaseISerializable/vb/FxCop.Usage.CallBaseISerializable.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA2240 : Implémentez ISerializable correctement](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229 : Implémentez des constructeurs de sérialisation](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238 : Implémentez les méthodes de sérialisation correctement](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235 : Marquez tous les champs non sérialisables](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237 : Marquez les types ISerializable avec SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239 : Spécifiez des méthodes de désérialisation pour les champs facultatifs](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120 : Sécurisez les constructeurs de sérialisation](../code-quality/ca2120-secure-serialization-constructors.md)



