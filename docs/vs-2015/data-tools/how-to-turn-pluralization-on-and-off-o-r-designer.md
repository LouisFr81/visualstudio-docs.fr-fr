---
title: 'Comment : activer et désactiver (Concepteur O-R) la pluralisation | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1f4491f25a861b8556ae5018e526349d6a17187a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49279108"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>Comment : activer et désactiver (Concepteur O/R) la pluralisation
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Par défaut, lorsque vous faites glisser des objets de base de données qui ont des noms se terminant par s ou ies de **Explorateur de serveurs**/**Database Explorer** sur la [outils LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md), les noms des classes d’entité générées sont modifiés à partir d’au pluriel au singulier. C'est pour insister sur le fait que la classe d'entité instanciée mappe à un enregistrement unique de données. Par exemple, l'ajout d'une table Customers au [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] génère une classe d'entité nommée Customer parce que la classe gérera les données d'un seul client.  
  
> [!NOTE]
>  Par défaut, la pluralisation est activée uniquement dans la version de langue anglaise de Visual Studio.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-turn-pluralization-on-and-off"></a>Pour activer et désactiver la pluralisation  
  
1.  Dans le menu **Outils** , cliquez sur **Options**.  
  
2.  Dans le **Options** boîte de dialogue, développez **outils de base de données**.  
  
> [!NOTE]
>  Sélectionnez **afficher tous les paramètres** si le **outils de base de données** nœud n’est pas visible.  
  
1.  Cliquez sur **Concepteur O/R**.  
  
2.  Définissez **Pluralisation des noms** à **activé** = **False** pour définir le [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] afin qu’il ne modifie pas les noms de classes.  
  
3.  Définissez **Pluralisation des noms** à **activé** = **True** pour appliquer les règles de pluralisation aux noms de classes d’objets ajoutés à la [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Outils LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Accès aux données dans Visual Studio](../data-tools/accessing-data-in-visual-studio.md)

