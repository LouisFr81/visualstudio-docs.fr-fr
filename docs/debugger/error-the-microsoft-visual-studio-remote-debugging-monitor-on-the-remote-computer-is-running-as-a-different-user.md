---
title: 'Erreur : Microsoft Visual Studio Remote Debugging Monitor sur l’ordinateur distant s’exécute avec un utilisateur différent'
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 513d05149ca52e1d2ec1ca057cca722cef097bd1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55034845"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Erreur : Microsoft Visual Studio Remote Debugging Monitor sur l’ordinateur distant s’exécute avec un utilisateur différent
Si vous essayez d'effectuer un débogage distant, vous risquez de recevoir ce message d'erreur :  
  
 Microsoft Visual Studio Remote Debugging Monitor sur l'ordinateur distant s'exécute avec un utilisateur différent.  
  
## <a name="cause"></a>Cause  
 Ce message se produit lorsque vous déboguez en mode Aucune authentification et l'utilisateur qui a démarré msvsmon n'est pas l'utilisateur qui exécute Visual Studio.  
  
## <a name="solution"></a>Solution  
 La solution la plus sûre et la mieux adaptée consiste à exécuter Remote Debugging Monitor (msvsmon.exe) sous le même compte d'utilisateur que Visual Studio. Si vous ne pouvez pas le faire, vous pouvez exécuter Remote Debugging Monitor sous l’autre compte avec l’option **Permettre à tous les utilisateurs de déboguer** sélectionnée dans la boîte de dialogue **Options** de Remote Debugging Monitor.  
  
> [!CAUTION]
>  Accorder à d'autres utilisateurs l'autorisation de se connecter implique l'éventualité d'une connexion accidentelle à la session de débogage distant incorrecte. Le débogage exécuté en mode **Aucune authentification** n’est jamais sécurisé et doit être utilisé avec précaution.
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs de débogage à distance et dépannage](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)