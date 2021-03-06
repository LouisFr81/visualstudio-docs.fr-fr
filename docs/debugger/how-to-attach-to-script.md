---
title: 'Comment : attacher à un Script | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- script debugging, attaching to script
- script, attaching to
- processes, attaching to script
- remote debugging, attaching to script
ms.assetid: 82013e9a-ef53-4fd2-b451-a6891cdc6307
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05d2a2cbd3cfe59b1d110fdd8b0b7c5fd042d25c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54937325"
---
# <a name="how-to-attach-to-script"></a>Comment : attacher à un script
Cette rubrique explique comment attacher manuellement le débogueur Visual Studio à un fichier de script pour le débogage.  
  
### <a name="to-attach-to-a-running-process"></a>Pour établir un attachement à un processus en cours d'exécution  
  
1. Dans le menu **Débogage** , sélectionnez **Attacher au processus**. Si aucun projet n’est ouvert, cliquez sur **Attacher au processus** dans le menu **Outils**.  
  
2. Dans la boîte de dialogue **Attacher au processus**, recherchez le processus de script à attacher dans la liste **Processus disponibles**. Vous pouvez identifier les processus de script dans la colonne **Type**.  
  
   1.  Si le processus que vous souhaitez déboguer est en cours d'exécution sur un autre ordinateur, sélectionnez d'abord l'ordinateur distant.
  
   2.  Si le processus s’exécute sous un compte d’utilisateur différent, cochez la case **Afficher les processus de tous les utilisateurs** .  
  
   3.  Si vous êtes connecté via une **Connexion Bureau à distance**, cochez la case **Afficher les processus de toutes les sessions**.  
  
3. Cliquez sur le processus que vous voulez attacher.  
  
4. Dans le **attacher à** zone, vous devez voir **code de Script** ou **automatique : Code de script**. Si un élément différent est affiché, suivez ces étapes :  
  
   1.  Cliquez sur **Sélectionner**.  
  
   2.  Dans la boîte de dialogue **Sélectionner le type de code**, sélectionnez **Script** sous **Déboguer ces types de codes**.  
  
   3.  Cliquez sur **OK**.  
  
5. Cliquez sur **Attacher**.  
  
    Vous pouvez visualiser un avertissement vous indiquant que le débogage de script est désactivé dans Internet Explorer. Si cela se produit, consultez [Avertissement : le débogage de Script est désactivé](../debugger/warning-script-debugging-disabled.md).  
  
   La liste **Processus disponibles** s’affiche automatiquement quand vous ouvrez la boîte de dialogue **Processus** . Les processus peuvent démarrer et s’interrompre en arrière-plan pendant que la boîte de dialogue est ouverte. Le contenu n'est donc pas toujours à jour. Vous pouvez réactualiser la liste à tout moment pour afficher la liste des processus en cours en appuyant sur le bouton **Actualiser**.  
  
   Vous pouvez attacher un débogueur à plusieurs programmes à la fois, mais un seul d’entre eux est actif dans le débogueur à un moment donné. Vous pouvez définir le programme actif dans la barre d'outils Emplacement de débogage. Pour plus d’informations, consultez [Comment : définir le processus actuel](/previous-versions/visualstudio/visual-studio-2010/d5d4sxdw(v=vs.100)).  
  
   Toutes les commandes d’exécution du menu **Déboguer** affectent le programme actif. Vous pouvez interrompre tout programme débogué à partir de la boîte de dialogue processus. Consultez [à l’aide de points d’arrêt](../debugger/using-breakpoints.md).  
  
> [!NOTE]
>  Si vous essayez d'établir un attachement à un processus appartenant à un compte d'utilisateur non fiable, une boîte de dialogue d'avertissement de sécurité s'affiche avec un message de confirmation. Pour plus d’informations, consultez [avertissement de sécurité : l’attachement à un processus appartenant à un utilisateur non fiable peut être dangereux. Si les informations suivantes semblent suspectes ou si vous avez des doutes, n’attachez pas ce processus](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md).  
  
 Dans certains cas, lors du débogage dans une session Terminal Services (Bureau à distance), la liste Processus disponibles n'affiche pas tous les processus disponibles. Dans [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] ou une version ultérieure, si vous exécutez Visual Studio avec un compte d'utilisateur limité, la liste Processus disponibles n'affiche pas les processus qui s'exécutent dans la session 0, qui est utilisée pour les services et les autres processus serveur, notamment w3wp.exe. Vous pouvez résoudre le problème en exécutant Visual Studio sous un compte administrateur ou à partir de la console serveur au lieu d'une session Terminal Services. Si aucune de ces solutions n’est possible, la troisième option consiste à attacher le débogueur au processus en entrant vsjitdebugger.exe -p ProcessId dans la ligne de commande Windows. Vous pouvez déterminer l'ID de processus à l'aide de tlist.exe. Pour obtenir tlist.exe, téléchargez et installez les outils de débogage pour Windows, qui sont disponibles dans le [Centre de développement Windows](/windows-hardware/drivers/dashboard/).  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage de scripts côté client](../debugger/client-side-script-debugging.md)   
 [Attacher à des processus en cours d’exécution](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Avertissement de sécurité : L’attachement à un processus appartenant à un utilisateur non approuvé peut être dangereux. Si les informations suivantes semblent suspectes ou si vous avez des doutes, ne faites pas d’attachement à ce processus](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)   
 [Sécurité du débogueur](../debugger/debugger-security.md)