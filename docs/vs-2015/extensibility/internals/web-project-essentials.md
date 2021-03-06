---
title: Web Essentials de projet | Microsoft Docs
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
- web projects, essentials
ms.assetid: ca2f4e43-322c-4431-8680-52da846940bc
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6343860465cc5c8acdefb80a39eac3c33087a36d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51748844"
---
# <a name="web-project-essentials"></a>Éléments fondamentaux de projet web
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Projets Web créent des applications Web. Vous pouvez utiliser un projet Web pour créer une application Web qui comporte les pages Web actives. Une page Web active a au code côté serveur qui restitue la page Web à la demande.  
  
 À l’aide de langages de programmation traditionnels, tels que [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ou [!INCLUDE[csprcs](../../includes/csprcs-md.md)], vous pouvez créer des pages Web actives pour collecter et traiter les informations à partir d’un utilisateur, stockez-le dans une base de données et ainsi de suite.  
  
-   Le modèle code-behind associe les fichiers de code source dépendant Web pages .aspx d’extension de fichier ou .asmx. Par exemple, hello.aspx peut avoir le hello.aspx.cs de fichier de code source dépendant.  
  
-   Le code côté serveur associé à une page Web active est compilé dans un fichier exécutable qui se trouve dans le dossier "/ bin" site Web.  
  
-   Fichiers de code source supplémentaires, tels que les classes d’assistance qui ne sont pas associés à une page Web spécifique, se trouvent dans le dossier/App_Code du site Web.  
  
    -   Un projet de site Web (WSP) génère un fichier exécutable pour chaque page Web active. Fichiers exécutables supplémentaires sont générés à partir des fichiers de code source dans le dossier/App_Code.  
  
    -   Un projet d’application Web (WAP) produit un seul fichier exécutable qui combine le code pour toutes les pages Web actives, ainsi que tous les fichiers source dans le dossier/App_Code.  
  
-   Le fichier de solution pour un projet Web se trouve séparément à partir du site Web lui-même. Par défaut, les fichiers de solution se trouvent dans \Documents and Settings\\*Votre_compte*\My Documents\\*\<Visual Studio ### >* \Projects\\ *Votresiteweb*.  
  
    > [!NOTE]
    >  Si vous souhaitez conserver le fichier de solution avec le site Web, simplement déplacez-la à cet endroit et le rouvrir.  
  
-   Si vous ouvrez un site Web qui n’a aucun fichier de solution dans Visual Studio, un nouveau fichier de solution est automatiquement généré pour elle.  
  
-   Il n’existe aucun fichier de projet pour les projets Web. Informations de projet sont stockées dans le fichier solution, le fichier web.config et ailleurs.  
  
-   Ajouter automatiquement des propriétés globales à un projet Web crée un fichier de stockage dans le dossier de solution du projet Web.  
  
-   Une page Web active peut être associée à un langage de programmation côté serveur à l’aide de la directive de Page ou le \<script runat = « server » > balise.  
  
-   En outre, les pages Web peuvent avoir n’importe quel nombre de blocs de script côté client écrit dans n’importe quel langage de script.  
  
-   Un système de projet de site Web est implémenté en ajoutant des modèles de projet et d’élément et d’inscription à la [!INCLUDE[vwprvw](../../includes/vwprvw-md.md)] projet.  
  
-   Un système de proxy d’application Web est implémenté comme un sous-type de projet, également appelé une version de projet. Le [!INCLUDE[vwprvw](../../includes/vwprvw-md.md)] projet est versionné par le sous-type WAP pour créer le système WAP. Pour plus d’informations sur les sous-types de projet, consultez [sous-types de projet](../../extensibility/internals/project-subtypes.md).  
  
-   Une page Web active combine HTML avec un langage de programmation côté serveur. Le langage côté serveur est appelé le langage contenu. Pour prendre en charge un langage de relation contenant-contenu, le système de projet Web doit implémenter le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> famille d’interfaces.  
  
    -   Pour prendre en charge le langage contenu dans un éditeur, le service de langage HTML doit différer l’affichage de code de langue de relation contenant-contenu à un service de langage contenu.  
  
    -   Marqueurs d’erreur (tildes rouges) doivent toujours être créés dans la mémoire tampon principale de l’éditeur de code.  
  
## <a name="see-also"></a>Voir aussi  
 [Projets Web](../../extensibility/internals/web-projects.md)

