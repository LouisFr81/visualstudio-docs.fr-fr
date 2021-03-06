---
title: 'CA2006 : Utilisez SafeHandle pour encapsuler les ressources natives | Microsoft Docs'
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
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 88d53d90d00f58706e366b54dfa78b59e499bc24
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49935378"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006 : Utilisez SafeHandle pour encapsuler les ressources natives
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|Category|Microsoft.Reliability|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Le code managé utilise <xref:System.IntPtr> pour accéder aux ressources natives.

## <a name="rule-description"></a>Description de la règle
 Utilisation de `IntPtr` dans le code managé peut indiquer un problème potentiel de sécurité et de fiabilité. Toutes les utilisations de `IntPtr` doivent être examinées pour déterminer si l’utilisation d’un <xref:System.Runtime.InteropServices.SafeHandle> , ou une technologie similaire, est nécessaire à la place. Des problèmes seront produit si le `IntPtr` représente une ressource native, tels que la mémoire, un descripteur de fichier ou un socket, que le code managé est censé propre. Si le code managé est propriétaire de la ressource, il doit également libérer les ressources natives associés, car un échec pour ce faire, peut provoquer des fuites de ressources.

 Dans de tels scénarios, des problèmes de sécurité ou de fiabilité existera également si l’accès multithread est autorisé au `IntPtr` et un moyen de libérer la ressource qui est représentée par le `IntPtr` est fourni. Ces problèmes impliquent le recyclage de le `IntPtr` valeur sur la version de ressource alors que l’utilisation simultanée de la ressource est effectuée sur un autre thread. Cela peut entraîner des conditions de concurrence où un thread peut lire ou écrire des données qui sont associées à la ressource incorrecte. Par exemple, si votre type stocke un handle de système d’exploitation comme un `IntPtr` et permet aux utilisateurs d’appeler les opérations **fermer** et toute autre méthode qui utilise ce handle simultanément et sans une sorte de synchronisation, votre code a un recyclage de handle problème.

 Ce problème de recyclage de handle peut provoquer une altération des données et, souvent, une faille de sécurité. `SafeHandle` et sa classe sœur <xref:System.Runtime.InteropServices.CriticalHandle> fournissent un mécanisme pour encapsuler un handle natif à une ressource afin que ces problèmes de thread peuvent être évités. En outre, vous pouvez utiliser `SafeHandle` et sa classe sœur `CriticalHandle` pour d’autres problèmes liés aux threads, par exemple, pour contrôler attentivement la durée de vie des objets managés qui contiennent une copie du handle natif sur les appels aux méthodes natives. Dans ce cas, vous pouvez souvent supprimer des appels à `GC.KeepAlive`. Le performances généraux subie lorsque vous utilisez `SafeHandle` et, à un moindre degré, `CriticalHandle`, peuvent souvent être réduits via une conception minutieuse.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Convertir `IntPtr` utilisation à `SafeHandle` à gérer en toute sécurité l’accès aux ressources natives. Consultez le <xref:System.Runtime.InteropServices.SafeHandle> rubrique de référence pour obtenir des exemples.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Vous ne devez pas supprimer cet avertissement.

## <a name="see-also"></a>Voir aussi
 <xref:System.IDisposable>



