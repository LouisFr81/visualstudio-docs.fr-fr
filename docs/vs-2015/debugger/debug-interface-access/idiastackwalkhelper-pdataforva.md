---
title: IDiaStackWalkHelper::pdataForVA | Microsoft Docs
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
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c937ac3039ef5807623d99a9d7fcaadada17a3e6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816747"
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Retourne le bloc de données PDATA associé à l’adresse virtuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `va`  
 [in] Spécifie l’adresse virtuelle des données à obtenir.  
  
 `cbData`  
 [in] La taille des données en octets à obtenir.  
  
 `pcbData`  
 [out] Retourne la taille réelle des données en octets qui ont été obtenues.  
  
 `pbData`  
 [in, out] Une mémoire tampon est remplie avec les données demandées. Ne peut pas être `NULL`.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` s’il n’existe aucun PDATA pour l’adresse spécifiée. Sinon, retourne un code d'erreur.  
  
## <a name="remarks"></a>Notes  
 PDATA (la section nommée « .pdata ») d’un module contient des informations sur la gestion des exceptions de fonctions.  
  
 L’appelant sait que la quantité de données doit être retournée afin de l’appelant n’a pas besoin de poser pour la quantité de données est disponible. Par conséquent, il est acceptable pour une implémentation de cette méthode retourne une erreur si le `pbData` paramètre est `NULL`.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)



