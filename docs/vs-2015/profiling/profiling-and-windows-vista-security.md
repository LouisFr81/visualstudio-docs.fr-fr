---
title: Profilage et sécurité Windows Vista | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 736e7a04813a6c56d6cab6d1886171e321d583cb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47507757"
---
# <a name="profiling-and-windows-vista-security"></a>Profilage et sécurité Windows Vista
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [profilage et sécurité de Windows Vista](https://docs.microsoft.com/visualstudio/profiling/profiling-and-windows-vista-security).  
  
Selon les paramètres d’autorisation d’accès utilisateur de [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)] mis à disposition par l’administrateur d’un ordinateur, un utilisateur individuel peut disposer de l’autorisation de sécurité pour profiler un processus sur cet ordinateur. Les exemples suivants montrent les différences possibles entre les utilisateurs :  
  
-   Certains utilisateurs peuvent accéder à des fonctionnalités de profilage avancées quand l’administrateur a défini le démarrage du pilote et du service.  
  
-   Les utilisateurs de domaine peuvent accéder seulement au profilage d’échantillon.  
  
-   Certains utilisateurs peuvent refuser l’accès au profilage à tous les autres utilisateurs.  
  
 Pour plus d’informations, consultez les options d’administration dans [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Profilage intersession  
 Le *profilage intersession* est la capacité à profiler un processus qui s’exécute dans une autre session ouverte. Par exemple, la plupart des services s’exécutent dans la session 0, et les utilisateurs ne peuvent pas s’exécuter directement dans la session 0. À l’aide du bouton **Attacher au processus** de la barre d’outils de l’Explorateur de performances ou de l’option /attach de l’outil en ligne de commande VSPerfCmd, vous pouvez profiler la plupart des processus dans plusieurs sessions ouvertes.  
  
 Pour consulter la liste des processus disponibles, définissez les options de visibilité du profilage interprocessus. Ces options sont disponibles dans la fenêtre **Attacher au processus** qui s’affiche quand vous cliquez sur **Attacher au processus** :  
  
-   **Afficher les processus de tous les utilisateurs**  
  
     Quand cette option n’est pas sélectionnée, la liste affiche uniquement les processus détenus par l’utilisateur actuel. Quand **Afficher les processus de tous les utilisateurs** est sélectionnée, la liste affiche les processus de tous les utilisateurs.  
  
-   **Afficher les processus de toutes les sessions**  
  
     Quand cette option n’est pas sélectionnée, la liste affiche les processus de la session active. Quand elle est sélectionnée, la liste affiche les processus de toutes les sessions.  
  
## <a name="see-also"></a>Voir aussi  
 [Vues d’ensemble](../profiling/overviews-performance-tools.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Guide pratique pour attacher un processus à un processus en cours d’exécution](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)


