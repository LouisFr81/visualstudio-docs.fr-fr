---
title: L’accès à stockée paramètres de police et couleur | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- fonts, accessing stored settings
- font and color control [Visual Studio SDK], persistence
- colors, accessing stored settings
ms.assetid: beba7174-e787-45c2-b6ff-a60f67ad4998
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 66bbab5cf82d4ada241d8e5b3a4213ac51ecffd2
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335452"
---
# <a name="access-stored-font-and-color-settings"></a>Accès stockés des paramètres de police et couleur

Visual Studio stocke l’environnement de développement intégré (IDE) modifié des paramètres pour les polices et couleurs utilisées dans le Registre. Vous pouvez utiliser le <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> interface pour accéder à ces paramètres.

## <a name="to-initiate-state-persistence-of-fonts-and-colors"></a>Pour initier la persistance de l’état de polices et couleurs

Les informations de police et de couleur sont stockées par catégorie dans l’emplacement de Registre suivant : [HKCU\SOFTWARE\Microsoft \Visual Studio\\*\<version de Visual Studio >* \FontAndColors\\  *\<CategoryGUID >*], où  *\<CategoryGUID >* est le GUID de catégorie.

Par conséquent, pour lancer la persistance, un VSPackage doit :

-   Obtenir un <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> interface en appelant `QueryService` contre le fournisseur de services global.

     `QueryService` doit être appelée à l’aide d’un argument d’ID de service de `SID_SVsFontAndColorStorage` et un argument d’ID d’interface `IID_IVsFontAndColorStorage`.

-   Utilisez le <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.OpenCategory%2A> méthode pour ouvrir une catégorie à rendre persistantes à l’aide de GUID de la catégorie et un indicateur de mode en tant qu’arguments.

     Le mode spécifié par le `fFlags` argument, est construit à partir des valeurs dans le <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS> énumération. Ce mode contrôle :

    -   Les paramètres qui sont accessibles via le <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> interface.

    -   Tous les paramètres ou uniquement les paramètres qui modifient les utilisateurs et qui sont récupérables par le biais du <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> interface.

    -   La manière de propager les modifications apportées aux paramètres utilisateur.

    -   Le format de valeurs de couleur qui sont utilisés.

## <a name="to-use-state-persistence-of-fonts-and-colors"></a>Pour utiliser la persistance d’état de polices et couleurs

Couleurs et polices persistantes implique :

- Synchroniser les paramètres de l’IDE avec paramètres stockés dans le Registre.

- Propagation des informations de modification du Registre.

- Définition et récupération des paramètres stockés dans le Registre.

La synchronisation du paramètre de stockage avec les paramètres de l’IDE est en grande partie transparent. L’IDE sous-jacent écrit automatiquement les paramètres mis à jour pour **éléments affichés** pour les entrées de Registre des catégories.

Si plusieurs VSPackages partagent une catégorie particulière, un VSPackage doit exiger que les événements sont générés lorsque les méthodes de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> interface sont utilisés pour modifier les paramètres du Registre stockée.

Par défaut, la génération d’événements n’est pas activée. Pour activer la génération d’événements, une catégorie doit être ouvert à l’aide de [__FCSTORAGEFLAGS. FCSF_PROPAGATECHANGES](<xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS.FCSF_PROPAGATECHANGES>). Ouverture d’une catégorie de force l’IDE appeler approprié <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> méthode qui implémente un VSPackage.

> [!NOTE]
> Les modifications via le **police et couleur** page de propriétés génèrent des événements indépendants de <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>. Vous pouvez utiliser la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> interface pour déterminer si une mise à jour des paramètres de police et couleur de mise en cache est nécessaire avant d’appeler les méthodes de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> classe.

### <a name="store-and-retrieve-information"></a>Store et récupérer des informations

Pour obtenir ou configurer les informations un utilisateur peut modifier pour un élément d’affichage nommé dans une catégorie ouverte, VSPackages appeler le <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.SetItem%2A> méthodes.

Pour une catégorie particulière est obtenue à l’aide des attributs d’informations sur la police du <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.SetFont%2A> méthodes.

> [!NOTE]
> Le `fFlags` argument qui est passé à la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.OpenCategory%2A> méthode lors de l’ouverture de cette catégorie définit le comportement de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> méthodes. Par défaut, ces méthodes retournent uniquement des informations sur les éléments d’affichage qui ont été modifiés. Toutefois, si une catégorie est ouvert à l’aide de la [__FCSTORAGEFLAGS. FCSF_LOADDEFAULTS](<xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS.FCSF_LOADDEFAULTS>) indicateur, les deux mises à jour et éléments inchangés affichés sont accessibles par <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A>.

Par défaut, uniquement modifié **éléments affichés** informations sont conservées dans le Registre. Le <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> interface ne peut pas être utilisée pour récupérer tous les paramètres pour les polices et couleurs.

> [!NOTE]
> Le <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> et <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> méthodes retournent REGDB_E_KEYMISSING, (0x80040152L) lorsque vous les utilisez pour récupérer des informations sur inchangé **éléments affichés**.

Les paramètres de tous les **éléments affichés** en un particulier **catégorie** peut être obtenu en utilisant les méthodes de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> interface.

## <a name="see-also"></a>Voir aussi

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>
- <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS>
- [Implémenter des catégories personnalisées et afficher les éléments](../extensibility/implementing-custom-categories-and-display-items.md)