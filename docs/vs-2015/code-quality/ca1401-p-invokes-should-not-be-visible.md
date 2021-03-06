---
title: 'CA1401 : P-Invoke ne doit pas être visible | Microsoft Docs'
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
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 23142fcb226259378be56c59032d3b96d9b94087
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49852503"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401 : Les P/Invoke ne doivent pas être visibles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|Category|Microsoft.Interoperability|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une méthode publique ou protégée dans un type public a le <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> attribut (également implémenté par le `Declare` mot clé dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).

## <a name="rule-description"></a>Description de la règle
 Les méthodes marquées avec le <xref:System.Runtime.InteropServices.DllImportAttribute> attribut (ou les méthodes qui sont définies à l’aide de la `Declare` mot clé dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) Platform Invocation Services permet d’accéder au code non managé. De telles méthodes ne doivent pas être exposées. En gardant ces méthodes privées ou internes, vous vous assurer que votre bibliothèque ne peut pas être utilisée de violation de sécurité en autorisant l’accès à des API non managées qu’ils ne peuvent pas appeler sinon les appelants.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, modifiez le niveau d’accès de la méthode.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant déclare une méthode qui enfreint cette règle.

 [!code-csharp[FxCop.Interoperability.DllImports#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/cs/FxCop.Interoperability.DllImports.cs#1)]
 [!code-vb[FxCop.Interoperability.DllImports#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/vb/FxCop.Interoperability.DllImports.vb#1)]



