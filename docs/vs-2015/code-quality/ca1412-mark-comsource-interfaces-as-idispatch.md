---
title: 'CA1412 : Marquer les Interfaces ComSource comme IDispatch | Microsoft Docs'
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
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6b0e5f45778287ed9672773ce600b68c5b23cbd5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936106"
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412 : Marquer les interfaces ComSource comme IDispatch
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkComSourceInterfacesAsIDispatch|
|CheckId|CA1412|
|Category|Microsoft.Interoperability|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Un type est marqué avec le <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> attribut et au moins une interface spécifiée n’est pas marqué avec le <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> attribut défini sur le `InterfaceIsDispatch` valeur.

## <a name="rule-description"></a>Description de la règle
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> est utilisé pour identifier les interfaces d’événements qu’une classe expose aux clients de composant COM (Object Model). Ces interfaces doivent être exposées en tant que `InterfaceIsIDispatch` pour permettre aux clients COM Visual Basic 6 recevoir des notifications d’événements. Par défaut, si une interface n’est pas marquée avec le <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> attribut, elle est exposée comme une interface double.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, ajoutez ou modifiez la <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> attribut afin que sa valeur est définie sur InterfaceIsIDispatch pour toutes les interfaces qui sont spécifiés avec le <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> attribut.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant montre une classe où une des interfaces enfreint la règle.

 [!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.MarkIDispatch/cs/FxCop.Interoperability.MarkIDispatch.cs#1)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.MarkIDispatch/vb/FxCop.Interoperability.MarkIDispatch.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1408 : N’utilisez pas le paramètre AutoDual ClassInterfaceType](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Voir aussi
 [Comment : déclencher des événements gérés par un récepteur COM](http://msdn.microsoft.com/en-us/7c9944b2-e951-4c3e-a0a1-59b2ae37d7fd) [interopération avec du Code non managé](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



