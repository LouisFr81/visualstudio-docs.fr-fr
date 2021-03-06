---
title: Conditions MSBuild | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, conditions
- conditions [MSBuild]
ms.assetid: 9d7aa308-b667-48ed-b4c9-a61e49eb0a85
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 30ac71ccce1b237913db5acc8b34300b0517bcd6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54969744"
---
# <a name="msbuild-conditions"></a>Conditions MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] prend en charge un ensemble spécifique de conditions qui peuvent être appliquées à chaque fois qu’un attribut `Condition` est autorisé. Le tableau suivant décrit ces conditions.  
  
|Condition|Description|  
|---------------|-----------------|  
|'`stringA`' == '`stringB`'|A la valeur `true` si `stringA` équivaut à `stringB`.<br /><br /> Par exemple :<br /><br /> `Condition="'$(CONFIG)'=='DEBUG'"`<br /><br /> Les guillemets simples ne sont pas requis pour les chaînes alphanumériques simples ou les valeurs booléennes, mais ils le sont pour les valeurs vides.|  
|'`stringA`' != '`stringB`'|A la valeur `true` si `stringA` est différent de `stringB`.<br /><br /> Par exemple :<br /><br /> `Condition="'$(CONFIG)'!='DEBUG'"`<br /><br /> Les guillemets simples ne sont pas requis pour les chaînes alphanumériques simples ou les valeurs booléennes, mais ils le sont pour les valeurs vides.|  
|\<, >, \<=, >=|Évalue les valeurs numériques des opérandes. Retourne `true` si l’évaluation relationnelle a la valeur true. Les opérandes doivent être un nombre décimal ou hexadécimal. Les nombres hexadécimaux doivent commencer par « 0x ». **Remarque :**  au format XML, les caractères `<` et `>` doivent être insérés dans une séquence d’échappement. Le symbole `<` est représenté sous la forme `&lt;`. Le symbole `>` est représenté sous la forme `&gt;`.|  
|Exists(« `stringA` »)|A la valeur `true` si un fichier ou un dossier du nom `stringA` existe.<br /><br /> Par exemple :<br /><br /> `Condition="!Exists('$(builtdir)')"`<br /><br /> Les guillemets simples ne sont pas requis pour les chaînes alphanumériques simples ou les valeurs booléennes, mais ils le sont pour les valeurs vides.|  
|HasTrailingSlash (« `stringA` »)|A la valeur `true` si la chaîne spécifiée contient une barre oblique inverse finale (\\) ou une barre oblique (/).<br /><br /> Par exemple :<br /><br /> `Condition="!HasTrailingSlash('$(OutputPath)')"`<br /><br /> Les guillemets simples ne sont pas requis pour les chaînes alphanumériques simples ou les valeurs booléennes, mais ils le sont pour les valeurs vides.|  
|!|A la valeur `true` si l’opérande a la valeur `false`.|  
|Et|A la valeur `true` si les deux opérandes ont la valeur `true`.|  
|Ou|A la valeur `true` si l’un des opérandes au moins a la valeur `true`.|  
|()|Mécanisme de regroupement qui prend la valeur `true` si les expressions qu’il contient ont la valeur `true`.|  
|$if$ ( %expression% ), $else$, $endif$|Vérifie si la condition `%expression%` spécifiée correspond à la valeur de chaîne du paramètre de modèle personnalisé transmis. Si la condition `$if$` prend la valeur `true`, ses instructions sont exécutées ; dans le cas contraire, la condition `$else$` est vérifiée. Si la condition `$else$` a la valeur `true`, ses instructions sont exécutées. Dans le cas contraire, la condition `$endif$` met fin à l’évaluation de l’expression.<br /><br /> Pour obtenir des exemples d’utilisation, consultez [Logique des paramètres de modèles de projet/d’élément Visual Studio](http://stackoverflow.com/questions/6709057/visual-studio-project-item-template-parameter-logic).|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur MSBuild](../msbuild/msbuild-reference.md)   
 [Constructions conditionnelles](../msbuild/msbuild-conditional-constructs.md)   
 [Procédure pas à pas : Créer un fichier projet MSBuild à partir de zéro](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)
