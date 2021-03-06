---
title: 'CA1501 : Éviter l’excès d’héritage | Microsoft Docs'
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
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 378a6de743a9f9698bf66949cfb7b271e836c617
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49872341"
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501 : Éviter l'excès d'héritage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidExcessiveInheritance|
|CheckId|CA1501|
|Category|Microsoft.Maintainability|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type est imbriqué de plus de quatre niveaux dans sa hiérarchie d'héritage.

## <a name="rule-description"></a>Description de la règle
 Les hiérarchies de type profondément imbriquées peuvent être difficiles à suivre, comprendre et gérer. Cette règle limite l’analyse aux hiérarchies dans le même module.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, dérivez le type d’un type de base moins imbriqué dans la hiérarchie d’héritage ou éliminer certains des types de base intermédiaires.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer un avertissement de cette règle. Toutefois, le code peut être plus difficile à gérer. Notez que, en fonction de la visibilité des types de base, résolution des violations de cette règle peut créer des modifications avec rupture. Par exemple, la suppression des types de base publiques est une modification avec rupture.

## <a name="example"></a>Exemple
 L’exemple suivant montre un type qui viole la règle.

 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Maintainability.ExcessiveInheritance/cs/FxCop.Maintainability.ExcessiveInheritance.cs#1)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Maintainability.ExcessiveInheritance/vb/FxCop.Maintainability.ExcessiveInheritance.vb#1)]



