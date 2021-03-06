---
title: Conseils pour le débogage de Threads en Code natif | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1852e2d0b3e773e5be0f3f60ad191056a4af0889
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51775002"
---
# <a name="tips-for-debugging-threads-in-native-code"></a>Conseils pour le débogage de threads en code natif
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Voici quelques conseils que vous utiles pour le débogage de threads en code natif :  
  
-   Vous pouvez afficher le contenu du bloc d’informations du Thread en tapant `@TIB` dans le **espion** fenêtre ou **Espion express** boîte de dialogue.  
  
-   Vous pouvez afficher le dernier code d’erreur pour le thread actuel en entrant `@Err` dans le **espion** fenêtre ou **Espion express** boîte de dialogue.  
  
-   Vous pouvez utiliser les fonctions des bibliothèques Runtime C pour déboguer une application multithread. Pour plus d’informations, consultez [_malloc_dbg](http://msdn.microsoft.com/library/c97eca51-140b-4461-8bd2-28965b49ecdb).  
  
## <a name="see-also"></a>Voir aussi  
 [Déboguer les Applications multithread](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Débogage du code natif](../debugger/debugging-native-code.md)



