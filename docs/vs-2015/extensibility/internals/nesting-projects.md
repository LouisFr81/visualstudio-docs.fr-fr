---
title: Imbriquer des projets | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project nesting
- nested projects
- projects [Visual Studio SDK], child projects
- projects [Visual Studio SDK], nesting
ms.assetid: 12cce037-9840-4761-845e-5abd5fb317b0
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b4ccf51dd492a32990718ffe84bfe78cd736a42c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51805202"
---
# <a name="nesting-projects"></a>Imbriquer des projets
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Les développeurs d’applications entreprise qui utilisent votre Package VS peuvent regrouper facilement des types de projets dans similaires [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] à l’aide de *l’imbrication de projet*. Par exemple, le projet de modèle pour l’entreprise utilise des projets imbriqués pour grouper des projets en catégories. Projets de façade Business, l’interface utilisateur Web projets et ainsi de suite sont regroupés dans une catégorie.  
  
 Dans ce scénario, il n’existe aucune limite au nombre de projets, que le développeur peut imbriquer sous chaque projet parent, bien que le développeur peut fournir par programmation les limites. Ce type de regroupement peut également être effectué récursive, auquel cas les projets du même type comme un projet enfant peuvent être imbriqués sous l’enfant à devenir un sous-projet de l’enfant, qui est un sous-projet du parent.  
  
 Imbrication de projet n’est pas partie intégrante du [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Vous devez écrire le code pour activer l’imbrication et un sous-projet imbrication dans des projets enfants. Le projet parent est un VSPackage spéciale, ou un type de projet, créé et inscrit avec son propre GUID qui inclut le code qui est requis pour implémenter l’imbrication de projet.  
  
 Vous trouverez un exemple de projets imbriqués dans l’exemple de projet Example.Nested c#.  
  
## <a name="nested-projects-example"></a>Exemple de projets imbriqués  
 ![Imbriqué des projets Solution](../../extensibility/internals/media/vsnestedprojects.gif "vsNestedProjects")  
Exemple de projets imbriqués  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : implémenter des projets imbriqués](../../extensibility/internals/how-to-implement-nested-projects.md)   
 [Considérations pour décharger et recharger les projets imbriqués](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)   
 [Prise en charge de l’Assistant pour les projets imbriqués](../../extensibility/internals/wizard-support-for-nested-projects.md)   
 [L’inscription de projet et modèles d’élément](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Mise en œuvre de la gestion des commandes pour les projets imbriqués](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)   
 [Filtrage de la boîte de dialogue AddItem pour les projets imbriqués](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)   
 [Liste de vérification : Créer de nouveaux Types de projet](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Paramètres de contexte](../../extensibility/internals/context-parameters.md)   
 [Fichier Assistant (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)

