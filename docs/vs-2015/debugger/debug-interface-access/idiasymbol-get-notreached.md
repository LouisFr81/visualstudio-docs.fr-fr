---
title: IDiaSymbol::get_notReached | Microsoft Docs
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
- C++
helpviewer_keywords:
- IDiaSymbol::get_notReached method
ms.assetid: e44ba922-6cda-40c2-9b62-44e5a8628e63
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17109c26a57d38669488467e8fe536c7e8a81f06
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51790498"
---
# <a name="idiasymbolgetnotreached"></a>IDiaSymbol::get_notReached
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Récupère un indicateur qui spécifie si la fonction ou l’étiquette n’est jamais atteint.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT get_notReached(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 pFlag  
 [out] Retourne `TRUE` si la fonction ou l’étiquette n’est jamais atteint ; sinon, retourne `FALSE`.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne `S_FALSE` ou un code d’erreur.  
  
> [!NOTE]
>  La valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.  
  
## <a name="requirements"></a>Configuration requise  
  
|Spécification|Description|  
|-----------------|-----------------|  
|En-tête :|dia2.h|  
|Version :|DIA SDK 8.0|  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



