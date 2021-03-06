---
title: Fonction SccBeginBatch | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 31064e0bc746ecc6fb67f5e2feacbd9ae91ca7bd
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51724352"
---
# <a name="sccbeginbatch-function"></a>Fonction SccBeginBatch
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette fonction démarre une séquence de traitement par lots des opérations de contrôle de code source. Le [SccEndBatch](../extensibility/sccendbatch-function.md) sera appelé pour terminer le lot. Ces lots ne peuvent pas être imbriqués.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Aucun.  
  
## <a name="return-value"></a>Valeur de retour  
 L’implémentation de plug-in de contrôle de source de cette fonction est censée retourner l’une des valeurs suivantes :  
  
|Value|Description|  
|-----------|-----------------|  
|SCC_OK|Lot d’opérations a démarré avec succès.|  
|SCC_E_UNKNOWNERROR|Erreur non spécifique.|  
  
## <a name="remarks"></a>Notes  
 Lots de contrôle source sont utilisés pour exécuter les mêmes opérations sur plusieurs projets ou de plusieurs contextes. Lots peuvent être utilisés pour éliminer les boîtes de dialogue de projet redondante à partir de l’expérience utilisateur lors d’une opération par lot. Le `SccBeginBatch` (fonction) et le [SccEndBatch](../extensibility/sccendbatch-function.md) sont utilisés comme une paire de fonction pour indiquer le début et la fin d’une opération. Ils ne peuvent pas être imbriquées. `SccBeginBatch` définit un indicateur qui indique qu’une opération par lot est en cours.  
  
 Pendant une opération par lot est en vigueur, le plug-in de contrôle de code source doit présenter au maximum une boîte de dialogue pour toute question à l’utilisateur et s’appliquent de la réponse à partir de cette boîte de dialogue sur toutes les opérations suivantes.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’API de plug-in de contrôle de source](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)

