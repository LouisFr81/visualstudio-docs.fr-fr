---
title: Prise en charge du contrôle de code Source | Microsoft Docs
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
- source control [Visual Studio SDK], supporting
ms.assetid: 567acde3-354e-4f39-8d99-0ef86c103396
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8310a18d9390858256067ba8dd16b61129b819a6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51746324"
---
# <a name="supporting-source-control"></a>Prise en charge du contrôle de code source
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] prend en charge les extractions de fichiers, des archivages et autres opérations de contrôle de source de votre projet ou l’éditeur. Comme un client de contrôle de code source, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] est conçu pour interagir avec un package de contrôle de code source, tel que [!INCLUDE[vsvss](../../includes/vsvss-md.md)], qui fournit l’archivage, le contrôle de version et des fonctionnalités de contrôle pour un ensemble de fichiers définis dynamiquement.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Modèle des packages de contrôle de code source](../../extensibility/internals/model-for-source-control-packages.md)  
 Décrit les interfaces d’un type de projet doit implémenter pour prendre en charge le contrôle de code source.  
  
 [Décisions de conception](../../extensibility/internals/source-control-design-decisions.md)  
 Fournit des questions dont les réponses modifier la façon dont vous implémentez un type de projet.  
  
 [Détails de la configuration](../../extensibility/internals/source-control-configuration-details.md)  
 Décrit comment la prise en charge du contrôle de code source change l’implémentation d’un type de projet.  
  
 [Instructions supplémentaires pour les projets et les éditeurs](../../extensibility/internals/additional-source-control-guidelines-for-projects-and-editors.md)  
 Présente les meilleures pratiques pour les éditeurs et les types de projets.  
  
 [Détails du runtime](../../extensibility/internals/source-control-runtime-details.md)  
 Décrit comment enregistrer un projet lorsqu’un utilisateur l’ajoute à un système de contrôle de code source.  
  
## <a name="reference"></a>Référence  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>  
 Indique à l’environnement ou d’un package de contrôle de code source qu’un fichier est sur le point d’être modifié en mémoire ou enregistré.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>  
 Permet aux projets et hiérarchies pour s’enregistrer avec le contrôle de code source et obtenir des informations sur l’état de contrôle de code source.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>  
 Implémenté dans un système de projet pour fournir un contrôle de code source pour les fichiers de projet et des éléments de projet.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>  
 Utilisé par les projets pour demander à l’environnement pour l’autorisation d’ajouter, supprimer ou renommer un fichier ou répertoire dans une solution.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>  
 Avertit les clients des modifications apportées aux fichiers de projet ou aux répertoires.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Types de projets](../../extensibility/internals/project-types.md)  
 Fournit une vue d’ensemble des projets en tant que blocs de construction de base de la [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] l’environnement de développement intégré (IDE). Liens sont fournis vers des rubriques supplémentaires qui expliquent comment projets de contrôle de génération et compilation du code.

