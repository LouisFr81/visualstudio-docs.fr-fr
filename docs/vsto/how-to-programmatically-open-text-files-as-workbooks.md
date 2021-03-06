---
title: 'Procédure : Ouvrir des fichiers texte en tant que classeurs par programmation'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8d53c21247e18f198fdac1c22a3b38c0bc5348b6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56633913"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Procédure : Ouvrir des fichiers texte en tant que classeurs par programmation
  Vous pouvez ouvrir un fichier texte comme un classeur. Vous devez passer le nom du fichier texte que vous souhaitez ouvrir. Vous pouvez spécifier plusieurs paramètres facultatifs, tels que le numéro de ligne à démarrer l’analyse et le format de colonne des données dans le fichier.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Exemple
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>Compiler le code
 Cet exemple nécessite les composants suivants :

-   Un fichier texte délimité par des virgules nommé `Test.txt` qui contient au moins trois lignes de texte.

-   Le fichier texte `Test.txt` à stocker sur le lecteur C.

## <a name="see-also"></a>Voir aussi
- [Travailler avec des classeurs](../vsto/working-with-workbooks.md)
- [Guide pratique pour Ouvrir des classeurs par programmation](../vsto/how-to-programmatically-open-workbooks.md)
- [Guide pratique pour Créer par programmation des classeurs](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Guide pratique pour Enregistrer des classeurs par programmation](../vsto/how-to-programmatically-save-workbooks.md)
- [Guide pratique pour Fermer des classeurs par programmation](../vsto/how-to-programmatically-close-workbooks.md)
- [Paramètres optionnels dans les solutions Office](../vsto/optional-parameters-in-office-solutions.md)
