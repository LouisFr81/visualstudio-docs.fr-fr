---
title: 'Erreur : Ordinateur distant n’a pas pu lancer les communications DCOM | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.unmarshal_callback_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2612542a50d87b2fc8de50bf50955160c0b6f55
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54990821"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>Erreur : L’ordinateur distant n’a pas pu lancer les communications DCOM
Une erreur DCOM s'est produite lorsque l'ordinateur distant a tenté de communiquer avec l'ordinateur local. L'ordinateur local est l'ordinateur qui  
  
 exécute Visual Studio. Cette erreur peut se produire pour plusieurs raisons :  
  
-   L'ordinateur local a un pare-feu activé.  
  
-   L'authentification Windows de l'ordinateur distant vers l'ordinateur local ne fonctionne pas.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Si l’ordinateur local a un pare-feu Windows est activé, consultez [le débogage à distance](../debugger/remote-debugging.md) pour obtenir des instructions sur la façon de configurer le pare-feu pour le débogage local.  
  
2.  Testez l'authentification Windows en essayant d'ouvrir un partage de fichiers sur l'ordinateur local du serveur distant.  
  
3.  Pour restaurer l'authentification Windows, tentez de redémarrer les deux ordinateurs. Vérifiez si les journaux des événements de l'ordinateur local ou distant contiennent des erreurs Kerberos et contactez les administrateurs de domaines pour les problèmes connus.  
  
## <a name="see-also"></a>Voir aussi  
 [Remote Debugging](../debugger/remote-debugging.md)