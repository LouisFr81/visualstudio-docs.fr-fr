---
title: 'CA2117 : Les types APTCA doivent uniquement étendre des types de base APTCA | Microsoft Docs'
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
- CA2117
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
helpviewer_keywords:
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
- CA2117
ms.assetid: c505b586-2f1e-47cb-98ee-a5afcbeda70f
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4b069674827ab266b4a4b7a99f81e039d487f6da
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49922644"
---
# <a name="ca2117-aptca-types-should-only-extend-aptca-base-types"></a>CA2117 : Les types APTCA doivent uniquement étendre des types de base APTCA
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AptcaTypesShouldOnlyExtendAptcaBaseTypes|
|CheckId|CA2117|
|Category|Microsoft.Security|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type public ou protégé dans un assembly avec le <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> attribut hérite d’un type déclaré dans un assembly qui n’a pas l’attribut.

## <a name="rule-description"></a>Description de la règle
 Par défaut, les types publics ou protégés dans les assemblys avec noms forts sont implicitement protégés par un [demandes d’héritage](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9) pour la confiance totale. Assemblys avec nom fort est marqué avec le <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribut (APTCA) n’ont pas cette protection. L’attribut désactive la demande d’héritage. Cela rend les types exposés déclarés dans l’assembly pouvant être héritées par les types qui n’ont pas de confiance totale.

 Lorsque l’attribut APTCA est présent sur un assembly entièrement fiable, et un type dans l’assembly hérite d’un type qui n’autorise pas les appelants partiellement approuvés, une faille de sécurité est possible. Si deux types `T1` et `T2` remplir les conditions suivantes, des appelants malveillants peuvent utiliser le type `T1` pour contourner la demande de l’héritage de confiance totale implicite qui protège `T2`:

- `T1` un type public est déclaré dans un assembly entièrement fiable qui possède l’attribut APTCA.

- `T1` hérite d’un type `T2` hors de son assembly.

- `T2`d’assembly n’a pas l’attribut APTCA et, doit donc pas être héritée par les types dans les assemblys de confiance partiel.

  Un type de niveau de confiance partiel `X` peut hériter de `T1`, ce qui lui donne accès aux membres hérités déclarés dans `T2`. Étant donné que `T2` n’a pas l’attribut APTCA, son type dérivé immédiat (`T1`) doit satisfaire une demande d’héritage pour une confiance totale ; `T1` dispose d’une confiance totale et par conséquent satisfait cette vérification. Le risque de sécurité est car `X` ne participe pas à satisfaire la demande d’héritage qui protège `T2` à partir de sous-classement non approuvé. Pour cette raison, les types avec l’attribut APTCA ne doivent pas étendre les types qui n’ont pas l’attribut.

  Un autre problème de sécurité et peut-être un plus courant, qui est le type dérivé (`T1`) peut, par le biais des erreurs de programmation, exposer des membres protégés du type qui requiert une confiance totale (`T2`). Lorsque cela se produit, les appelants non approuvés ont accès aux informations qui doivent être disponibles uniquement aux types de niveau de confiance suffisant.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Si le type indiqué par la violation est dans un assembly qui ne nécessite pas l’attribut APTCA, supprimez-le.

 Si l’attribut APTCA est requis, ajoutez une demande d’héritage pour une confiance totale pour le type. Cela protège contre l’héritage par les types non approuvés.

 Il est possible de corriger une violation en ajoutant l’attribut APTCA pour les assemblys des types de base signalés par la violation. Ne le faites pas sans la première réalisation d’une révision de sécurité de tout le code dans les assemblys et de tout le code qui repose sur les assemblys.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Pour supprimer sans risque un avertissement de cette règle, vous devez vous assurer que les membres protégés exposés par votre type n’autorisent pas, directement ou indirectement, à des appelants non approuvés à accéder aux informations sensibles, des opérations ou des ressources qui peuvent être utilisées dans une action destructrice.

## <a name="example"></a>Exemple
 L’exemple suivant utilise deux assemblys et une application de test pour illustrer la vulnérabilité de sécurité détectée par cette règle. Le premier assembly n’a pas l’attribut APTCA et ne doit pas être hérité par les types de niveau de confiance partiel (représenté par `T2` dans la discussion précédente).

 [!code-csharp[FxCop.Security.NoAptcaInherit#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.NoAptcaInherit/cs/FxCop.Security.NoAptcaInherit.cs#1)]

## <a name="example"></a>Exemple
 Le deuxième assembly, représenté par `T1` dans la discussion précédente, est entièrement fiable, et permet aux appelants partiellement approuvés.

 [!code-csharp[FxCop.Security.YesAptcaInherit#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.YesAptcaInherit/cs/FxCop.Security.YesAptcaInherit.cs#1)]

## <a name="example"></a>Exemple
 Le type de test, représenté par `X` dans la discussion précédente, est dans un assembly partiellement approuvé.

 [!code-csharp[FxCop.Security.TestAptcaInherit#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TestAptcaInherit/cs/FxCop.Security.TestAptcaInherit.cs#1)]

 Cet exemple produit la sortie suivante.

 **Respecter à la glen louche 22/2/2003 12:00:00 AM ! ** 
 **à partir d’un Test : pré ensoleillée**
**se rencontrent en le pré ensoleillée 22/2/2003 12:00:00 AM !**
## <a name="related-rules"></a>Règles associées
 [CA2116 : Les méthodes APTCA doivent appeler seulement des méthodes APTCA](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)

## <a name="see-also"></a>Voir aussi
 [Instructions de codage sécurisé](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) [assemblys .NET Framework peut être appelés par le Code partiellement fiable](http://msdn.microsoft.com/en-us/a417fcd4-d3ca-4884-a308-3a1a080eac8d) [partiellement à l’aide de bibliothèques à partir de Code fiable](http://msdn.microsoft.com/library/dd66cd4c-b087-415f-9c3e-94e3a1835f74) [demandes d’héritage](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)




