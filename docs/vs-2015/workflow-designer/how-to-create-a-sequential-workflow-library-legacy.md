---
title: 'Comment : créer une bibliothèque de workflows séquentiels (hérité) | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- sequential workflows, creating library
- workflows, sequential workflow library
- projects, sequential workflow library
- sequential workflow libraries
ms.assetid: 9433ccf3-1eab-4d53-90ff-2e7b2341676c
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1a2f1801392c1edecec2fa26ec35c9d1728bc1c7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194582"
---
# <a name="how-to-create-a-sequential-workflow-library-legacy"></a>Procédure : créer une bibliothèque de workflows séquentiels (héritée)
Suivez ces étapes pour créer un projet de bibliothèque de workflows séquentiels à l'aide du [!INCLUDE[wfd1](../includes/wfd1-md.md)] hérité fourni par [!INCLUDE[vs2010](../includes/vs2010-md.md)]. Utilisez le [!INCLUDE[wfd2](../includes/wfd2-md.md)] hérité lorsque vous devez cibler le [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] ou le [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
### <a name="to-create-a-sequential-workflow-library-project"></a>Pour créer un projet de bibliothèque de workflow séquentiel  
  
1.  Démarrez Visual Studio.  
  
2.  Dans le menu **Fichier**, pointez sur **Nouveau**, puis sélectionnez **Projet**.  
  
     La boîte de dialogue **Nouveau projet** s'affiche.  
  
3.  Sélectionnez le **.NET Framework 3.0** option ou **.NET Framework 3.5** option dans la liste déroulante située en haut de la **nouveau projet** fenêtre pour accéder au concepteur hérité.  
  
    > [!NOTE]
    >  L’option par défaut dans [!INCLUDE[vs2010](../includes/vs2010-md.md)] est **.NET Framework 4**. Cette option permet de créer des applications [!INCLUDE[wf](../includes/wf-md.md)] qui ciblent le [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] et elle n'utilise pas le concepteur hérité.  
  
4.  Dans le **Types de projets** volet, sélectionnez Visual c# ou Visual Basic (sous **autres langages**), puis sélectionnez **Workflow**.  
  
5.  Dans le **modèles** volet, sélectionnez **bibliothèque de flux de travail séquentiel**.  
  
6.  Dans le **nom** , entrez un nom descriptif pour votre projet pour faciliter l’identification.  
  
7.  Dans le **emplacement** , entrez le répertoire dans lequel vous souhaitez enregistrer votre projet, ou cliquez sur **Parcourir** pour naviguer jusqu'à lui.  
  
     Si vous souhaitez un répertoire de solution créé pour le projet, sélectionnez le **créer le répertoire pour la solution** case et entrez un nom dans la **nom de la Solution** boîte.  
  
8.  Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de projets de flux de travail hérités](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Styles de création de flux de travail](http://msdn.microsoft.com/en-us/aacf4ec6-da05-4974-958a-974769dda739)