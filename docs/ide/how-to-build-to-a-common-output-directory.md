---
title: 'Procédure : Créer un répertoire de sortie commun'
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory
- builds [Visual Studio], common directory
- common directory
ms.assetid: 1fcc2c48-07cb-4c4f-9556-36945e7dfc4e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 40a8ea93075294bb4419cfe4178965a8a4808cfc
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55949706"
---
# <a name="how-to-build-to-a-common-output-directory"></a>Procédure : Créer un répertoire de sortie commun

Par défaut, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] génère chaque projet dans une solution dans son propre dossier à l’intérieur de la solution. Vous pouvez changer les chemins de sortie de build de vos projets pour imposer que toutes les sorties soient placées dans le même dossier.

## <a name="to-place-all-solution-outputs-in-a-common-directory"></a>Pour placer toutes les sorties de solution dans un répertoire commun

1.  Cliquez sur un projet dans la solution.

2.  Dans le menu **Projet**, cliquez sur **Propriétés**.

3.  En fonction du type de projet, cliquez sur l’onglet **Compiler** ou sur l’onglet **Générer**, puis définissez comme **Chemin de sortie** un dossier à utiliser pour tous les projets de la solution.

4.  Répétez les étapes 1 à 3 pour tous les projets de la solution.

## <a name="see-also"></a>Voir aussi

- [Compiler et générer](../ide/compiling-and-building-in-visual-studio.md)
- [Guide pratique pour changer le répertoire de sortie de build](../ide/how-to-change-the-build-output-directory.md)