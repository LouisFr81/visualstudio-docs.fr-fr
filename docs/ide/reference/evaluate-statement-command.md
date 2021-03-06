---
title: Évaluer l'instruction, commande
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 98bdaf41aa34367d656e2bfb5694f3b615dbe3b8
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55911739"
---
# <a name="evaluate-statement-command"></a>Évaluer l'instruction, commande
Évalue et affiche l’instruction donnée.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.EvaluateStatement text
```

## <a name="arguments"></a>Arguments
 `text` Obligatoire. Instruction à évaluer.

## <a name="remarks"></a>Notes
 La fenêtre utilisée pour entrer la commande **EvaluateStatement** détermine si un signe égal (=) est interprété comme un opérateur de comparaison ou comme un opérateur d’assignation.

 Dans la fenêtre **Commande**, un signe égal (=) est interprété comme un opérateur de comparaison. Ainsi, si les valeurs des variables `a` et `b` sont différentes, la commande

```cmd
>Debug.EvaluateStatement(a=b)
```

 retourne la valeur `false`.

 Dans la fenêtre **Exécution**, en revanche, un signe égal (=) est interprété comme un opérateur d’assignation. Ainsi, la commande

```cmd
>Debug.EvaluateStatement(a=b)
```

 assigne à la variable `a` la valeur de variable `b`.

## <a name="example"></a>Exemple

```cmd
>Debug.EvaluateStatement(a+b)
```

## <a name="see-also"></a>Voir aussi

- [Imprimer, commande](../../ide/reference/print-command.md)
- [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Commande, fenêtre](../../ide/reference/command-window.md)
- [Rechercher/Commande, zone](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)