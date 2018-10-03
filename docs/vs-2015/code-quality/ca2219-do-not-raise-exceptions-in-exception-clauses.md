---
title: 'CA2219 : Ne levez pas d’exceptions dans les clauses d’exception | Microsoft Docs'
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
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3f3ea7368026e2e120e877a8689319762fa2b55e
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47516905"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219 : Ne pas lever d'exceptions dans les clauses d'exception
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA2219 : ne levez pas d’exceptions dans les clauses d’exception](https://docs.microsoft.com/visualstudio/code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses).

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture, rupture|

## <a name="cause"></a>Cause
 Une exception est levée à partir d’un `finally`, filtre ou une clause fault.

## <a name="rule-description"></a>Description de la règle
 Lorsqu’une exception est déclenchée dans une clause d’exception, elle augmente considérablement la difficulté du débogage.

 Lorsqu’une exception est levée dans un `finally` ou une clause fault, la nouvelle exception masque l’exception active, le cas échéant. Cela rend l’erreur d’origine difficile à détecter et à déboguer.

 Lorsqu’une exception est déclenchée dans une clause de filtre, le runtime en mode silencieux intercepte l’exception et provoque le filtre doit évaluer sur false. Il n’existe aucun moyen de faire la différence entre l’évaluation de filtre false et une exception soit levée à partir d’un filtre. Cela rend difficiles à détecter et à déboguer les erreurs dans la logique du filtre.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour résoudre cette violation de cette règle, ne levez pas explicitement d’exception à partir d’un `finally`, filtre ou une clause fault.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez pas d’avertissement pour cette règle. Il n’existe aucun scénario dans lequel une exception levée dans une clause d’exception confère un avantage pour l’exécution de code.

## <a name="related-rules"></a>Règles associées
 [CA1065 : Ne levez pas d’exceptions dans des emplacements inattendus](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>Voir aussi
 [Avertissements liés à la conception](../code-quality/design-warnings.md)


