---
title: 'CA2144 : Le code Transparent ne doit pas charger d’assemblys à partir de tableaux d’octets | Microsoft Docs'
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
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a3ecbf57bf8b4af2bf8edd66a406d27f96809b39
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47516901"
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144 : Le code transparent ne doit pas charger d'assemblys depuis des tableaux d'octets
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA2144 : le code Transparent ne doit pas charger les assemblys à partir de tableaux d’octets](https://docs.microsoft.com/visualstudio/code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays).

|||
|-|-|
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|
|CheckId|CA2144|
|Category|Microsoft.Security|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une méthode transparente charge un assembly à partir d’un tableau d’octets à l’aide d’une des méthodes suivantes :

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

## <a name="rule-description"></a>Description de la règle
 La révision de sécurité du code transparent n’est pas aussi complète que la révision de sécurité du code critique, car le code transparent ne peut pas exécuter d’actions relatives à la sécurité. Les assemblys chargés à partir d’un tableau d’octets peuvent ne pas être remarqués dans du code transparent, et ce tableau d’octets peut contenir du code critique, voire critique de sécurité, qui doit être audité. Par conséquent, le code transparent ne doit pas charger les assemblys à partir d’un tableau d’octets.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, marquez la méthode qui charge l’assembly avec le <xref:System.Security.SecurityCriticalAttribute> ou <xref:System.Security.SecuritySafeCriticalAttribute> attribut.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 Cette règle se déclenche sur le code suivant, car une méthode transparente charge un assembly à partir d’un tableau d’octets.

 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2144.transparentmethodsshouldnotloadassembliesfrombytearrays/cs/ca2144 - transparentmethodsshouldnotloadassembliesfrombytearrays.cs#1)]


