---
title: ': CA2228 ne pas les formats de ressources non commercialisés | Microsoft Docs'
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
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: eb5e595062ca39ba644499012981c78d7a986ced
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49917524"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228 : Ne distribuez pas des formats de ressources non commercialisés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un fichier de ressources a été créé à l’aide d’une version de la [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] qui est actuellement pas en charge.

## <a name="rule-description"></a>Description de la règle
 Les fichiers de ressources qui ont été créés à l’aide de versions préliminaires de la [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] peut ne pas être utilisables par les versions prises en charge du .NET Framework.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, générez la ressource à l’aide d’une version prise en charge de la [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]k.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.



