---
title: Vue d’ensemble (SDK Debug Interface Access) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f159dcc58a096033516fdd272819b9eb1ad916d1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922653"
---
# <a name="overview-debug-interface-access-sdk"></a>Vue d’ensemble (Kit de développement logiciel Debug Interface Access)
Utilisez le SDK de DIA pour accéder aux informations de débogage de Microsoft. Le SDK de DIA fournit qu'une COM en fonction d’ensemble d’API qui élimine la nécessité de réécrire votre code chaque fois que Microsoft modifie le format des informations de débogage. Le DIA SDK vous permet également de lire à partir d’un ensemble sélectionné de versions précédentes d’informations de débogage, situés dans des fichiers .pdb et .dbg générés par [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 5.0 et versions ultérieures.  
  
 Chaque interface dans le SDK DIA représente un autre objet COM, sauf cas contraire. Interfaces supplémentaires et donc des objets supplémentaires, sont créés au moyen de requêtes explicites, tel que [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) ou [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md), et non en appelant `QueryInterface` sur les pointeurs d’interface existante.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)