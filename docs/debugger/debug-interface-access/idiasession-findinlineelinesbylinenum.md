---
title: IDiaSession::findInlineeLinesByLinenum | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 432c0859041740c74e6c3264c318d46352d262b3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972691"
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
Récupère une énumération qui permet au client d’effectuer une itération dans les informations de numéro de ligne de toutes les fonctions qui sont inline, directement ou indirectement, dans le nombre de lignes et les fichiers source spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `compiland`  
 [in] Un [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) objet qui représente le compiland dans laquelle rechercher les numéros de ligne. Ce paramètre ne peut pas être `NULL`.  
  
 `file`  
 [in] Un [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) objet qui représente le fichier source dans laquelle rechercher. Ce paramètre ne peut pas être `NULL`.  
  
 `linenum`  
 [in] Spécifie un numéro de ligne de base 1.  
  
> [!NOTE]
>  Vous ne pouvez pas utiliser de zéro pour spécifier toutes les lignes (utiliser le [IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md) méthode pour rechercher toutes les lignes).  
  
 `column`  
 [in] Spécifie le numéro de colonne. Utilisez zéro pour spécifier toutes les colonnes. Une colonne est un offset d’octet dans une ligne.  
  
 `ppResult`  
 [out] Retourne un [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objet qui contient une liste des numéros de ligne qui ont été récupérées.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum, énumération](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)