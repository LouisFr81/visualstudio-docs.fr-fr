---
title: Désactiver le débogueur juste-à-temps | Microsoft Docs
ms.date: 05/23/18
ms.topic: troubleshooting
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: edd21719348a69926a32bc23007e37d8bb577de9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54983753"
---
# <a name="disable-the-just-in-time-debugger"></a>Désactiver le débogueur juste-à-temps 

La boîte de dialogue peut ouvrir lorsqu’une erreur se produit dans une application en cours d’exécution et empêche la poursuite de l’application. 

Le débogueur juste à temps vous donne la possibilité pour lancer Visual Studio pour déboguer l’erreur. Vous devez avoir [Visual Studio](http://visualstudio.microsoft.com) ou un autre débogueur sélectionné pour afficher des informations détaillées sur l’erreur ou essayez de déboguer. 

Si vous êtes un utilisateur de Visual Studio et que vous souhaitez essayer de déboguer l’erreur, consultez [déboguer à l’aide du débogueur juste à temps](../debugger/debug-using-the-just-in-time-debugger.md). Si vous ne pouvez pas corriger l’erreur ou pour conserver le débogueur juste à temps à partir de l’ouverture, vous pouvez [juste-à-temps de désactiver le débogage à partir de Visual Studio](debug-using-the-just-in-time-debugger.md#BKMK_Enabling). 

Si vous aviez installé Visual Studio, mais n’est plus faire, vous devrez peut-être [juste-à-temps de désactiver le débogage à partir du Registre Windows](debug-using-the-just-in-time-debugger.md#disable-just-in-time-debugging-from-the-windows-registry). 

Si vous n’avez pas installé Visual Studio, vous pouvez empêcher le débogage en désactivant le débogage de script ou le débogage côté serveur juste-à-temps. 

- Si vous tentez d’exécuter une application web, désactiver le débogage de script :
  
  Dans Windows **le panneau de configuration** > **réseau et Internet** > **Options Internet**, sélectionnez **désactiver (débogage de script Internet Explorer)** et **désactiver (autre) de débogage de script**. Les étapes exactes et les paramètres varient selon votre version de Windows et de votre navigateur.
  
  ![Options d’Internet JIT](../debugger/media/jitinternetoptions.png "options JIT internet")
  
- Si vous hébergez une application web ASP.NET dans IIS, désactiver le débogage côté serveur :

  1. Dans le Gestionnaire des services Internet **affichage des fonctionnalités**, sous le **ASP.NET** section, double-cliquez sur **Compilation .NET**, ou sélectionnez-le, puis sélectionnez **ouvrir la fonctionnalité**dans les **Actions** volet. 
  1. Sous **comportement** > **déboguer**, sélectionnez **False**. Les étapes sont différentes dans les versions antérieures d’IIS.

Une fois que vous désactivez le débogage juste-à-temps, l’application peut être en mesure de gérer l’erreur et s’exécuter normalement. 

Si l’application a toujours une erreur non gérée, vous pouvez voir un message d’erreur ou l’application peut se bloquer ou de blocage. L’application ne s’exécute normalement jusqu'à ce que l’erreur est corrigée. Vous pouvez tenter de contacter le propriétaire de l’application et demandez-lui de résoudre le problème.
