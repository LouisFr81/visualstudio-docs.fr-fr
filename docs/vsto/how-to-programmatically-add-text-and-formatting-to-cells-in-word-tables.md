---
title: 'Procédure : Ajouter texte et mise en forme aux cellules des tableaux Word par programmation'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- cells, adding text and formatting
- text [Office development in Visual Studio], adding to Word tables
- formatting [Office development in Visual Studio]
- tables [Office development in Visual Studio], adding text and formatting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 983b2939d652c20c3fbcb42dd8caded802495c8d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56614647"
---
# <a name="how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables"></a>Procédure : Ajouter texte et mise en forme aux cellules des tableaux Word par programmation
  Chaque tableau se compose d’une collection de cellules. Chaque objet <xref:Microsoft.Office.Interop.Word.Cell> représente une cellule dans le tableau. Vous faites référence à chaque cellule par son emplacement dans le tableau. Cet exemple fait référence à la cellule située dans la première ligne et la première colonne du tableau. Il ajoute du texte à la cellule et lui applique un format.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-add-text-and-formatting-to-cells"></a>Pour ajouter du texte et appliquer un format aux cellules

1.  Faites référence à la cellule par son emplacement dans le tableau, ajoutez du texte à la cellule et appliquez-lui un format.

     Vous pouvez utiliser l’exemple de code suivant dans une personnalisation au niveau du document. Pour utiliser cet exemple, exécutez-le à partir de la classe `ThisDocument` dans votre projet.

     [!code-vb[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomation#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#97)]

     L'exemple de code suivant peut être utilisé dans un complément VSTO. Cet exemple utilise le document actif. Pour utiliser l'exemple, exécutez-le à partir de la classe `ThisAddIn` dans votre projet.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#97)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#97](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#97)]

## <a name="see-also"></a>Voir aussi
- [Guide pratique pour Créer par programmation des tableaux Word](../vsto/how-to-programmatically-create-word-tables.md)
- [Guide pratique pour Ajouter par programmation des lignes et colonnes à des tableaux Word](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)
- [Guide pratique pour Remplir par programmation des tableaux Word avec des propriétés de document](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)
