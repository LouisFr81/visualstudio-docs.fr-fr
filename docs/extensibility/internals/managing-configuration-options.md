---
title: Gestion des Options de Configuration | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- configuration options
ms.assetid: 596c28ee-f48d-4252-a5c4-f730c43a39e6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ba3b7c2c1cac1255c6234d2b9a8ed6ab4fd05820
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56644534"
---
# <a name="managing-configuration-options"></a>Gestion des options de configuration
Lorsque vous créez un nouveau type de projet, vous devez gérer les paramètres de configuration de projet et solution qui déterminent comment votre projet sera généré, empaquetée et déployée exécution. Les rubriques suivantes décrivent la configuration de projet et solution.

## <a name="in-this-section"></a>Dans cette section
- [Vue d’ensemble](../../extensibility/internals/configuration-options-overview.md)

 Décrit comment les projets dans [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] peut prendre en charge les configurations à plusieurs.

- [Pages de propriétés](../../extensibility/internals/property-pages.md)

 Explique que les utilisateurs peuvent afficher et modifier les propriétés dépendantes de configuration de projet et les propriétés indépendantes à l’aide des pages de propriétés.

- [Configuration de la solution](../../extensibility/internals/solution-configuration.md)

 Fournit des informations sur ce qui est stocké dans les configurations de solution et comment les configurations de solution contrôlent le comportement de la **Démarrer** et **Build** commandes.

- [Objet de configuration de projet](../../extensibility/internals/project-configuration-object.md)

 Explique comment l’objet de configuration de projet gère l’affichage des informations de configuration à l’interface utilisateur.

- [Configuration de projet pour la création](../../extensibility/internals/project-configuration-for-building.md)

 Explique comment une liste des configurations de solution pour une solution particulière est gérée par le **Configurations de Solution** boîte de dialogue.

- [Configuration de projet pour la gestion du déploiement](../../extensibility/internals/project-configuration-for-managing-deployment.md)

 Définit l’action de déploiement et les deux façons [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prend en charge les projets qui prennent en charge le déploiement.

- [Configuration de projet pour la sortie](../../extensibility/internals/project-configuration-for-output.md)

 Explique les processus de génération chaque configuration peut prendre en charge et les interfaces et les méthodes par qui génèrent des éléments peuvent être rendues disponibles.

## <a name="related-sections"></a>Rubriques connexes
- [Types de projets](../../extensibility/internals/project-types.md)

 Fournit une vue d’ensemble des projets en tant que blocs de construction de base de la [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] l’environnement de développement intégré (IDE). Liens sont fournis vers des rubriques supplémentaires qui expliquent comment projets de contrôle de génération et compilation du code.