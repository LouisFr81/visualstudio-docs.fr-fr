---
title: IDiaSession::findChildren | Microsoft Docs
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
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71a200d04da6ff79406f54feee05b73be4e6f689
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51782815"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Récupère tous les enfants d’un identificateur du parent spécifié qui correspondent au type de nom et le symbole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `parent`  
 [in] Un [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) objet représentant le parent. Si ce symbole parent est une fonction, un module ou un bloc, ses enfants lexicales sont retournées dans `ppResult`. Si le symbole de parent est un type, ses enfants de la classe sont retournées. Si ce paramètre est `NULL`, puis `symtag` doit être définie sur `SymTagExe` ou `SymTagNull`, qui retourne la portée globale (fichier .exe).  
  
 `symtag`  
 [in] Spécifie la balise de symbole des enfants à récupérer. Les valeurs sont extraites à partir de la [SymTagEnum (énumération)](../../debugger/debug-interface-access/symtagenum.md) énumération. La valeur `SymTagNull` pour récupérer tous les enfants.  
  
 `name`  
 [in] Spécifie le nom des enfants à récupérer. La valeur `NULL` pour tous les enfants doivent être récupérées.  
  
 `compareFlags`  
 [in] Spécifie les options de comparaison appliquées à la correspondance de noms. Les valeurs de la [NameSearchOptions (énumération)](../../debugger/debug-interface-access/namesearchoptions.md) énumération peut être utilisée seul ou combiné.  
  
 `ppResult`  
 [out] Retourne un [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) de récupérer l’objet qui contient la liste des symboles de l’enfant.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment rechercher des variables locales de fonction `pFunc` ce nom de la correspondance `szVarName`.  
  
```cpp#  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions (énumération)](../../debugger/debug-interface-access/namesearchoptions.md)   
 [SymTagEnum, énumération](../../debugger/debug-interface-access/symtagenum.md)



