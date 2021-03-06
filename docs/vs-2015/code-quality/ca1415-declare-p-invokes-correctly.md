---
title: 'CA1415 : Déclarer P-Invoke correctement | Microsoft Docs'
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
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c2a945029652f67fe7332a336e62523bba8175f6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49857287"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415 : Déclarer correctement les méthodes P/Invoke
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|Category|Microsoft.Interoperability|
|Modification avec rupture|Sans rupture - Si P/Invoke qui déclare le paramètre ne peut pas être visible à l’extérieur de l’assembly. Avec rupture - Si P/Invoke qui déclare le paramètre peut être consulté en dehors de l’assembly.|

## <a name="cause"></a>Cause
 Une méthode non managé est déclarée de manière incorrecte.

## <a name="rule-description"></a>Description de la règle
 Une plateforme d’appeler la méthode accède à un code non managé et est définie à l’aide de la `Declare` mot clé dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ou <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. Actuellement, cette règle recherche des déclarations de méthode qui ciblent des fonctions Win32 présentant un pointeur vers un paramètre de structure OVERLAPPED non managé et le paramètre managé correspondant n’est pas un pointeur vers un <xref:System.Threading.NativeOverlapped?displayProperty=fullName> structure.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, déclarez correctement la plateforme appeler la méthode.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant illustre les méthodes qui violent la règle et satisfaire à la règle non managé.

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DeclarePInvokes/cs/FxCop.Interoperability.DeclarePInvokes.cs#1)]

## <a name="see-also"></a>Voir aussi
 [Interopération avec du code non managé](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



