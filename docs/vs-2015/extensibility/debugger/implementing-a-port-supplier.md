---
title: Implémentation d’un fournisseur de Port | Microsoft Docs
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
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0596809ceccd3d528e3276f2ed310a4835c836eb
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51738758"
---
# <a name="implementing-a-port-supplier"></a>Implémentation d’un fournisseur de ports
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un fournisseur de port fournit des ports à la demande sur le Gestionnaire de session de débogage (SDM). Un fournisseur de port doit être implémentée lors du débogage sur un ordinateur non-DCOM ou lorsqu’un nouvel appareil doit être pris en charge. Par exemple, pour fournir le débogage à un téléphone portable, vous pouvez implémenter un fournisseur de port qui fournit des ports qui se connectent au téléphone cellulaire (par exemple au moyen de runtime d’intégration ou d’une connexion de cellule) énumère les processus et les programmes s’exécutant sur le téléphone.  
  
 Pour le débogage des programmes sur des ordinateurs Windows (y compris le débogage à distance), Visual Studio fournit des fournisseurs de port pour natif et les processus de Common Language Runtime (CLR), il est donc inutile d’implémenter votre propre fournisseur de port dans ces cas.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Implémentation et inscription d’un fournisseur de port](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 Explique comment le SDM interagit avec le fournisseur de port et de ses ports.  
  
 [Interfaces de fournisseur de port requises](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 Décrit les interfaces qui doivent être implémentées pour obtenir un fournisseur de port.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Concepts du débogueur](../../extensibility/debugger/debugger-concepts.md)  
 Décrit les principaux concepts architectures débogage.  
  
## <a name="see-also"></a>Voir aussi  
 [Extensibilité du débogueur de Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)

