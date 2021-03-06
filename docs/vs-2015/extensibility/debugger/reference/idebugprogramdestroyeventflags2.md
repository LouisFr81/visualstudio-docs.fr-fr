---
title: IDebugProgramDestroyEventFlags2 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProgramDestroyEventFlags2 interface
ms.assetid: d384ff71-dc71-40b9-a871-801f8b6a3418
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d062fe93a18b88cd6c24e0ece18d30f186c6420f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51777030"
---
# <a name="idebugprogramdestroyeventflags2"></a>IDebugProgramDestroyEventFlags2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Permet à un moteur de débogage remplacer le comportement par défaut de la [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] l’interface utilisateur lorsque vous arrêtez une session de débogage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramDestroyEventFlags2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Cette interface est implémentée par les moteurs de débogage. Il est utile pour les hôtes qui peuvent créer et détruire de plusieurs programmes pendant la durée de vie d’un processus.  
  
## <a name="methods"></a>Méthodes  
 Le tableau suivant présente les méthodes de `IDebugProgramDestroyEventFlags2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)|Récupère le programme détruire des indicateurs.|  
  
## <a name="remarks"></a>Notes  
 Le comportement par défaut de la [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] l’interface utilisateur consiste à revenir en arrière en mode Création après que tous les programmes ont envoyées à un programme événement de destruction. Cette interface permet à un moteur de débogage modifier ce comportement.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : Msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

