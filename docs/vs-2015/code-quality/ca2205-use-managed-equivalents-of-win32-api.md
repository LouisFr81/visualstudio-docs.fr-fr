---
title: 'CA2205 : Utilisez équivalents managés d’API Win32 | Microsoft Docs'
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
- UseManagedEquivalentsOfWin32Api
- CA2205
helpviewer_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ba23b176ed4f2120f4675611567955bdaf652153
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49907467"
---
# <a name="ca2205-use-managed-equivalents-of-win32-api"></a>CA2205 : Utilisez des équivalents managés de l'API Win32
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseManagedEquivalentsOfWin32Api|
|CheckId|CA2205|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un appel de méthode est définie et une méthode avec la fonctionnalité équivalente existe dans le [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] bibliothèque de classes.

## <a name="rule-description"></a>Description de la règle
 Un appel de méthode est utilisée pour appeler une fonction DLL non managée et est définie à l’aide de la <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> attribut, ou le `Declare` mot clé dans Visual Basic. Une méthode non managé défini de manière incorrecte peut entraîner des exceptions runtime en raison de problèmes tels qu’une fonction incorrectement, un mappage de types de données de valeur paramètre et de retour et champ incorrect spécifications, telles que la convention d’appel et le caractère erronée ensemble. S’il est disponible, il est généralement plus simple et moins sujettes à appeler la méthode managée équivalente à to définir et appeler la méthode non managée directement. Appel une plateforme appel de méthode peut également entraîner des problèmes de sécurité supplémentaires qui doivent être traitées.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, remplacez l’appel à la fonction non managée par un appel à son équivalent géré.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez un avertissement de cette règle si la méthode de remplacement suggérée ne fournit pas les fonctionnalités nécessaires.

## <a name="example"></a>Exemple
 Définition de méthode qui enfreint la règle d’appel de l’exemple suivant montre une plateforme. En outre, les appels à la plateforme appeler la méthode et la méthode managée équivalente sont affichés.

 [!code-csharp[FxCop.Usage.ManagedEquivalents#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.ManagedEquivalents/cs/FxCop.Usage.ManagedEquivalents.cs#1)]
 [!code-vb[FxCop.Usage.ManagedEquivalents#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.ManagedEquivalents/vb/FxCop.Usage.ManagedEquivalents.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1404 : Appeler GetLastError immédiatement après P/Invoke](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)

 [CA1060 : Déplacer les P/Invoke vers une classe NativeMethods](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)

 [CA1400 : Des points d’entrée P/Invoke doivent exister](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)

 [CA1401 : Les P/Invoke ne doivent pas être visibles](../code-quality/ca1401-p-invokes-should-not-be-visible.md)

 [CA2101 : Spécifier le marshaling pour les arguments de chaîne P/Invoke](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)



