---
title: IDiaSession::findLinesByRVA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByRVA method
ms.assetid: 06f53b0b-b5b4-42cf-9252-dcee0dbe2d71
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e976fa3172b4f7d3967657b0ac8252d2db93dfb2
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227181"
---
# <a name="idiasessionfindlinesbyrva"></a>IDiaSession::findLinesByRVA
Récupère les lignes dans un compiland spécifiée qui contiennent une adresse virtuelle relative (RVA) spécifiée.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findLinesByRVA ( 
    DWORD                 rva,
    DWORD                 length,
    IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Paramètres
`rva`  
[in] Spécifie l’adresse comme une RVA.

`length`  
[in] Spécifie le nombre d’octets de la plage d’adresses pour couvrir cette requête.

`ppResult`  
[out] Retourne un [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objet qui contient une liste de tous les nombres qui couvrent la plage d’adresses spécifiée.

## <a name="return-value"></a>Valeur de retour
En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="example"></a>Exemple
Cet exemple montre une fonction qui obtient tous les numéros de ligne contenues dans la fonction spécifiée à l’aide d’adresse virtuelle relative de la fonction et la longueur.

```C++
IDiaEnumLineNumbers* GetLineNumbersByRVA(IDiaSymbol *pFunc, IDiaSession *pSession)
{
    IDiaEnumLineNumbers* pEnum = NULL;
    DWORD                rva;
    ULONGLONG            length;

    if (pFunc->get_relativeVirtualAddress ( &rva ) == S_OK)
    {
        pFunc->get_length ( &length );
        pSession->findLinesByRVA( rva, static_cast<DWORD>( length ), &pEnum );
    }
    return(pEnum);
}
```

## <a name="see-also"></a>Voir aussi
[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
[IDiaSession](../../debugger/debug-interface-access/idiasession.md)
