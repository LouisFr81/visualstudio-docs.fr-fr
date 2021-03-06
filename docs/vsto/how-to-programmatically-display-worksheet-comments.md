---
title: 'Procédure : Afficher des commentaires de feuille de calcul par programmation'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, comments
- comments, worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 117643390f5c6bd9e62ec0ee8c8d58c28ec4e1b8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602242"
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>Procédure : Afficher des commentaires de feuille de calcul par programmation
  Vous pouvez afficher et masquer des commentaires dans des feuilles de calcul Microsoft Office Excel par programmation.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>Pour afficher tous les commentaires dans une feuille de calcul dans une personnalisation au niveau du document

1.  Affectez à la propriété <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> la valeur **true** si vous souhaitez afficher les commentaires ; sinon, affectez-lui la valeur **false**. Ce code doit être placé dans une classe Sheet et non pas dans la classe `ThisWorkbook` .

     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]

## <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>Pour afficher tous les commentaires dans une feuille de calcul dans un complément VSTO de niveau application

1.  Affectez à la propriété <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> la valeur **true** si vous souhaitez afficher les commentaires ; sinon, affectez-lui la valeur **false**.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]

## <a name="see-also"></a>Voir aussi
- [Travailler avec des feuilles de calcul](../vsto/working-with-worksheets.md)
- [Guide pratique pour Ajouter et supprimer des commentaires de feuille de calcul par programmation](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)
- [Éléments hôtes et la vue d’ensemble des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)
