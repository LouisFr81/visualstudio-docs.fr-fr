---
title: Créer des tests unitaires pilotés par les données
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.test.testresults.unittest.datadriven
- vs.test.testresults.unittest.datadriven.failure
helpviewer_keywords:
- unit tests, running
- unit tests, data-driven
- data-driven unit tests
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: dc5c4b68b5713ba8831d840decea7f2ea25704f4
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55931440"
---
# <a name="how-to-create-a-data-driven-unit-test"></a>Procédure : Créer un test unitaire piloté par les données

À l’aide du framework de test unitaire Microsoft pour le code managé, vous pouvez configurer une méthode de test unitaire permettant de récupérer les valeurs utilisées dans la méthode de test à partir d’une source de données. La méthode est exécutée successivement pour chaque ligne de la source de données, ce qui permet de tester facilement diverses entrées à l’aide d’une seule méthode.

La création d’un test unitaire piloté par les données comprend les étapes suivantes :

1.  Créez une source de données qui contient les valeurs que vous utilisez dans la méthode de test. La source de données peut correspondre à n’importe quel type inscrit sur la machine qui exécute le test.

2.  Ajoutez un champ <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> privé et une propriété `TestContext` publique à la classe de test.

3.  Créez une méthode de test unitaire et ajoutez un attribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute>.

4.  Utilisez la propriété d’indexeur <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A> pour récupérer les valeurs que vous utilisez dans un test.

## <a name="the-method-under-test"></a>Méthode testée

Par exemple, vous avez :

1.  Une solution appelée `MyBank`, qui accepte et traite les transactions de différents types de compte.

2.  Un projet dans `MyBank`, appelé `BankDb`, qui gère les transactions des comptes.

3.  Une classe appelée `Maths` dans le projet `DbBank`, qui remplit les fonctions mathématiques permettant de vérifier que les transactions sont avantageuses pour la banque.

4.  Un projet de test unitaire appelé `BankDbTests` pour tester le comportement du composant `BankDb`.

5.  Une classe de test unitaire appelée `MathsTests` pour vérifier le comportement de la classe `Maths`.

Nous allons tester une méthode dans `Maths` qui ajoute deux entiers à l’aide d’une boucle :

```csharp
public int AddIntegers(int first, int second)
{
    int sum = first;
    for( int i = 0; i < second; i++)
    {
        sum += 1;
    }
    return sum;
}
```

## <a name="create-a-data-source"></a>Créer une source de données

Pour tester la méthode `AddIntegers`, créez une source de données qui spécifie une plage de valeurs pour les paramètres et la somme à retourner. Dans cet exemple, nous allons créer une base de données SQL Compact nommée `MathsData` et une table nommée `AddIntegersData`, qui contient les noms et valeurs de colonnes suivants

|FirstNumber|SecondNumber|Sum|
|-|------------------|-|
|0|1|1|
|1|1|2|
|2|-3|-1|

## <a name="add-a-testcontext-to-the-test-class"></a>Ajouter un objet TestContext à la classe de test

Le framework de tests unitaires crée un objet `TestContext` pour stocker les informations de source de données d’un test piloté par les données. Le framework définit ensuite cet objet en tant que valeur de la propriété `TestContext` que vous créez.

```csharp
private TestContext testContextInstance;
public TestContext TestContext
{
    get { return testContextInstance; }
    set { testContextInstance = value; }
}
```

Dans votre méthode de test, vous accédez aux données via la propriété d’indexeur `DataRow` de `TestContext`.

## <a name="write-the-test-method"></a>Écrire la méthode de test

La méthode de test de `AddIntegers` est relativement simple. Pour chaque ligne de la source de données, appelez `AddIntegers` avec les valeurs de colonne **FirstNumber** et **SecondNumber** en tant que paramètres, puis vérifiez la valeur retournée par rapport à la valeur de colonne **Sum** :

```csharp
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0; Data Source=C:\Data\MathsData.sdf;", "Numbers")]
[TestMethod()]
public void AddIntegers_FromDataSourceTest()
{
    var target = new Maths();

    // Access the data
    int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
    int y = Convert.ToInt32(TestContext.DataRow["SecondNumber"]);
    int expected = Convert.ToInt32(TestContext.DataRow["Sum"]);
    int actual = target.IntegerMethod(x, y);
    Assert.AreEqual(expected, actual,
        "x:<{0}> y:<{1}>",
        new object[] {x, y});
}
```

La méthode `Assert` inclut un message qui affiche les valeurs `x` et `y` d’une itération non réussie. Par défaut, les valeurs ayant fait l’objet d’une assertion, `expected` et `actual`, sont déjà incluses dans les détails d’un test non réussi.

### <a name="specify-the-datasourceattribute"></a>Spécifier DataSourceAttribute

L’attribut `DataSource` spécifie la chaîne de connexion de la source de données et le nom de la table que vous utilisez dans la méthode de test. Les informations exactes de la chaîne de connexion varient selon le genre de source de données que vous utilisez. Dans cet exemple, nous avons utilisé une base de données SqlServerCe.

```csharp
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0;Data Source=C:\Data\MathsData.sdf", "AddIntegersData")]
```

L’attribut DataSource a trois constructeurs.

```csharp
[DataSource(dataSourceSettingName)]
```

Un constructeur avec un seul paramètre utilise les informations de connexion stockées dans le fichier *app.config* de la solution. *dataSourceSettingsName* est le nom de l’élément XML contenu dans le fichier config, qui spécifie les informations de connexion.

L’utilisation d’un fichier *app.config* vous permet de changer l’emplacement de la source de données sans changer le test unitaire lui-même. Pour plus d’informations sur la création et l’utilisation d’un fichier *app.config*, consultez [Procédure pas à pas : utilisation d’un fichier config pour définir une source de données](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md)

```csharp
[DataSource(connectionString, tableName)]
```

Le constructeur `DataSource` avec deux paramètres spécifie la chaîne de connexion de la source de données et le nom de la table qui contient les données de la méthode de test.

Les chaînes de connexion dépendent du type de la source de données. Toutefois, elles doivent contenir un élément Provider qui spécifie le nom invariant du fournisseur de données.

```csharp
[DataSource(
    dataProvider,
    connectionString,
    tableName,
    dataAccessMethod
    )]
```

### <a name="use-testcontextdatarow-to-access-the-data"></a>Utiliser TestContext.DataRow pour accéder aux données

Pour accéder aux données de la table `AddIntegersData`, utilisez l’indexeur `TestContext.DataRow`. Comme `DataRow` est un objet <xref:System.Data.DataRow>, récupérez les valeurs de colonne par noms d’index ou de colonnes. Dans la mesure où les valeurs sont retournées en tant qu’objets, convertissez-les vers le type approprié :

```csharp
int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);
```

## <a name="run-the-test-and-view-results"></a>Exécuter le test et afficher les résultats

Une fois que vous avez fini d’écrire une méthode de test, générez le projet de test. La méthode de test apparaît dans l’**Explorateur de tests**, dans le groupe **Tests non exécutés**. Tandis que vous exécutez, écrivez et réexécutez vos tests, **l’Explorateur de tests** affiche les résultats dans les groupes **Échecs de tests**, **Tests réussis** et **Tests non exécutés**. Vous pouvez choisir **Exécuter tout** pour exécuter tous vos tests ou **Exécuter** pour sélectionner un sous-ensemble de tests à exécuter.

La barre des résultats des tests en haut de l’**Explorateur de tests** s’anime pendant l’exécution de votre test. À la fin de la série de tests, la barre est verte en cas de réussite de tous les tests, ou rouge en cas d’échec de l’un des tests. Un résumé de la série de tests s’affiche dans le volet d’informations, en bas de la fenêtre **Explorateur de tests**. Sélectionnez un test pour en afficher les détails dans le volet inférieur.

> [!NOTE]
> Il existe un résultat pour chaque ligne de données et un résultat récapitulatif. Si le test a réussi sur chaque ligne de données, le récapitulatif de l’exécution indique **Réussite**. Si le test a échoué sur une ou plusieurs lignes de données, le récapitulatif de l’exécution indique **Échec**.

Si vous avez exécuté la méthode `AddIntegers_FromDataSourceTest` de notre exemple, la barre des résultats devient rouge et la méthode de test est déplacée vers le groupe **Échecs de tests**. Un test piloté par les données échoue si l’une des méthodes itérées de la source de données échoue également. Quand vous choisissez un test piloté par les données à l’état d’échec dans la fenêtre **Explorateur de tests**, le volet d’informations affiche les résultats de chaque itération identifiée par l’index de ligne de données. Dans notre exemple, il semble que l’algorithme `AddIntegers` ne gère pas correctement les valeurs négatives.

Quand la méthode testée est corrigée et que le test est réexécuté, la barre des résultats devient verte et la méthode de test est déplacée vers le groupe **Tests réussis**.

## <a name="see-also"></a>Voir aussi

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A?displayProperty=fullName>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName>
- [Tests unitaires sur votre code](../test/unit-test-your-code.md)
- [Exécuter des tests unitaires avec l’Explorateur de tests](../test/run-unit-tests-with-test-explorer.md)
- [Écrire des tests unitaires pour le .NET Framework à l’aide du framework de tests unitaires Microsoft pour le code managé](../test/unit-test-your-code.md)