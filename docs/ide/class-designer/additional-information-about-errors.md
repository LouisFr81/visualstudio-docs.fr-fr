---
title: Erreurs du Concepteur de classes
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.classdesigner.CPlusPlusViewInDiagramNoTypeFound
- vs.classdesigner.CPlusPlusNoTypeFound
- vs.classdesigner.CannotShowBaseType
- vs.classdesigner.MatchOrphanTypesAtLoad
- vs.classdesigner.CannotShowType
- vs.classdesigner.AssociationTypeNotFoundError
- vs.classdesigner.ViewInDiagramNoTypesFound
- vs.classdesigner.CannotImplementInterface
- vs.classdesigner.CannotShowImplementedInterface
- vs.classdesigner.ViewInDiagramUnparsableTypeFound
- vs.classdesigner.AssociationTypeNotFound
- vs.classdesigner.CPlusPlusTypeCannotBeAdded
helpviewer_keywords:
- errors, class diagrams
- errors, Class Designer
- error messages, Class Designer
- error messages, class diagrams
- Class Designer [Visual Studio], errors
- class diagrams, errors
ms.assetid: 79d70e70-704c-4255-ab68-c10d6949470e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: aadc0cfb66226f463ff8a2049d4dbf81e7bcf62b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55957102"
---
# <a name="class-designer-errors"></a>Erreurs du Concepteur de classes

Le **Concepteur de classes** n’effectue pas le suivi de l’emplacement de vos fichiers sources. Si vous modifiez votre structure de projet ou déplacez des fichiers sources dans le projet, le **Concepteur de classes** peut perdre la trace du type. Par exemple, il est fréquent de modifier le type source d’un typedef, de classes de base et de types d’associations. Vous pouvez recevoir une erreur telle que **Le Concepteur de classes n’est pas en mesure d’afficher ce type**. Pour résoudre cette erreur, refaites glisser le code source modifié ou déplacé vers le diagramme de classes pour l’afficher.

## <a name="resources"></a>Ressources

Vous pouvez obtenir de l'aide sur d'autres erreurs et avertissements dans les ressources suivantes :

- [Utiliser le code Visual C++](working-with-visual-cpp-code.md) inclut des informations de dépannage sur l’affichage de C++ dans un diagramme de classes.
- Le [Forum du Concepteur de classes Visual Studio](http://go.microsoft.com/fwlink/?LinkId=160754) propose un forum de questions relatives au **Concepteur de classes**.

## <a name="see-also"></a>Voir aussi

- [Concevoir et afficher des classes et des types](designing-and-viewing-classes-and-types.md)
