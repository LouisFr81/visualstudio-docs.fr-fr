---
title: CrossSession | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d465739892d6c3a848069211572019332f97fa77
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55022558"
---
# <a name="crosssession"></a>CrossSession
L’option *VSPerfCmd.exe* **CrossSession** permet au profileur de collecter des données de n’importe quelle session console. L’option **CrossSession** doit être utilisée avec l’option **Start**.  
  
 Vous pouvez utiliser l’abréviation **CS** à la place de **CrossSession**.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### <a name="parameters"></a>Paramètres  
 Aucun.  
  
## <a name="valid-options"></a>Options valides  
 Pour activer le profilage dans une autre session, l’option **CrossSession** doit être spécifiée avec l’option **Start**. L’option **CrossSession** doit également être spécifiée dans toutes les commandes **VSPerfCmd Attach** et **Detach** suivantes.  
  
 **Start:** `Method`  
 L’option **Start** initialise le profileur avec la méthode de profilage spécifiée.  
  
 **Attach :** _PID_[**,**_PID_]  
 Démarre le profilage des processus spécifiés.  
  
 **Detach**[**:**_PID_[,_PID_]]  
 Arrête le profilage des processus spécifiés.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, l’option **CrossSession** est utilisée pour attacher à une application qui a été démarrée dans une autre session de console.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## <a name="see-also"></a>Voir aussi  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profiler des applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profiler des applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profiler des services](../profiling/command-line-profiling-of-services.md)