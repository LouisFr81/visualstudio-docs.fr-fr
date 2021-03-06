---
title: Impossible d’assigner à 'this' | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f47778075b0395e4f0791d8f485188d40fab87a4
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344172"
---
# <a name="cannot-assign-to-this"></a>Impossible d'affecter à 'this'
Vous avez tenté d’affecter une valeur à **cela**. **Cela** est un [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] mot clé qui fait référence à un :

- l’objet en cours d’exécution une méthode,

- l’objet global si aucune méthode actuel (ou la méthode n’appartient pas à tout autre objet).

Une méthode est un [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] fonction est appelée via un objet. À l’intérieur d’une méthode, le **cela** mot clé est une référence à l’objet de la méthode a été appelée par le biais (ce qui se trouve l’objet créé en appelant le constructeur de classe avec le **nouveau** opérateur).

À l’intérieur d’une méthode, vous pouvez utiliser **cela** pour faire référence à l’objet en cours, mais vous ne pouvez pas attribuer une nouvelle valeur à **cela**.

## <a name="to-correct-this-error"></a>Pour corriger cette erreur

- N’essayez pas d’affecter à **cela**. Pour accéder à une propriété ou méthode d’un objet instancié, utilisez l’opérateur point (par exemple, **circle.radius**).

  > [!NOTE]
  > Vous ne pouvez pas nommer une variable créée par l’utilisateur **cela**; il s’agit une [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] mot réservé.

## <a name="see-also"></a>Voir aussi

- [Instruction this](../../javascript/reference/this-statement-javascript.md)
- [Résolution des problèmes liés aux scripts](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)