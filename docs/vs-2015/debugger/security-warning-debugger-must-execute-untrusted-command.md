---
title: 'Avertissement de sécurité : Le débogueur doit exécuter une commande non approuvée | Microsoft Docs'
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
- vs.debug.sourceserver.securityalert
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e5c004b3-b364-4098-ac98-770076ca9981
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4f37f629d12a94c65031543d196be92b3f259b6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51744730"
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Avertissement de sécurité : Le débogueur doit exécuter cette commande non approuvée
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette boîte de dialogue d'avertissement apparaît lorsque vous utilisez le serveur source. Elle indique que la commande que le débogueur a besoin d'exécuter pour obtenir le code source n'est pas dans la liste de commandes de confiance pour le serveur source contenue dans le fichier srcsvr.ini. Si c'est une commande valide, vous pouvez l'ajouter au fichier srcsvr.ini. Sinon, vous ne devez pas l'exécuter. Pour plus d’informations, consultez [Spécifier les fichiers de symboles (.pdb) et les fichiers sources](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="message-text"></a>Texte du message  
 **Le débogueur doit exécuter cette commande non approuvée pour obtenir le code source à partir du serveur source.**  
  
 **Si le débogage des fichiers de symboles (\*.pdb) est non à partir d’une source connue et approuvée, cette commande peut être non valide ou dangereuse à exécuter.**  
  
 **Vous souhaitez exécuter cette commande ?**  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 Zone de texte  
 Commande du fichier .pdb à exécuter.  
  
 Run  
 Permet l'exécution de la commande.  
  
 Ne pas exécuter  
 Arrête l'exécution de la commande et le téléchargement du fichier à partir du serveur source.  
  
## <a name="see-also"></a>Voir aussi  
 [Spécifier les symboles (.pdb) et les fichiers sources](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Sécurité du débogueur](../debugger/debugger-security.md)   
 [Serveur source](http://msdn.microsoft.com/library/windows/desktop/ms680641\(v=vs.85\).aspx)



