---
title: La chaîne de connexion contient des informations d’identification avec un mot de passe de texte clair et n’utilise pas la sécurité intégrée | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f1ec13cab1b8c41225cb1934740b8dd3e7f59ac0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230868"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>La chaîne de connexion contient des informations d'identification comprenant un mot de passe en texte clair et n'utilise pas la sécurité intégrée
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Voulez-vous enregistrer la chaîne de connexion dans le fichier DBML actuel et les fichiers de configuration de l'application avec ces informations confidentielles ?  Cliquez sur Non pour enregistrer la chaîne de connexion sans les informations confidentielles.  
  
 Lorsque vous travaillez avec des connexions de données qui incluent des informations confidentielles (mots de passe inclus dans la chaîne de connexion), vous pouvez enregistrer la chaîne de connexion dans le fichier DBML et le fichier de configuration de l'application du projet, avec ou sans les informations confidentielles.  
  
> [!WARNING]
>  Définir explicitement la **connexion** propriétés **paramètres d’Application** propriété **False** ajoutera le mot de passe pour le fichier DBML.  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>Pour enregistrer la chaîne de connexion avec les informations confidentielles dans les paramètres d'application du projet  
  
-   Cliquez sur **Oui**.  
  
     La chaîne de connexion est stockée en tant que paramètre d'application. La chaîne de connexion intègre les informations sensibles dans le texte brut. Le fichier DBML ne contient pas les informations sensibles.  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>Pour enregistrer la chaîne de connexion sans les informations confidentielles dans les paramètres d'application du projet  
  
-   Cliquez sur **Non**.  
  
     La chaîne de connexion est stockée en tant que paramètre d'application, mais le mot de passe n'est pas inclus.  
  
## <a name="see-also"></a>Voir aussi  
 [Outils LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)

