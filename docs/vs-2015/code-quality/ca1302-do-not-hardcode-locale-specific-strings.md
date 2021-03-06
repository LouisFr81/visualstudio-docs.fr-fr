---
title: 'CA1302 : Ne pas coder en dur les chaînes spécifiques aux paramètres régionaux | Microsoft Docs'
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
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 23f2b807d66662691afaa4805a50b34255a39bdb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49842415"
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302 : Ne pas coder en dur les chaînes spécifiques aux paramètres régionaux
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotHardcodeLocaleSpecificStrings|
|CheckId|CA1302|
|Category|Microsoft.Globalization|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Une méthode utilise un littéral de chaîne qui représente la partie du chemin d’accès de certains dossiers système.

## <a name="rule-description"></a>Description de la règle
 Le <xref:System.Environment.SpecialFolder?displayProperty=fullName> énumération contient des membres qui font référence à des dossiers système spéciaux. Les emplacements de ces dossiers peuvent avoir des valeurs différentes sur différents systèmes d’exploitation, l’utilisateur peut modifier certains de ces emplacements, et ces derniers sont localisés. Un exemple d’un dossier spécial est le dossier système, qui est « C:\WINDOWS\system32 » sur [!INCLUDE[winxp](../includes/winxp-md.md)] mais « C:\WINNT\system32 » sur [!INCLUDE[win2kfamily](../includes/win2kfamily-md.md)]. Le <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> méthode retourne les emplacements qui sont associés les <xref:System.Environment.SpecialFolder> énumération. Les emplacements retournés par <xref:System.Environment.GetFolderPath%2A> sont localisés et appropriés pour l’ordinateur en cours d’exécution.

 Cette règle crée des jetons dans les chemins d’accès de dossier sont récupérées en utilisant le <xref:System.Environment.GetFolderPath%2A> méthode dans les niveaux de répertoires séparés. Chaque littéral de chaîne est comparé aux jetons. Si une correspondance est trouvée, il est supposé que la méthode génère une chaîne qui fait référence à l’emplacement du système qui est associé au jeton. Pour la portabilité et d’adaptabilité, utilisez la <xref:System.Environment.GetFolderPath%2A> méthode pour récupérer les emplacements des dossiers système spéciaux au lieu d’utiliser des littéraux de chaîne.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, extraire l’emplacement à l’aide de la <xref:System.Environment.GetFolderPath%2A> (méthode).

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer un avertissement de cette règle si le littéral de chaîne n’est pas utilisé pour faire référence à un des emplacements du système qui est associé le <xref:System.Environment.SpecialFolder> énumération.

## <a name="example"></a>Exemple
 L’exemple suivant génère le chemin d’accès du dossier application data commun, qui génère trois avertissements de cette règle. Ensuite, l’exemple récupère le chemin d’accès à l’aide de la <xref:System.Environment.GetFolderPath%2A> (méthode).

 [!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.HardcodedLocaleStrings/cs/FxCop.Globalization.HardcodedLocaleStrings.cs#1)]
 [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Globalization.HardcodedLocaleStrings/vb/FxCop.Globalization.HardcodedLocaleStrings.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1303 : Ne passez pas des littéraux comme paramètres localisés](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)



