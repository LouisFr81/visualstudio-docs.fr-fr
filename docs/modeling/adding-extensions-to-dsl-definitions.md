---
title: Ajout d'extensions à des définitions DSL
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec4be7c084bbcd1a73affa3035f1ef116d958c9a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55909621"
---
# <a name="add-extensions-to-dsl-definitions"></a>Ajouter des extensions à des définitions DSL

Extension de définition DSL vous permet de créer un package d’extensions à un langage spécifique à un domaine (DSL). L’extension DSL, qui est contenue dans une Extension d’intégration Visual Studio (VSIX), peut être installée sur l’ordinateur d’un utilisateur dans la même manière qu’une solution DSL. Les fonctionnalités supplémentaires peuvent être dynamiquement activées et désactivées au moment de l’exécution. DSL n’ont pas à être explicitement conçu pour l’extension, et extensions peuvent être conçues ultérieurement, ou par des tiers, sans en altérer le DSL étendue.

Extensions DSL peuvent inclure les fonctionnalités suivantes :

-   Propriétés des éléments de modèle et de présentation

-   Éléments décoratifs pour les formes et connecteurs

-   Classes, des relations, formes et connecteurs

-   Contraintes de validation

-   Onglets et des éléments de boîte à outils

Un utilisateur d’un langage DSL étendu peut créer et enregistrer un modèle qui contient les instances des fonctionnalités supplémentaires. Le modèle peut être lu par d’autres utilisateurs qui ont installé l’extension appropriée. Les utilisateurs qui n’ont pas installé l’extension ne peut pas utiliser les fonctionnalités supplémentaires, mais ils peuvent mettre à jour et enregistrer un modèle sans perdre les fonctionnalités supplémentaires.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Voir aussi

- [Billets de blog connexes](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
