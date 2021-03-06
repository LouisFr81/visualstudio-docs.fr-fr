---
title: VSG_DEFAULT_RUN_FILENAME | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 675bd0ceef2b8eef382891bf0fc4b42400ca9df4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018655"
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
Définit par sa présence si une instance par défaut de la [vsgdbg, classe](vsgdbg-class.md) classe, qui fournit l’interface de capture par programmation — est fourni.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## <a name="value"></a>Value  
 Un préprocesseur qui symbole par sa présence ou absence détermine si une instance par défaut de la `VsgDbg` classe est fournie. Si ce symbole est défini, puis aucune instance par défaut de la `VsgDbg` classe est fournie ; sinon, une instance par défaut est fournie et initialisée avant l’exécution de votre programme.  
  
 L’interface de capture par programmation est fournie via un pointeur qui a une portée globale, `g_pVsgDbg`.  
  
```cpp
VsgDbg *g_pVsgDbg;  
```  
  
## <a name="remarks"></a>Remarques  
 L’instance par défaut est souvent suffisante, mais pour utiliser l’interface de capture par programmation à l’intérieur d’une DLL lors de l’appareil D3D a été créé en dehors de cette DLL, vous devez créer et gérer votre propre instance de la `VsgDbg` classe. Si vous gérez votre propre interface à l’API de capture par programmation de cette façon, désactivez l’instance par défaut en définissant `VSG_NODEFAULT_INSTANCE` afin d’éviter la surcharge.  
  
 Si l’instance par défaut n’est pas désactivé, il est automatiquement initialisé avant l’exécution de votre programme et est automatiquement détruit lorsque votre programme se termine. Il est inutile d’initialiser ou annuler explicitement l’initialisation de cette instance.  
  
 Pour désactiver l’instance par défaut, vous devez définir `VSG_NODEFAULT_INSTANCE` avant d’inclure `vsgcapture.h` dans votre programme.  
  
## <a name="example"></a>Exemple  
 Cet exemple montre comment désactiver l’instance par défaut :  
  
```cpp
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```
