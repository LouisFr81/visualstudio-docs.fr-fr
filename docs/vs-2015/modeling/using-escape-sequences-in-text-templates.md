---
title: Utilisation des séquences d’échappement dans les modèles de texte | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, escape sequences
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: be273c8cf69094a640ea7210bdbdc50005841a49
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49296541"
---
# <a name="using-escape-sequences-in-text-templates"></a>Utilisation de séquences d'échappement dans des modèles de texte
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser des séquences d’échappement dans les modèles de texte pour générer des balises de modèle de texte et (dans le code c# uniquement) et d’échappement les caractères de contrôle entre guillemets.  
  
 Pour imprimer les balises d’ouverts et de fermeture pour un bloc de code standard pour le fichier de sortie, échappez les balises comme suit :  
  
```  
\<# ... \#>  
```  
  
 Vous pouvez faire de même avec d’autres balises de bloc texte modèle directive et le code.  
  
 Si un bloc de texte inclut des chaînes utilisées pour échapper des balises de modèle de texte, vous pouvez utiliser les séquences d’échappement suivantes :  
  
-   Si une balise de modèle de texte est précédée d’un nombre pair de d’échappement (\\) le modèle de caractères analyseur inclura la moitié des caractères d’échappement et incluent la séquence comme une balise de modèle de texte. Par exemple, s’il existe quatre caractères d’échappement dans le modèle de texte, il y aura deux «\\» caractères dans le fichier généré.  
  
-   Si la balise de modèle de texte est précédée d’un nombre impair de d’échappement (\\) caractères, l’Analyseur de modèle inclura la moitié de la «\\» caractères ainsi que la balise proprement dite (\<# ou #>). La balise n’est pas considérée comme une balise de modèle de texte.  
  
-   Si un caractère d’échappement (\\) caractère apparaît nulle part ailleurs dans n’importe quel ordre autre qu’où la méthode remplace un caractère de contrôle ou un guillemet (en c# uniquement), le caractère affichera directement.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour générer des modèles à partir de modèles à l’aide de séquences d’échappement](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)



