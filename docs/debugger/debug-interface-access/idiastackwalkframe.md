---
title: IDiaStackWalkFrame | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf14665b4a8f6f57e01d53debedbb3534fa025d1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015483"
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
Gère le contexte de la pile entre les appels de la [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md) (méthode).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IDiaStackWalkFrame`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Récupère la valeur d’un Registre.|  
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Définit la valeur d’un Registre.|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Lit la mémoire à partir de l’image.|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Recherche dans le frame de pile spécifié pour l’adresse de retour de fonction le plus proche.|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Recherche dans le frame de pile spécifié pour une adresse de retour à ou près de l’adresse spécifiée.|  
  
## <a name="remarks"></a>Remarques  
 Cette interface est utilisée pendant l’exécution du programme pour lire et écrire des registres ainsi accéder à la mémoire et rechercher une adresse de retour.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 L’application cliente implémente cette interface et passe une instance de l’interface à la [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md) (méthode). La même instance de cette interface est encore et encore utilisée pour maintenir l’état des registres pendant chaque appel de la `execute` (méthode). Le `execute` méthode utilise également cette interface pour déterminer l’adresse de retour.  
  
## <a name="requirements"></a>Spécifications  
 En-tête : Dia2.h  
  
 Bibliothèque : diaguids.lib  
  
 DLL : msdia80.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces (Kit SDK Debug Interface Access)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)