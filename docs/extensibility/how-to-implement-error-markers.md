---
title: 'Procédure : Implémenter des marqueurs d’erreur | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - error markers
ms.assetid: e8e78514-5720-4fc2-aa43-00b6af482e38
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2934cb9cb009a46cbd79340173eb2cad0a0fefe0
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720080"
---
# <a name="how-to-implement-error-markers"></a>Procédure : Implémenter des marqueurs d’erreur
Marqueurs d’erreur (ou des soulignements ondulés rouges) sont les personnalisations de l’éditeur de texte pour implémenter la plus difficile. Toutefois, les avantages qu’ils donnent aux utilisateurs de votre VSPackage peuvent compensent largement le coût afin de lui fournir. Marqueurs d’erreur légèrement marquer le texte que votre analyseur de langage juge incorrecte avec une ligne rouge ondulée ou ondulée. Cet indicateur permet aux programmeurs en affichant visuellement code incorrect.

 Utiliser des marqueurs de texte pour implémenter les soulignements ondulés rouges. En règle générale, services de langage ajouter des soulignements ondulés rouges à la mémoire tampon de texte comme une réussite en arrière-plan en période d’inactivité ou dans un thread d’arrière-plan.

## <a name="to-implement-the-red-wavy-underline-feature"></a>Pour implémenter la fonctionnalité de soulignement ondulé rouge

1. Sélectionnez le texte sous lequel vous voulez placer la ligne ondulée rouge.

2. Créer un marqueur de type `MARKER_CODESENSE_ERROR`. Pour plus d'informations, voir [Procédure : Ajouter des marqueurs de texte standard](../extensibility/how-to-add-standard-text-markers.md).

3. Après cela, transmettez un <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> pointeur d’interface.

   Ce processus vous permet également de vous permettent de créer le texte info-bulle ou un menu contextuel spéciaux sur un marqueur donné. Pour plus d'informations, voir [Procédure : Ajouter des marqueurs de texte standard](../extensibility/how-to-add-standard-text-markers.md).

   Les objets suivants sont nécessaires avant que les marqueurs d’erreur peuvent être affichées.

- Un analyseur.

- Un fournisseur de tâches (autrement dit, une implémentation de <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2>) qui conserve un enregistrement des modifications dans les informations de ligne afin d’identifier les lignes pour être réanalysé.

- Événements de modification d’un filtre de vue de texte qui capture le signe insertion à partir de la vue en utilisant le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents.OnChangeCaretLine%2A>) méthode.

  L’analyseur, le fournisseur de tâche et le filtre fournissent l’infrastructure nécessaire pour rendre les marqueurs d’erreur possible. Les étapes suivantes décrivent le processus pour l’affichage des marqueurs d’erreur.

1.  Dans une vue filtrée, le filtre Obtient un pointeur vers le fournisseur de tâches associé aux données de cette vue.

    > [!NOTE]
    >  Vous pouvez utiliser le même filtre de commande pour les conseils de méthode, saisie semi-automatique des instructions, erreur marques et ainsi de suite.

2.  Lorsque le filtre reçoit un événement indiquant que vous avez déplacé vers une autre ligne, une tâche est créée pour rechercher des erreurs.

3.  Le Gestionnaire de tâches vérifie si la ligne a été modifiée. Dans ce cas, il analyse la ligne pour les erreurs.

4.  Si des erreurs sont détectées, le fournisseur de tâches crée une instance d’élément de tâche. Cette instance crée le marqueur de texte que l’environnement utilise en tant qu’un marqueur d’erreur dans l’affichage de texte.

## <a name="see-also"></a>Voir aussi
- [Utiliser des marqueurs de texte avec l’API héritée](../extensibility/using-text-markers-with-the-legacy-api.md)
- [Guide pratique pour Ajouter des marqueurs de texte standard](../extensibility/how-to-add-standard-text-markers.md)
- [Guide pratique pour Créer des marqueurs de texte personnalisé](../extensibility/how-to-create-custom-text-markers.md)
- [Guide pratique pour Utiliser des marqueurs de texte](../extensibility/how-to-use-text-markers.md)
