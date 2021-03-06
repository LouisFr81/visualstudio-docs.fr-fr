---
title: 'Procédure : Exécuter une transformation XSLT à partir de l’éditeur XML'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 56a0fe82-5231-487d-8b6e-a08a9b04e0fc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 918ef14c075bfd09e4361e24bb3b95df53d2e45c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55953264"
---
# <a name="how-to-execute-an-xslt-transformation-from-the-xml-editor"></a>Procédure : Exécuter une transformation XSLT à partir de l’éditeur XML

L'Éditeur XML permet d'associer une feuille de style XSLT à un document XML, d'effectuer la transformation et d'en afficher le résultat. Le résultat de la transformation XSLT est affiché dans une nouvelle fenêtre de document.

Le **sortie** propriété spécifie le nom de fichier pour la sortie. Si le **sortie** propriété est vide, un nom de fichier est généré dans votre répertoire temporaire. L’extension de fichier est basée sur le `xsl:output` élément dans votre style de la feuille et peut être. *XML*,. *txt* ou. *htm*.

Si le **sortie** propriété spécifie un nom de fichier avec une. *htm* ou. *HTML* extension, la sortie XSLT est affichée à l’aide de [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Internet Explorer. Toutes les autres extensions de fichier s'ouvrent dans l'éditeur par défaut choisi par [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Visual Studio. Par exemple, si l’extension de fichier est. *xml*, Visual Studio utilise l’éditeur XML.

## <a name="to-execute-an-xslt-transformation-from-an-xml-document"></a>Pour exécuter une transformation XSLT à partir d'un document XML

1.  Ouvrez un document XML dans l'éditeur XML.

2.  Associez une feuille de style XSLT au document XML.

    -   Ajoutez une instruction de traitement `xml-stylesheet` au document XML. Par exemple, ajoutez la ligne `<?xml-stylesheet type='text/xsl' href='filename.xsl'?>` au prologue du document.

         ou

    -   Ajouter la feuille de style XSLT à l’aide du **propriétés** fenêtre. Dans le document **fenêtre Propriétés**, cliquez sur le **Parcourir** bouton pour le **feuille de style** champ, sélectionnez la feuille de style XSLT, puis cliquez sur **ouvrir**.

3.  Cliquez sur le **ShowXSL sortie** bouton sur le **éditeur XML** barre d’outils.

    > [!NOTE]
    > Si aucune feuille de style n'est associée au document XML, une boîte de dialogue vous invite à la spécifier.
    >
    >  Le résultat de la transformation XSLT est affiché dans une nouvelle fenêtre de document.

## <a name="to-execute-an-xslt-transformation-from-an-xslt-style-sheet"></a>Pour exécuter une transformation XSLT à partir d'une feuille de style XSLT

1.  Ouvrez une feuille de style XSLT dans l'éditeur XML.

2.  Spécifiez un document XML dans le **entrée** champ du document **propriétés** fenêtre.

    > [!NOTE]
    > Le document XML est le document d'entrée utilisé pour la transformation. Si un document n’est pas spécifié lors de la transformation XSLT est démarrée, le **ouvrir le fichier** boîte de dialogue s’affiche et vous pouvez spécifier un document à ce moment-là.

3.  Cliquez sur le **ShowXSLT sortie** bouton sur le **éditeur XML** barre d’outils.

     Le résultat de la transformation XSLT est affiché dans une nouvelle fenêtre de document.

## <a name="to-provide-a-different-output-file-name"></a>Pour spécifier un autre nom de fichier de sortie

1.  Spécifiez un nom de fichier dans le **sortie** champ du document **propriétés** fenêtre.

2.  Cliquez sur le **ShowXSLT sortie** bouton sur le **éditeur XML** barre d’outils.

     Le résultat de la transformation XSLT s’affiche dans une nouvelle fenêtre de document et de l’éditeur utilisé dans la fenêtre de sortie dépend de l’extension de fichier de votre **sortie** propriété de document.

## <a name="see-also"></a>Voir aussi

- [Éditeur XML](../xml-tools/xml-editor.md)