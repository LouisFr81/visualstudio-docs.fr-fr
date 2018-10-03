---
title: 'CA1716 : Les identificateurs ne doivent pas correspondre aux mots clés | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c1a3affbecf7a39ee323fd64bc8a56d92e8a4d5e
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588079"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716 : Les identificateurs ne doivent pas correspondre à des mots clés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA1716 : les identificateurs ne doivent pas correspondre aux mots clés](https://docs.microsoft.com/visualstudio/code-quality/ca1716-identifiers-should-not-match-keywords).

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Category|Microsoft.Naming|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un nom d’un espace de noms, un type ou un membre d’interface ou virtuel correspond à un mot clé réservé dans un langage de programmation.

## <a name="rule-description"></a>Description de la règle
 Identificateurs pour les espaces de noms, types et virtuels et les membres d’interface ne doivent pas correspondre aux mots clés définis par les langages qui ciblent le common language runtime. Selon le langage qui est utilisé et le mot clé, ambiguïtés et les erreurs du compilateur peuvent rendre la bibliothèque difficile à utiliser.

 Cette règle vérifie par rapport à des mots clés dans les langues suivantes :

-   Visual Basic

-   C#

-   C++/CLI

 Comparaison de non-respect de la casse est utilisée pour [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] mots clés et comparaison respectant la casse est utilisée pour les autres langues.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Sélectionnez un nom qui n’apparaît pas dans la liste des mots clés.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Vous pouvez supprimer un avertissement de cette règle si vous êtes convaincu que l’identificateur sera confondez pas les utilisateurs de l’API, et que la bibliothèque est utilisable dans toutes les langues disponibles dans le [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].


