---
title: 'CA2201 : Ne levez pas des types d’exceptions réservés | Microsoft Docs'
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
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9cc22f6bc8f7e863f0808c05b0b5cba37ba79fbf
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49810591"
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201 : Ne levez pas des types d'exceptions réservés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotRaiseReservedExceptionTypes|
|CheckId|CA2201|
|Category|Microsoft.Usage|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une méthode déclenche un type d’exception trop général ou qui est réservée par le runtime.

## <a name="rule-description"></a>Description de la règle
 Les types d’exception suivants sont trop généraux pour fournir suffisamment d’informations à l’utilisateur :

- <xref:System.Exception?displayProperty=fullName>

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.SystemException?displayProperty=fullName>

  Les types d’exception suivants sont réservés et doivent être levées uniquement par le common language runtime :

- <xref:System.ExecutionEngineException?displayProperty=fullName>

- <xref:System.IndexOutOfRangeException?displayProperty=fullName>

- <xref:System.NullReferenceException?displayProperty=fullName>

- <xref:System.OutOfMemoryException?displayProperty=fullName>

  **Ne levez pas d’Exceptions générales**

  Si vous lever un type d’exception générale, tel que <xref:System.Exception> ou <xref:System.SystemException> dans une bibliothèque ou une infrastructure, il oblige les utilisateurs à intercepter toutes les exceptions, y compris les exceptions inconnues qu’ils ne savent pas gérer.

  Au lieu de cela, levez un type plus dérivé qui existe déjà dans le framework ou créer votre propre type qui dérive de <xref:System.Exception>.

  **Lever des Exceptions spécifiques**

  Le tableau suivant présente les paramètres et les exceptions à lever lorsque vous validez le paramètre, y compris le paramètre de valeur dans l’accesseur set d’une propriété :

|Description du paramètre|Exception|
|---------------------------|---------------|
|`null` Référence|<xref:System.ArgumentNullException?displayProperty=fullName>|
|En dehors de la plage autorisée de valeurs (par exemple, un index pour une collection ou liste)|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|
|Non valide `enum` valeur|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|
|Contient un format qui ne répond pas aux spécifications de paramètres d’une méthode (telles que la chaîne de format pour `ToString(String)`)|<xref:System.FormatException?displayProperty=fullName>|
|Non valide|<xref:System.ArgumentException?displayProperty=fullName>|

 Lorsqu’une opération est non valide pour l’état actuel d’un objet levez <xref:System.InvalidOperationException?displayProperty=fullName>

 Lorsqu’une opération est effectuée sur un objet qui a été supprimé levez <xref:System.ObjectDisposedException?displayProperty=fullName>

 Lorsqu’une opération n’est pas pris en charge (par exemple, dans un substituée **Stream.Write** dans un Stream ouvert en lecture) lever <xref:System.NotSupportedException?displayProperty=fullName>

 Lorsqu’une conversion entraînerait un dépassement de capacité (comme une surcharge d’opérateur de cast explicite) levez <xref:System.OverflowException?displayProperty=fullName>

 Pour toutes les autres situations, envisagez de créer votre propre type qui dérive de <xref:System.Exception> et levez cette exception.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, modifier le type de l’exception levée à un type spécifique qui ne fait pas partie des types réservés.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="related-rules"></a>Règles associées
 [CA1031 : Ne pas intercepter des types d’exception générale](../code-quality/ca1031-do-not-catch-general-exception-types.md)



