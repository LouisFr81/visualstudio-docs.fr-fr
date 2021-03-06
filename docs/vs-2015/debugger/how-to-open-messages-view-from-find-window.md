---
title: 'Comment : ouvrir la vue Messages à partir de la fenêtre Rechercher | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Messages View in Spy++, opening
- opening Messages View in Spy++
ms.assetid: 601a193e-432a-417b-9406-6fec9e401264
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64d32064ef20b1f7e188624a5a91ffd231b82b66
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51801249"
---
# <a name="how-to-open-messages-view-from-find-window"></a>Comment : ouvrir la vue Messages à partir de Rechercher une fenêtre
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Il peut s’avérer pratique d’utiliser le **rechercher une fenêtre** boîte de dialogue pour sélectionner une fenêtre cible, puis ouvrez un affichage de Messages de cette fenêtre.  
  
### <a name="to-open-a-messages-view-window-using-the-find-window-dialog-box"></a>Pour ouvrir une fenêtre d’affichage de Messages à l’aide de la boîte de dialogue Rechercher une fenêtre  
  
1.  Réorganisez vos fenêtres afin que Spy ++ et la fenêtre cible sont visibles.  
  
2.  À partir de la **Spy** menu, choisissez **rechercher une fenêtre**.  
  
     Le [boîte de dialogue Rechercher une fenêtre](../debugger/find-window-dialog-box.md) s’ouvre.  
  
3.  À partir de la **Windows** onglet, faites glisser le **outil recherche** sur la fenêtre cible. Lorsque vous faites glisser l’outil, le **rechercher une fenêtre** boîte de dialogue affiche des détails sur la fenêtre sélectionnée.  
  
     – ou –  
  
     Si vous avez le handle de la fenêtre que vous souhaitez examiner (par exemple, copié à partir du débogueur), vous pouvez la taper dans le **gérer** zone de texte.  
  
4.  Sous **afficher**, sélectionnez **Messages**.  
  
5.  Appuyez sur **OK**.  
  
     Une valeur vide [vue Messages](../debugger/messages-view.md) fenêtre s’ouvre et un **Messages** menu est ajouté à la barre d’outils Spy ++.  
  
6.  À partir de la **Messages** menu, choisissez **des Options de journalisation**.  
  
     Le [la boîte de dialogue Options des messages](../debugger/message-options-dialog-box.md) s’ouvre.  
  
7.  Sélectionnez les options pour les messages que vous souhaitez afficher.  
  
8.  Appuyez sur **OK** pour commencer la journalisation des messages.  
  
     Selon les options sélectionnées, messages commencent le streaming dans la fenêtre d’affichage de Messages active.  
  
9. Lorsque vous avez suffisamment de messages, choisissez **Stop Logging** à partir de la **Messages** menu.



