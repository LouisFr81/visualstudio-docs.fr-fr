---
title: Mise en œuvre de la gestion des commandes pour imbriqués projets | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a75c6edcc084c8ec7c6942e011af9978a961c83
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606532"
---
# <a name="implementing-command-handling-for-nested-projects"></a>Implémentation de la gestion des commandes pour les projets imbriqués
L’IDE peut transmettre des commandes qui sont transmises via le <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> et <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfaces pour les projets imbriqués ou des projets parents peuvent filtrer ou substituer les commandes.

> [!NOTE]
>  Seules les commandes habituellement gérées par le projet parent peuvent être filtrés. Commandes telles que **Build** et **déployer** qui sont gérés par l’IDE ne peuvent pas être filtré.

 Les étapes suivantes décrivent le processus d’implémentation de la gestion des commandes.

## <a name="procedures"></a>Procédures

#### <a name="to-implement-command-handling"></a>Pour implémenter la gestion des commandes

1. Lorsque l’utilisateur sélectionne un nœud ou un projet imbriqué dans un projet imbriqué :

   1. Les appels de l’IDE le <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> (méthode).

      — ou —

   2. Si la commande avait été créée dans une fenêtre de hiérarchie, par exemple une commande de menu contextuel dans l’Explorateur de solutions, l’IDE appelle le <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> méthode sur les parents du projet.

2. Le projet parent peut examiner les paramètres à passer à `QueryStatus`, tel que `pguidCmdGroup` et `prgCmds`, afin de déterminer si le projet parent doit filtrer les commandes. Si le projet parent est implémenté pour filtrer les commandes, il doit définir :

   ```
   prgCmds[0].cmdf = OLECMDF_SUPPORTED;
   // make sure it is disabled
   prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;
   ```

    Le projet parent doit retourner `S_OK`.

    Si le projet parent ne filtre pas la commande, elle doit simplement retourner `S_OK`. Dans ce cas, l’IDE achemine automatiquement la commande au projet enfant.

    Le projet parent n’a pas à acheminer la commande au projet enfant. L’IDE exécute cette tâche...

## <a name="see-also"></a>Voir aussi
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>
- [Commandes, menus et barres d’outils](../../extensibility/internals/commands-menus-and-toolbars.md)
- [Imbriquer des projets](../../extensibility/internals/nesting-projects.md)