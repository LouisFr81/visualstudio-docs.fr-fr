---
title: Débogage F# | Microsoft Docs
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
- Debugging [F#]
- F#, debugging
ms.assetid: 20bcd51c-2d06-4281-9a1e-ef2b91d1a779
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4cfe65671e0f3d9b3e4702c9f08740c6694286ce
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51734809"
---
# <a name="debugging-f"></a>Débogage de F# #
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le débogage de F# est semblable au débogage de tout langage managé, à quelques exceptions près :  
  
-   Le **automatique** fenêtre ne s’affiche pas F# variables.  
  
-   L'opération Modifier & Continuer n'est pas prise en charge pour F# La modification du code F# pendant une session de débogage est possible mais doit être évitée. Dans la mesure où les modifications du code ne sont pas appliquées pendant la session de débogage, le fait de modifier le code F# lors du débogage provoquera une incompatibilité entre le code source et le code débogué.  
  
-   Le débogueur ne reconnaît pas les expressions F#. Pour entrer une expression dans une fenêtre du débogueur ou une boîte de dialogue lors du débogage de F#, vous devez traduire l'expression en syntaxe C#. Lorsque vous traduisez une expression F# en syntaxe C#, assurez-vous que C# utilise == comme opérateur de comparaison d'égalité et que F# utilise un signe = unique.  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage du code managé](../debugger/debugging-managed-code.md)



