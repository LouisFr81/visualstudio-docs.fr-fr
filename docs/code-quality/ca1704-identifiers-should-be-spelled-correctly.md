---
title: "CA1704 : L'orthographe des identificateurs doit être correcte"
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8dbfc8081f980b7b9e978da782f1627a88a716a3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55941282"
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704 : L'orthographe des identificateurs doit être correcte

|||
|-|-|
|TypeName|IdentifiersShouldBeSpelledCorrectly|
|CheckId|CA1704|
|Category|Microsoft.Naming|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause

Le nom d’un identificateur contient un ou plusieurs mots qui ne sont pas reconnus par la bibliothèque de vérificateur d’orthographe Microsoft. Cette règle ne pas vérifier les constructeurs ou les membres de dénomination spéciale telles que get et définir des accesseurs de propriété.

## <a name="rule-description"></a>Description de la règle

Cette règle analyse l’identificateur dans des jetons et vérifie l’orthographe de chaque jeton. L’algorithme d’analyse effectue les transformations suivantes :

- Les lettres majuscules démarrent un nouveau jeton. Par exemple, MonNomestJosé crée des jetons à « Mon », « Name », « Est », « Joe ».

- Pour plusieurs lettres majuscules, la dernière lettre majuscule démarre un nouveau jeton. Par exemple, ÉditeurGUI crée des jetons à « Interface graphique utilisateur », « Éditeur ».

- Début et de fin des apostrophes sont supprimés. Par exemple, 'sender' crée des jetons à « expéditeur ».

- Traits de soulignement indiquent la fin d’un jeton et sont supprimés. Par exemple, Hello_world crée des jetons à « Hello », « world ».

- Esperluettes incorporées sont supprimées. Par exemple, pour & mat crée des jetons pour « format ».

## <a name="language"></a>Langue

Actuellement, le vérificateur d’orthographe vérifie uniquement à des dictionnaires de culture en anglais. Vous pouvez modifier la culture de votre projet dans le fichier projet, en ajoutant le **CodeAnalysisCulture** élément.

Exemple :

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> Si vous définissez la culture sur autre chose qu’une culture en anglais, cette règle d’analyse du code est désactivée en mode silencieux.

## <a name="how-to-fix-violations"></a>Comment corriger les violations

Pour corriger une violation de cette règle, corrigez l’orthographe du mot ou ajoutez le mot au dictionnaire personnalisé.

### <a name="to-add-words-to-a-custom-dictionary"></a>Pour ajouter des mots dans un dictionnaire personnalisé

Nommez le fichier XML de dictionnaire personnalisé *CustomDictionary.xml*. Placer le dictionnaire dans le répertoire d’installation de l’outil, le répertoire du projet, ou dans le répertoire associé à l’outil sous le profil de l’utilisateur (*%USERPROFILE%\Application données\\...* ). Pour savoir comment ajouter le dictionnaire personnalisé à un projet dans Visual Studio, consultez [Comment : Personnaliser le dictionnaire d’analyse du Code](../code-quality/how-to-customize-the-code-analysis-dictionary.md).

- Ajouter des mots qui ne doivent pas provoquer une violation sous le chemin d’accès de mots/dictionnaire/reconnues.

- Ajouter des mots qui doivent provoquer une violation sous le chemin d’accès de dictionnaire/mots/non reconnu.

- Ajouter des mots qui doivent être marqués comme obsolète sous le chemin d’accès de mots/dictionnaire/déconseillées. Consultez la rubrique associée [CA1726 : Utiliser des termes](../code-quality/ca1726-use-preferred-terms.md) pour plus d’informations.

- Ajoutez des exceptions aux règles de casse acronyme pour le chemin d’accès des acronymes/dictionnaire/CasingExceptions.

Voici un exemple de la structure d’un fichier de dictionnaire personnalisé :

```xml
<Dictionary>
   <Words>
      <Unrecognized>
         <Word>cb</Word>
      </Unrecognized>
      <Recognized>
         <Word>stylesheet</Word>
         <Word>GotDotNet</Word>
      </Recognized>
      <Deprecated>
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>
      </Deprecated>
   </Words>
   <Acronyms>
      <CasingExceptions>
         <Acronym>CJK</Acronym>
         <Acronym>Pi</Acronym>
      </CasingExceptions>
   </Acronyms>
</Dictionary>
```

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements

Supprimez un avertissement de cette règle uniquement si le mot est intentionnellement mal orthographié et le mot s’applique à un ensemble limité de la bibliothèque. Mots épelés correctement réduisent la courbe d’apprentissage qui est requise pour les nouvelles bibliothèques de logiciels.

## <a name="related-rules"></a>Règles associées

- [CA2204 : Les littéraux doivent être correctement orthographiés](../code-quality/ca2204-literals-should-be-spelled-correctly.md)
- [CA1703 : Chaînes de ressources doivent être correcte](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1709 : Identificateurs doivent être correcte](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708 : Les identificateurs doivent différer par leur casse](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707 : Identificateurs ne doivent pas contenir de traits de soulignement](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1726 : Utilisez les termes préférés](../code-quality/ca1726-use-preferred-terms.md)

## <a name="see-also"></a>Voir aussi

- [Guide pratique pour Personnaliser le dictionnaire d’analyse du Code](../code-quality/how-to-customize-the-code-analysis-dictionary.md)
