---
title: Référence des API pour l’extensibilité de modélisation UML | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML - extending
- UML API
- UML model, API
ms.assetid: 2b2ffe93-c358-4d28-a5e5-3d0474629b58
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: dff485db59f418fe05cd586335b6f9ceae153428
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51785038"
---
# <a name="api-reference-for-uml-modeling-extensibility"></a>Référence des API pour l'extensibilité de la modélisation UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez écrire du code de programme pour lire et modifier les modèles que vous créez avec Visual Studio. La référence de l'API fournit des informations sur les classes spécifiques pour vous aider lors de cette tâche. Pour plus d’informations sur les tâches, consultez les rubriques sous [modèles et diagrammes UML étendre](../modeling/extend-uml-models-and-diagrams.md). Pour connaître les versions de Visual Studio qui prennent en charge les modèles UML, consultez [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="assemblies"></a>Assemblys  
  
|Assembly|Ce que cela vous permet de faire|  
|--------------|--------------------------------|  
|Microsoft.VisualStudio.Uml.Interfaces.dll|-Permet de lire et modifier des éléments de modèle tels que IUseCase, IAssociation et ainsi de suite.<br />-Parcourir les relations entre les éléments.<br /><br /> Les espaces de noms et les types correspondent à ceux définis dans la spécification UML.|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll|-Créer de nouvelles instances d’éléments de modèle<br />-Permet d’accéder et modifier des formes et des diagrammes.|  
  
## <a name="see-also"></a>Voir aussi  
 [Étendre des diagrammes et des modèles UML](../modeling/extend-uml-models-and-diagrams.md)   
 [Informations de référence de l’API pour le SDK de modélisation pour Visual Studio](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)



