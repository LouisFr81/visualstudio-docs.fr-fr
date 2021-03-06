---
title: Introduction à la modification pour les développeurs Visual Basic
description: Cette présentation de 10 minutes de l’éditeur de code de Visual Studio montre de quelles façons Visual Studio facilite l’écriture, la navigation et la compréhension du code Visual Basic.
ms.custom: seodec18, get-started
ms.date: 11/20/2018
ms.technology: vs-ide-general
ms.topic: tutorial
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
ms.workload:
- dotnet
ms.openlocfilehash: baed4947d6e31cb06a64f04b0cb68d17d31c6f2f
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939474"
---
# <a name="learn-to-use-the-code-editor"></a>Apprendre à utiliser l’éditeur de code

Dans cette présentation de 10 minutes de l’éditeur de code de Visual Studio, vous allez ajouter du code dans un fichier pour découvrir de quelles façons Visual Studio facilite l’écriture, la navigation et la compréhension du code.

> [!TIP]
> Si vous n’avez pas encore installé Visual Studio, accédez à la page [Téléchargements Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) pour l’installer gratuitement.

Cet article part du principe que vous connaissez déjà Visual Basic. Si ce n’est pas le cas, nous vous suggérons de consulter un tutoriel comme [Bien démarrer avec Visual Basic dans Visual Studio](../../get-started/visual-basic/tutorial-console.md) pour commencer.

> [!TIP]
> Pour suivre cet article, vérifiez que vous avez sélectionné les paramètres Visual Basic pour Visual Studio. Pour plus d’informations sur la sélection des paramètres pour l’environnement de développement intégré (IDE), consultez [Sélectionner les paramètres d’environnement](visual-studio-ide.md#select-environment-settings).

## <a name="create-a-new-code-file"></a>Créer un fichier de code

Vous allez commencer par créer un fichier et y ajouter du code.

1. Ouvrez Visual Studio et, dans le menu **Fichier** de la barre de menus, choisissez **Nouveau fichier**.

1. Dans la boîte de dialogue **Nouveau fichier**, sous la catégorie **Général**, choisissez **Classe Visual Basic**, puis choisissez **Ouvrir**.

   Un nouveau fichier qui s’ouvre dans l’éditeur présente le squelette d’une classe Visual Basic. (Notez que vous n’êtes pas obligés de créer un projet Visual Studio complet pour bénéficier de certains des avantages offerts par l’éditeur de code, comme la coloration syntaxique. Tout ce dont vous avez besoin c’est un fichier de code !)

   ![Fichier de code Visual Basic dans Visual Studio](media/tutorial-editor.png)

## <a name="use-code-snippets"></a>Utiliser des extraits de code

Visual Studio fournit des *extraits de code* qui vous aident à créer rapidement et facilement les blocs de code couramment utilisés. Ces [extraits de code](../../ide/code-snippets.md) sont disponibles pour plusieurs langages de programmation, y compris Visual Basic, C# et C++. Ajoutons l’extrait de code **Sub** Visual Basic à notre fichier.

1. Placez votre curseur au-dessus de la ligne indiquant `End Class` et le type **sub**.

   Une boîte de dialogue contextuelle affiche des informations sur le mot clé `Sub` et relatives à l’insertion de l’extrait de code **Sub**.

   ![IntelliSense pour l’extrait de code dans Visual Studio](media/tutorial-intellisense-snippet.png)

1. Appuyez deux fois sur **Tab** pour insérer l’extrait de code.

   La présentation de la procédure Sub `MySub()` est ajoutée au fichier.

Les extraits de code disponibles diffèrent en fonction des langages de programmation. Vous pouvez examiner les extraits de code disponibles pour Visual Basic en choisissant **Modifier** > **IntelliSense** > **Insérer un extrait de code** (ou appuyez sur  **CTRL**+**K**, **Ctrl**+**X**). Dans Visual Basic, les extraits de code sont disponibles pour les catégories suivantes :

![Liste des extraits de code Visual Basic](media/tutorial-code-snippet-list.png)

Il existe des extraits de code pour déterminer si un fichier existe sur l’ordinateur, pour écrire dans un fichier texte, pour lire une valeur de Registre, pour exécuter une requête SQL, pour créer une [instruction For Each...Next](/dotnet/visual-basic/language-reference/statements/for-each-next-statement) et bien plus encore.

## <a name="comment-out-code"></a>Commenter du code

La barre d’outils, qui est la ligne de boutons sous la barre de menus dans Visual Studio, peut aider à augmenter votre productivité quand vous codez. Par exemple, vous pouvez activer ou désactiver le mode de saisie semi-automatique IntelliSense, augmenter ou réduire un retrait d’une ligne, ou commenter du code que vous ne voulez pas compiler. ([IntelliSense](../../ide/using-intellisense.md) constitue une aide au codage qui affiche une liste de méthodes correspondantes, entre autres.) Dans cette section, nous allons commenter du code.

![Boutons de la barre d'outils de l’éditeur](media/tutorial-editor-toolbar.png)

1. Collez le code suivant dans le corps de la procédure `MySub()`.

   ```vb
   ' _words is a string array that we'll sort alphabetically
   Dim _words = New String() {
   "the",
   "quick",
   "brown",
   "fox",
   "jumps"
   }

   Dim morewords = New String() {
   "over",
   "the",
   "lazy",
   "dog"
   }

   Dim query = From word In _words
               Order By word.Length
               Select word
   ```

1. Nous n’utilisons pas le tableau `morewords`, mais nous n’allons pas le supprimer complètement car nous en aurons peut-être besoin plus tard. Au lieu de cela, nous allons commenter ces lignes. Sélectionnez toute la définition de `morewords` jusqu’à l’accolade de fin, puis choisissez le bouton **Commenter les lignes sélectionnées** dans la barre d’outils. Si vous préférez utiliser le clavier, appuyez sur **Ctrl**+**K**, **Ctrl**+**C**.

   ![Bouton Commenter](media/tutorial-comment-out.png)

   Le caractère de commentaire Visual Basic `'` est ajouté au début de chaque ligne sélectionnée pour commenter le code.

## <a name="collapse-code-blocks"></a>Réduire les blocs de code

Vous pouvez réduire des sections de code pour vous concentrer uniquement sur les parties qui vous intéressent. Pour nous entraîner, nous allons réduire le tableau `_words` à une seule ligne de code. Choisissez la petite case grise avec le signe moins qui se trouve dans la marge de la ligne indiquant `Dim _words = New String() {`. Si vous préférez utiliser le clavier, placez le curseur n’importe où dans la définition du tableau et appuyez sur **Ctrl**+**M**, **Ctrl**+**M**.

![Bouton de réduction du mode Plan](media/tutorial-collapse.png)

Le bloc de code est réduit de façon à afficher uniquement la première ligne, suivie de points de suspension (`...`). Pour redévelopper le bloc de code, cliquez sur la même case grise, qui affiche maintenant un signe plus, ou appuyez sur **Ctrl**+**M**, **Ctrl**+**M**  à nouveau. Cette fonctionnalité, appelée [Mode Plan](../../ide/outlining.md), est très utile pour réduire des méthodes longues ou des classes entières.

## <a name="view-symbol-definitions"></a>Afficher les définitions de symbole

L’éditeur de Visual Studio facilite l’inspection de la définition d’un type, d’une méthode, etc. Une façon de faire est d’accéder au fichier qui contient la définition, par exemple en choisissant **Atteindre la définition** à partir de n’importe quel endroit où le symbole est référencé. Une autre façon encore plus rapide, sans avoir à déplacer le focus en dehors du fichier dans lequel vous travaillez, consiste à utiliser la fonctionnalité [Aperçu de la définition](../../ide/go-to-and-peek-definition.md#peek-definition). Vous allez afficher un aperçu de la définition du type `String`.

1. Cliquez avec le bouton droit sur le mot `String`, puis choisissez **Aperçu de la définition** dans le menu de contenu. Ou bien, appuyez sur **Alt**+**F12**.

   Une fenêtre indépendante s’affiche, avec la définition de la classe `String`. Vous pouvez faire défiler le contenu de la fenêtre indépendante, ou même afficher un aperçu de la définition d’un autre type à partir du code en aperçu.

   ![Fenêtre Aperçu de la définition](media/tutorial-peek-definition.png)

1. Fermez la fenêtre Aperçu de la définition en choisissant la petite case avec un « x » dans le coin supérieur droit de la fenêtre indépendante.

## <a name="use-intellisense-to-complete-words"></a>Utiliser IntelliSense pour compléter des mots

[IntelliSense](../../ide/using-intellisense.md) est une aide précieuse quand vous écrivez du code. Cette fonctionnalité peut afficher des informations sur les membres d’un type disponibles, ou les détails des paramètres des différentes surcharges d’une méthode. Vous pouvez également utiliser IntelliSense pour compléter un mot automatiquement quand vous avez tapé suffisamment de caractères pour lever toute ambiguïté sur le mot. Nous allons ajouter une ligne de code pour imprimer les chaînes ordonnées dans la fenêtre de console, qui est l’emplacement standard pour la sortie du programme.

1. Sous la variable `query`, commencez à taper le code suivant :

   ```vb
   For Each str In qu
   ```

   IntelliSense affiche une **Info express** relative au symbole `query`.

   ![Complétion de mot IntelliSense dans Visual Studio](media/tutorial-intellisense-completion-list.png)

1. Pour insérer le reste du mot `query` à l’aide la fonctionnalité de complétion de mot d’IntelliSense, appuyez sur **Tab**.

1. Terminez le bloc de code pour obtenir le code suivant.

   ```vb
   For Each str In query
       Console.WriteLine(str)
   Next
   ```

## <a name="refactor-a-name"></a>Refactoriser un nom

Aucun développeur ne réussit à créer un code parfait dès le départ. L’une de vos premières modifications sera probablement de changer le nom d’une variable ou d’une méthode. Nous allons donc essayer la fonctionnalité [Refactoriser](../../ide/refactoring-in-visual-studio.md) de Visual Studio pour renommer la variable `_words` en `words`.

1. Placez votre curseur sur la définition de la variable `_words`, puis choisissez **Renommer** dans le menu contextuel (clic droit).

   Une boîte de dialogue contextuelle **Renommer** s’affiche en haut à droite de l’éditeur.

1. Avec la variable `_words` toujours sélectionnée, tapez le nom de votre choix pour **mots**. Notez que la référence à `words` dans la requête est également renommée automatiquement. Avant d’appuyer sur **Entrée** ou de cliquer sur **Appliquer**, cochez la case **Inclure les commentaires** dans la boîte de dialogue contextuelle **Renommer**.

   ![Renommer (boîte de dialogue)](media/tutorial-rename.png)

1. Appuyez sur **Entrée** ou cliquez sur **Appliquer**.

   Les deux occurrences de `words` sont renommées, tout comme la référence à `words` dans le commentaire de code.

## <a name="next-steps"></a>Étapes suivantes

> [!div class="nextstepaction"]
> [Découvrir les projets et les solutions](tutorial-projects-solutions.md)

## <a name="see-also"></a>Voir aussi

- [Extraits de code](../../ide/code-snippets.md)
- [Naviguer dans le code](../../ide/navigating-code.md)
- [Mode Plan](../../ide/outlining.md)
- [Atteindre la définition et Aperçu de la définition](../../ide/go-to-and-peek-definition.md)
- [Refactorisation](../../ide/refactoring-in-visual-studio.md)
- [Utiliser IntelliSense](../../ide/using-intellisense.md)