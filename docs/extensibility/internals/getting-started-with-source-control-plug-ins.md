---
title: Mise en route avec les Plug-ins de contrôle de code Source | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, getting started
- getting started, source control plug-ins
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 74fe044f5ce00697be36fc69413e0bf7d0042e62
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602869"
---
# <a name="get-started-with-source-control-plug-ins"></a>Bien démarrer avec les plug-ins de contrôle de code source
Pour créer un contrôle de source de plug-in, vous devez créer une DLL qui implémente les fonctions définies dans l’API de plug-in de contrôle de Source, puis inscrire la DLL avec [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pour le rendre disponible pour une utilisation dans le contrôle de version du code source.

 Trois versions de l’API de plug-in de contrôle de Source (versions 1.1, 1.2 et 1.3) sont disponibles pour les plug-ins de contrôle de code source. L’API de plug-in de contrôle Source décrite ici est la version 1.3. Il a été conçu pour être entièrement compatible avec les plug-ins de contrôle de code source prenant en charge les versions 1.1 et 1.2. Le [Nouveautés de la Version 1.3 des API de plug-in de contrôle Source](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) section décrit en détail les nouvelles fonctionnalités prises en charge dans la dernière version de l’API de plug-in de contrôle de Source.

## <a name="in-this-section"></a>Dans cette section
- [Guide pratique pour Installer un plug-in de contrôle de code source](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)

 Décrit comment rendre les entrées de Registre qui sont requis pour incorporer dans un DLL de contrôle de code source.

- [Nouveautés de la Version 1.3 des API de plug-in de contrôle Source](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)

 Fournit une vue d’ensemble des modifications qui ont été apportées à l’API de plug-in de contrôle de Source dans la version 1.3.

- [Nouveautés de la Version 1.2 des API de plug-in de contrôle Source](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

 Fournit une vue d’ensemble des modifications qui ont été apportées à l’API de plug-in de contrôle de Source dans la version 1.2.

## <a name="related-sections"></a>Rubriques connexes
- [Plug-ins de contrôle de code source](../../extensibility/source-control-plug-ins.md)

 Fournit une liste complète de tous les éléments dans l’API de plug-in de contrôle de Source.

- [Créer un contrôle de source de plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)

 Définit le SDK de plug-in de contrôle de Source et décrit les ressources incluses.