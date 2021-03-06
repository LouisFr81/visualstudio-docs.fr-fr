---
title: Ajout de commutateurs de ligne de commande | Microsoft Docs
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
- command-line switches, adding
- command-line switches, retrieving
- IVsAppCommandLine::GetOption method
- command line, switches
ms.assetid: 8bbbd87e-76fe-4fb5-8ef9-65f5e31967cf
caps.latest.revision: 22
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5034e6bcb5aa878c16dbf9dadf478d68276c4fac
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51748272"
---
# <a name="adding-command-line-switches"></a>Ajout de commutateurs de ligne de commande
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez ajouter des commutateurs de ligne de commande qui s’appliquent à votre VSPackage lors de l’exécution de devenv.exe. Utilisez <xref:Microsoft.VisualStudio.Shell.ProvideAppCommandLineAttribute> pour déclarer le nom du commutateur et ses propriétés. Dans cet exemple, le commutateur MySwitch est ajouté pour une sous-classe de VSPackage nommé **AddCommandSwitchPackage** avec aucun argument et le VSPackage chargé automatiquement.  
  
```csharp  
[ProvideAppCommandLine("MySwitch", typeof(AddCommandSwitchPackage), Arguments = "0", DemandLoad = 1)]  
```  
  
 Les paramètres nommés sont affichés dans le tableau suivant  
  
 Arguments  
 Le nombre d’arguments pour le commutateur. Peut être « * », ou une liste d’arguments.  
  
 DemandLoad  
 Charger le VSPackage automatiquement si la valeur est 1, sinon la valeur 0.  
  
 HelpString  
 La chaîne ou une ressource ID d’aide de la chaîne à afficher avec **devenv / ?**.  
  
 Name  
 Le commutateur.  
  
 PackageGuid  
 Le GUID du package.  
  
 La première valeur d’Arguments est généralement 0 ou 1. Une valeur de ' *' peut être utilisé pour indiquer que le reste entier de la ligne de commande est l’argument. Il se peut que cela peut être utile pour déboguer les scénarios où un utilisateur doit passer dans une chaîne de commande de débogueur.  
  
 La valeur de DemandLoad est soit `true` (1) ou `false` (0) indique que le VSPackage doit être chargé automatiquement.  
  
 La valeur HelpString est l’ID de ressource de la chaîne qui apparaît dans le devenv / ? Affichage de l’aide. Cette valeur doit être sous la forme « #nnn » où nnn est un entier. La valeur de chaîne dans le fichier de ressources doit se terminer par un caractère de nouvelle ligne.  
  
 La valeur de nom est le nom du commutateur.  
  
 La valeur PackageGuid est le GUID du package qui implémente ce commutateur. L’IDE utilise ce GUID pour trouver le VSPackage dans le Registre à laquelle s’applique le commutateur de ligne de commande.  
  
## <a name="retrieving-command-line-switches"></a>Récupération des commutateurs de ligne de commande  
 Lors du chargement de votre package, vous pouvez récupérer les commutateurs de ligne de commande en effectuant les étapes suivantes.  
  
1. Dans votre package Visual Studio <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> implémentation, appelez `QueryService` sur <xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine> pour obtenir le <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine> interface.  
  
2. Appelez <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine.GetOption%2A> pour récupérer les commutateurs de ligne de commande que l’utilisateur a entré.  
  
   Le code suivant montre comment déterminer si le commutateur de ligne de commande MySwitch a été entré par l’utilisateur :  
  
```csharp  
IVsAppCommandLine cmdline = (IVsAppCommandLine)GetService(typeof(SVsAppCommandLine));  
  
int isPresent = 0;  
string optionValue = "";  
  
cmdline.GetOption("MySwitch", out isPresent, out optionValue);  
```  
  
 Il vous incombe de vérifier vos commutateurs de ligne de commande chaque fois que votre package est chargé.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 [Commutateurs de la ligne de commande Devenv](../ide/reference/devenv-command-line-switches.md)   
 [Utilitaire CreatePkgDef](../extensibility/internals/createpkgdef-utility.md)   
 [Fichiers .Pkgdef](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)

