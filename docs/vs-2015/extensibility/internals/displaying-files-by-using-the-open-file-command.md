---
title: Afficher les fichiers à l’aide de la commande Ouvrir un fichier | Microsoft Docs
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
- project types, supporting Open File command
- Open File command
- persistence, supporting Open File command
ms.assetid: 4fff0576-b2f3-4f17-9769-930f926f273c
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1f1a2ca2b87cadf118c83501bbd6b6bf78af761a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51727282"
---
# <a name="displaying-files-by-using-the-open-file-command"></a>Affichage de fichiers à l’aide de la commande Ouvrir un fichier
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Les étapes suivantes décrivent comment l’IDE gère le **ouvrir un fichier** commande, qui est disponible sur le **fichier** menu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Les étapes décrivent également la façon dont les projets doivent répondre aux appels issus de cette commande.  
  
 Lorsqu’un utilisateur clique sur le **ouvrir un fichier** commande sur le **fichier** menu et sélectionne un fichier à partir de la **ouvrir un fichier** boîte de dialogue, la processus suivante se produit.  
  
1.  À l’aide de la table de document en cours d’exécution, l’IDE détermine si le fichier est déjà ouvert dans un projet.  
  
    -   Si le fichier est ouvert, l’IDE resurfaces la fenêtre.  
  
    -   Si le fichier n’est pas ouvert, l’IDE appelle <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> pour chaque projet afin de déterminer quel projet peut ouvrir le fichier de requête.  
  
        > [!NOTE]
        >  Dans votre implémentation de projet de <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>, fournir une valeur de priorité qui indique le niveau auquel votre projet s’ouvre le fichier. Les valeurs de priorité sont fournies dans le <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> énumération.  
  
2.  Chaque projet répond avec un niveau de priorité qui indique l’importance qu’il place sur en cours du projet à ouvrir le fichier.  
  
3.  L’IDE utilise les critères suivants pour déterminer quel projet s’ouvre le fichier :  
  
    -   Le projet qui répond avec la priorité la plus élevée (DP_Intrinsic) s’ouvre le fichier. Si plusieurs projets répond avec cette priorité, le premier projet répondre ouvre le fichier.  
  
    -   Si aucun répond de projet avec la priorité la plus élevée (DP_Intrinsic), mais tous les projets répondre avec la priorité de même, avec moins, le projet actif ouvre le fichier. Si aucun projet n’est active, le premier projet répondre ouvre le fichier.  
  
    -   Si aucun projet ne réclame la propriété du fichier (DP_Unsupported), le projet fichiers divers ouvre le fichier.  
  
         Si une instance du projet fichiers divers est créée, le projet est toujours répond avec la valeur DP_CanAddAsExternal. Cette valeur indique que le projet peut ouvrir le fichier. Ce projet est utilisé pour héberger les fichiers ouverts ne sont pas dans n’importe quel autre projet. La liste des éléments de ce projet n’est pas rendu persistant ; ce projet est visible dans **l’Explorateur de solutions** uniquement lorsqu’il est utilisé pour ouvrir un fichier.  
  
         Si le projet fichiers divers n’indique pas qu’il peut ouvrir le fichier, une instance du projet n’a pas été créée. Dans ce cas, l’IDE crée une instance du projet fichiers divers et indique le projet pour ouvrir le fichier.  
  
4.  Dès que l’IDE détermine quel projet s’ouvre le fichier, elle appelle le <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> méthode sur ce projet.  
  
5.  Le projet a ensuite la possibilité d’ouvrir le fichier à l’aide d’un éditeur spécifique au projet ou un éditeur standard. Pour plus d’informations, consultez [Comment : ouvrir éditeurs spécifiques du projet](../../extensibility/how-to-open-project-specific-editors.md) et [Comment : ouvrir des éditeurs Standard](../../extensibility/how-to-open-standard-editors.md), respectivement.  
  
## <a name="see-also"></a>Voir aussi  
 [Afficher les fichiers à l’aide de l’ouvrir avec la commande](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)   
 [Ouvrir et enregistrer des éléments de projet](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Comment : ouvrir des éditeurs spécifiques du projet](../../extensibility/how-to-open-project-specific-editors.md)   
 [Guide pratique pour ouvrir des éditeurs standard](../../extensibility/how-to-open-standard-editors.md)

