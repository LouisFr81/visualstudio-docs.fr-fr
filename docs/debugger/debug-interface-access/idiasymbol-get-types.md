---
title: IDiaSymbol::get_types | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_types method
ms.assetid: 5f056e0c-e15b-4e00-8f78-aadc8574f7ea
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fcfde6e7824fa0df315cb843eedb92e4d249b618
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54965144"
---
# <a name="idiasymbolgettypes"></a>IDiaSymbol::get_types
Récupère un tableau de types spécifiques au compilateur pour ce symbole.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_types (   
   DWORD       cTypes,  
   DWORD*      pcTypes,  
   IDiaSymbol* types[]  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `cTypes`  
 [in] Taille de la mémoire tampon devant contenir les données.  
  
 `pcTypes`  
 [out] Retourne le nombre de types écrits, ou, si le `types` paramètre est `NULL`, puis le nombre total de types disponibles.  
  
 `types[]`  
 [out] Un tableau qui doit être rempli avec le [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) les objets qui représentent tous les types de ce symbole.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne `S_FALSE` ou un code d’erreur.  
  
> [!NOTE]
>  La valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)