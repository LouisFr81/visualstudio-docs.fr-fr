---
title: 'Erreur : Débogage n&#39;t Possible car un débogueur du noyau est activé sur le système | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.kernel_dbg_enabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- kernel debugger
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c35910a7682d4e9a6d848f270dd8d6c86e4bd850
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54954148"
---
# <a name="error-debugging-isn39t-possible-because-a-kernel-debugger-is-enabled-on-the-system"></a>Erreur : Débogage n&#39;t Possible car un débogueur du noyau est activé sur le système
Lorsque vous déboguez du code managé, le message d'erreur suivant peut s'afficher :  
  
```cmd
Debugging isn't possible because a kernel debugger is enabled on the system  
```  
  
 Ce message se produit lorsque vous essayez de déboguer du code managé :  
  
- sur un système [!INCLUDE[win7](../debugger/includes/win7_md.md)] ou [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)]qui a été démarré en mode débogage.  
  
- l'application utilise la version CLR CLR 2.0, 3.0, ou 3.5.  
  
## <a name="solution"></a>Solution  
  
#### <a name="to-fix-this-problem"></a>Pour corriger ce problème  
  
- Mettez votre application à niveau pour utiliser la version CLR 4.0 ou 4.5  
  
   - ou -  
  
- Désactivez le débogage du noyau et déboguez dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
   - ou -  
  
- Déboguez à l'aide du débogueur du noyau au lieu de [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
   - ou -  
  
- Dans le débogueur du noyau, désactivez les exceptions en mode utilisateur.  
  
#### <a name="to-disable-kernel-debugging-in-the-current-session"></a>Pour désactiver le débogage du noyau dans la session active  
  
-   À l'invite de commandes, tapez :  
  
    ```cmd
    Kdbgctrl.exe -d  
    ```  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-windows-vista-and-windows-7"></a>Pour désactiver le débogage du noyau pour toutes les sessions (Windows Vista et Windows 7)  
  
1.  À l'invite de commandes, tapez :  
  
    ```cmd
    bcdedit /debug off   
    ```  
  
2.  Redémarrez l'ordinateur.  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-other-windows-operating-systems"></a>Pour désactiver le débogage du noyau pour toutes les sessions (systèmes d'exploitation autres que Windows)  
  
1.  Recherchez le fichier boot.ini sur votre lecteur système (généralement C:\\). Le fichier boot.ini peut être masqué et en lecture seule. Par conséquent, vous devez utiliser la commande suivante pour l'afficher :  
  
    ```cmd
    dir /ASH  
    ```  
  
2.  Ouvrez boot.ini en utilisant le Bloc-notes et supprimez les options suivantes :  
  
    ```cmd
    /debug  
    /debugport  
    /baudrate  
    ```  
  
3.  Redémarrez l'ordinateur.  
  
#### <a name="to-debug-with-the-kernel-debugger"></a>Pour déboguer avec le débogueur du noyau  
  
1.  Si le débogueur du noyau est raccordé, un message s'affiche pour demander si vous souhaitez continuer le débogage. Cliquez sur le bouton pour continuer.  
  
2.  Vous pouvez obtenir une `User break exception(Int 3).`. Dans ce cas, entrez la commande du débogueur du noyau suivante pour poursuivre le débogage :  
  
     `gn`  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité du débogueur](../debugger/debugger-security.md)   
 [Débogage du code managé](../debugger/debugging-managed-code.md)
