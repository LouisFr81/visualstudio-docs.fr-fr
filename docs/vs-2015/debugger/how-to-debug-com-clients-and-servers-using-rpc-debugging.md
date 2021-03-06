---
title: 'Comment : déboguer des Clients COM et des serveurs à l’aide du débogage RPC | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.com
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- RPC (Remote Procedure Call), debugging COM clients and servers
- COM, debugging
- RPC (Remote Procedure Call)
- RPC (Remote Procedure Call), debugging
- COM clients, debugging
- COM servers, debugging
- out-of-process remote procedure call debugging
- remote debugging, RPC (Remote Procedure Call)
- in-process remote procedure call debugging
ms.assetid: 3e8526c8-43b5-4b87-8e0d-b22c24f0a3ea
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78a4c85d24ea382e5946000ac2225588c5deceed
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51786795"
---
# <a name="how-to-debug-com-clients-and-servers-using-rpc-debugging"></a>Comment : déboguer des clients COM et des serveurs à l'aide du débogage RPC
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser le débogage RPC pour déboguer des applications client/serveur COM. Vous devez activer le débogage RPC pour l'utiliser. Lorsque le débogage RPC est activé, si vous effectuez un pas à pas détaillé dans l'appel serveur à partir du client, le débogueur est attaché au serveur, ce qui permet de déboguer son code. Une fois que le débogueur est attaché, vous pouvez utiliser toutes ses fonctionnalités avec les processus client et serveur.  
  
### <a name="to-enable-rpc-debugging"></a>Pour activer le débogage RPC  
  
1.  Dans le menu **Outils**, cliquez sur **Options**.  
  
2.  Dans le **Options** boîte de dialogue, cliquez sur le **débogage** dossier.  
  
3.  Cliquez sur le **natif** page.  
  
4.  Sélectionnez le **débogage RPC** case à cocher.  
  
    > [!NOTE]
    >  Pour déboguer des appels RPC, vous devez posséder les privilèges Administrateur ou Utilisateur avec pouvoirs.  
  
    > [!NOTE]
    >  Le processus d'exécution pas à pas RPC sur un serveur distant qui exécute Microsoft Windows Vista fonctionne uniquement si un débogueur natif est attaché au serveur distant. Sinon, l'appel RPC échoue sans message d'erreur. Sinon, l'appel RPC s'effectue, mais le processus d'exécution pas à pas dans l'appel RPC ne fonctionne pas.  
  
## <a name="see-also"></a>Voir aussi  
 [Serveur COM débogage et conteneurs](../debugger/com-server-and-container-debugging.md)   
 [Débogage dans Visual Studio](../debugger/debugging-in-visual-studio.md)



