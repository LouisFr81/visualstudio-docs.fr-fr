---
title: 'Comment : incrémenter automatiquement la publication ClickOnce Version | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: ac5b4e67c0bbebba7586715e4ba491bf11bacc4a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49300220"
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>Comment : incrémenter automatiquement la version de publication ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Lors de la publication une [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] application, en modifiant le `Publish Version` propriété entraîne l’application à publier une mise à jour. Par défaut, Visual Studio incrémente automatiquement le `Revision` numéro de la `Publish Version` chaque fois que vous publiez l’application.  
  
 Vous pouvez désactiver ce comportement sur le **publier** page de la **Concepteur de projet**.  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>Pour désactiver la Version de publication à incrémentation automatique  
  
1.  Après avoir sélectionné un projet dans l’ **Explorateur de solutions**, dans le menu **Projet** , cliquez sur **Propriétés**.  
  
2.  Cliquez sur le **publier** onglet.  
  
3.  Dans le **Publish Version** section, désactivez le **incrémenter automatiquement la révision avec chaque version** case à cocher.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour définir la version de publication ClickOnce](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Publication d’applications ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Guide pratique pour publier une application ClickOnce à l’aide de l’Assistant Publication](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



