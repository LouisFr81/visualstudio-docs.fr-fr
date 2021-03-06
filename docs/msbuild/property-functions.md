---
title: Fonctions de propriétés | Microsoft Docs
ms.date: 02/21/2017
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, property functions
ms.assetid: 2253956e-3ae0-4bdc-9d3a-4881dfae4ddb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 86e4c96d0b6f4f441d862ba76bf5fa1199a704d6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997037"
---
# <a name="property-functions"></a>Fonctions de propriétés

Dans les versions 4 et 4.5 de .NET Framework, des fonctions de propriété peuvent être utilisées pour évaluer des scripts MSBuild. Les fonctions de propriété peuvent utilisées partout où figurent des propriétés. Au contraire des tâches, les fonctions de propriété peuvent être utilisées en dehors des cibles et elles sont évaluées avant l'exécution des cibles.

 Sans utiliser de tâches MSBuild, vous pouvez lire l'heure système, comparer des chaînes, établir des correspondances avec des expressions régulières et effectuer d'autres actions dans votre script de génération. MSBuild tente de convertir les chaînes en nombres et les nombres en chaînes, et d'effectuer les autres conversions nécessaires.

## <a name="property-function-syntax"></a>Syntaxe des fonctions de propriété

Il y a trois sortes de fonctions de propriété. Chaque fonction a une syntaxe différente :

- Fonctions de propriété (d'instance) de chaîne
- Fonctions de propriété statique
- Fonctions de propriété MSBuild

### <a name="string-property-functions"></a>Fonctions de propriété de type chaîne

Toutes les valeurs de propriété de build sont simplement des valeurs de chaîne. Vous pouvez utiliser des méthodes (d'instance) de chaîne pour effectuer des opérations sur toutes les valeurs de propriété. Par exemple, vous pouvez extraire le nom du lecteur (les trois premiers caractères) d'une propriété de build qui représente un chemin d'accès complet à l'aide de ce code :

```fundamental
$(ProjectOutputFolder.Substring(0,3))
```

### <a name="static-property-functions"></a>Fonctions de propriété statique

Dans votre script de génération, vous pouvez accéder aux propriétés et aux méthodes statiques de nombreuses classes système. Pour obtenir la valeur d’une propriété statique, utilisez la syntaxe suivante, où \<Class> est le nom de la classe système et \<Property> le nom de la propriété.

```fundamental
$([Class]::Property)
```

Par exemple, vous pouvez utiliser le code suivant pour définir une propriété de build avec la date et l'heure actuelles.

```xml
<Today>$([System.DateTime]::Now)</Today>
```

Pour appeler une méthode statique, utilisez la syntaxe suivante, où \<Class> est le nom de la classe système, \<Method> le nom de la méthode et (\<Parameters>) la liste des paramètres de la méthode :

```fundamental
$([Class]::Method(Parameters))
```

Par exemple, pour définir une propriété de build avec un nouveau GUID, vous pouvez utiliser ce script :

```xml
<NewGuid>$([System.Guid]::NewGuid())</NewGuid>
```

Dans les fonctions de propriété statique, vous pouvez utiliser toutes les méthodes ou propriétés statiques de ces classes système :

- System.Byte
- System.Char
- System.Convert
- System.DateTime
- System.Decimal
- System.Double
- System.Enum
- System.Guid
- System.Int16
- System.Int32
- System.Int64
- System.IO.Path
- System.Math
- System.Runtime.InteropServices.OSPlatform
- System.Runtime.InteropServices.RuntimeInformation
- System.UInt16
- System.UInt32
- System.UInt64
- System.SByte
- System.Single
- System.String
- System.StringComparer
- System.TimeSpan
- System.Text.RegularExpressions.Regex
- System.UriBuilder
- System.Version
- Microsoft.Build.Utilities.ToolLocationHelper

Vous pouvez également utiliser les méthodes et propriétés statiques suivantes :

- System.Environment::CommandLine
- System.Environment::ExpandEnvironmentVariables
- System.Environment::GetEnvironmentVariable
- System.Environment::GetEnvironmentVariables
- System.Environment::GetFolderPath
- System.Environment::GetLogicalDrives
- System.IO.Directory::GetDirectories
- System.IO.Directory::GetFiles
- System.IO.Directory::GetLastAccessTime
- System.IO.Directory::GetLastWriteTime
- System.IO.Directory::GetParent
- System.IO.File::Exists
- System.IO.File::GetCreationTime
- System.IO.File::GetAttributes
- System.IO.File::GetLastAccessTime
- System.IO.File::GetLastWriteTime
- System.IO.File::ReadAllText

### <a name="calling-instance-methods-on-static-properties"></a>Appeler des méthodes d’instance sur des propriétés statiques

Si vous accédez à une propriété statique qui retourne une instance d'un objet, vous pouvez appeler les méthodes d'instance de cet objet. Pour appeler une méthode d’instance, utilisez la syntaxe suivante, où \<Class> est le nom de la classe système, \<Property> le nom de la propriété, \<Method> le nom de la méthode et (\<Parameters>) la liste des paramètres de la méthode :

```fundamental
$([Class]::Property.Method(Parameters))
```

Le nom de la classe doit être complet avec l'espace de noms.

Par exemple, vous pouvez utiliser le code suivant pour définir une propriété de build avec la date du jour.

```xml
<Today>$([System.DateTime]::Now.ToString('yyyy.MM.dd'))</Today>
```

### <a name="msbuild-property-functions"></a>Fonctions de propriété MSBuild

Vous pouvez accéder à plusieurs méthodes statiques dans votre build, qui prennent en charge des fonctions liées à l'arithmétique, à la logique au niveau du bit et aux caractères d'échappement. Pour accéder à ces méthodes, utilisez la syntaxe suivante, où \<Method> est le nom de la méthode et \<(Parameters>) la liste des paramètres de la méthode.

```fundamental
$([MSBuild]::Method(Parameters))
```

Par exemple, pour ajouter en même temps deux propriétés qui ont des valeurs numériques, utilisez le code suivant.

```fundamental
$([MSBuild]::Add($(NumberOne), $(NumberTwo)))
```

Voici une liste de fonctions de propriété MSBuild :

|Signature de fonction|Description|
|------------------------|-----------------|
|double Add(double a, double b)|Additionne deux doubles.|
|long Add(long a, long b)|Additionne deux longs.|
|double Subtract(double a, double b)|Fait une soustraction entre deux doubles.|
|long Subtract(long a, long b)|Fait une soustraction entre deux longs.|
|double Multiply(double a, double b)|Fait une multiplication de deux doubles.|
|long Multiply(long a, long b)|Fait une multiplication de deux longs.|
|double Divide(double a, double b)|Fait une division de deux doubles.|
|long Divide(long a, long b)|Fait une division de deux longs.|
|double Modulo(double a, double b)|Calcule le modulo de deux doubles.|
|long Modulo(long a, long b)|Calcule le modulo de deux longs.|
|chaîne Escape(chaîne sans caractère d'échappement)|Place un caractère d'échappement devant la chaîne selon les règles d'échappement de MSBuild.|
|chaîne Unescape(chaîne avec caractère d'échappement)|Enlève le caractère d'échappement de la chaîne selon les règles d'échappement de MSBuild.|
|entier BitwiseOr(entier premier, entier second)|Effectue un `OR` au niveau du bit sur le premier et le second entier (premier &#124; second).|
|entier BitwiseAnd(entier premier, entier second)|Effectue un `AND` au niveau du bit sur le premier et le second entier (premier & second).|
|entier BitwiseXor(entier premier, entier second)|Effectue un `XOR` au niveau du bit sur le premier et le second entier (premier ^ second).|
|entier BitwiseNot(entier premier)|Effectue un `NOT` au niveau du bit (~premier).|
|bool IsOsPlatform(string platformString)|Spécifie si la plateforme du système d’exploitation actuelle est `platformString`. `platformString`doit être membre de <xref:System.Runtime.InteropServices.OSPlatform>.|
|bool IsOSUnixLike|True si le système d’exploitation actuel est un système Unix.|
|string NormalizePath(params string[] path)|Obtient le chemin complet au format canonique du chemin fourni et vérifie qu’il contient les caractères de séparateur de répertoire appropriés au système d’exploitation actuel.|
|string NormalizeDirectory(params string[] path)|Obtient le chemin complet au format canonique du répertoire fourni et vérifie qu’il contient les caractères de séparateur de répertoire appropriés au système d’exploitation actuel et qu’il se termine par une barre oblique.|
|string EnsureTrailingSlash(string path)|Si le chemin donné ne se termine pas par une barre oblique, ajoutez-en une. Si le chemin est une chaîne vide, ne le modifiez pas.|
|string GetPathOfFileAbove(string file, string startingDirectory)|Recherche un fichier en se basant sur l’emplacement du fichier de build actuel ou sur `startingDirectory`, s’il est spécifié.|
|GetDirectoryNameOfFileAbove(string startingDirectory, string fileName)|Recherche un fichier dans le répertoire spécifié ou dans un emplacement de la structure de répertoire au-dessus de ce répertoire.|
|string MakeRelative(string basePath, string path)|Rend `path` relatif à `basePath`. `basePath` doit être un répertoire absolu. Si rendre `path` relatif n’est pas possible, il est retourné sous forme de chaîne textuelle. Similaire à `Uri.MakeRelativeUri`.|
|string ValueOrDefault(string conditionValue, string defaultValue)|Retourne la chaîne dans le paramètre 'defaultValue' seulement si le paramètre 'conditionValue' est vide ; sinon, retourne la valeur conditionValue.|

##  <a name="nested-property-functions"></a>Fonctions de propriété imbriquées

Vous pouvez combiner des fonctions de propriété pour former des fonctions plus complexes, comme dans l'exemple suivant.

```fundamental
$([MSBuild]::BitwiseAnd(32, $([System.IO.File]::GetAttributes(tempFile))))
```

Cet exemple retourne le bit <xref:System.IO.FileAttributes> de `Archive` (32 ou 0) du fichier spécifié par le chemin d'accès `tempFile`. Notez que les valeurs des données énumérées ne peuvent pas apparaître par leur nom dans les fonctions de propriété. La valeur numérique (32) doit être utilisée à la place.

Des métadonnées peuvent également apparaître dans des fonctions de propriété imbriquées. Pour plus d’informations, consultez l’article [Batching (Traitement par lot MSBuild)](../msbuild/msbuild-batching.md).

## <a name="msbuild-doestaskhostexist"></a>Fonction MSBuild DoesTaskHostExist

La fonction de propriété `DoesTaskHostExist` de MSBuild retourne une valeur indiquant si un hôte de tâche est actuellement installé pour les valeurs de runtime et d'architecture spécifiées.

La syntaxe de cette fonction de propriété est la suivante :

```fundamental
$([MSBuild]::DoesTaskHostExist(string theRuntime, string theArchitecture))
```

## <a name="msbuild-ensuretrailingslash"></a>MSBuild EnsureTrailingSlash

La fonction de propriété `EnsureTrailingSlash` dans MSBuild ajoute une barre oblique de fin s’il n’en existe pas déjà une.

La syntaxe de cette fonction de propriété est la suivante :

```fundamental
$([MSBuild]::EnsureTrailingSlash('$(PathProperty)'))
```

## <a name="msbuild-getdirectorynameoffileabove"></a>Fonction MSBuild GetDirectoryNameOfFileAbove

La fonction de propriété MSBuild `GetDirectoryNameOfFileAbove` recherche un fichier dans les répertoires situés sous le répertoire actif du chemin d'accès.

 La syntaxe de cette fonction de propriété est la suivante :

```fundamental
$([MSBuild]::GetDirectoryNameOfFileAbove(string ThePath, string TheFile))
```

 Le code suivant est un exemple de cette syntaxe.

```xml
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))\EnlistmentInfo.props" Condition=" '$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))' != '' " />
```

## <a name="msbuild-getpathoffileabove"></a>MSBuild GetPathOfFileAbove

La fonction de propriété `GetPathOfFileAbove` dans MSBuild retourne le chemin du fichier qui précède immédiatement celui indiqué. Sur le plan fonctionnel, elle revient à appeler

```xml
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />
```

La syntaxe de cette fonction de propriété est la suivante :

```fundamental
$([MSBuild]::GetPathOfFileAbove(dir.props))
```

## <a name="msbuild-getregistryvalue"></a>Fonction MSBuild GetRegistryValue

La propriété de fonction MSBuild `GetRegistryValue` retourne la valeur d'une clé de Registre. Cette fonction prend deux arguments, le nom de la clé et le nom de la valeur, et retourne la valeur qui se trouve dans le Registre. Si vous ne spécifiez pas un nom de valeur, la valeur par défaut est retournée.

Les exemples suivants montrent comment cette fonction est utilisée :

```fundamental
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, ``))                                  // default value
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, `SymbolCacheDir`))
$([MSBuild]::GetRegistryValue(`HKEY_LOCAL_MACHINE\SOFTWARE\(SampleName)`, `(SampleValue)`))             // parens in name and value
```

## <a name="msbuild-getregistryvaluefromview"></a>Fonction MSBuild GetRegistryValueFromView

La fonction de propriété MSBuild `GetRegistryValueFromView` extrait des données du Registre système en fonction de la clé de Registre, de la valeur et d'une ou plusieurs vues ordonnées du Registre. La clé et la valeur sont recherchées dans chaque vue du Registre dans l'ordre, jusqu'à ce qu'elles soient trouvées.

Le syntaxe de cette fonction de propriété est :

```fundamental
[MSBuild]::GetRegistryValueFromView(string keyName, string valueName, object defaultValue, params object[] views)
```

Le système d’exploitation Windows 64 bits gère une clé de Registre **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node** qui présente une vue de Registre **HKEY_LOCAL_MACHINE\SOFTWARE** pour les applications 32 bits.

Par défaut, une application 32 bits s'exécutant sur WOW64 accède à la vue de Registre 32 bits et une application 64 bits accède à la vue de Registre 64 bits.

Les vues de Registre suivantes sont disponibles :

|Vue de Registre|Définition|
|-------------------|----------------|
|RegistryView.Registry32|Vue de Registre pour les applications 32 bits.|
|RegistryView.Registry64|Vue de Registre pour les applications 64 bits.|
|RegistryView.Default|La vue de Registre qui correspond au processus sur lequel l'application s'exécute.|

Voici un exemple.

 ```fundamental
$([MSBuild]::GetRegistryValueFromView('HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SDKs\Silverlight\v3.0\ReferenceAssemblies', 'SLRuntimeInstallPath', null, RegistryView.Registry64, RegistryView.Registry32))
```

Il extrait les données de **SLRuntimeInstallPath** de la clé **ReferenceAssemblies**, en recherchant d’abord dans la vue de Registre 64 bits, puis dans la vue de Registre 32 bits.

## <a name="msbuild-makerelative"></a>Fonction MSBuild MakeRelative

La fonction de propriété MSBuild `MakeRelative` retourne le chemin d'accès relatif du second chemin par rapport au premier chemin. Chaque chemin peut être un fichier ou un dossier.

La syntaxe de cette fonction de propriété est la suivante :

```fundamental
$([MSBuild]::MakeRelative($(FileOrFolderPath1), $(FileOrFolderPath2)))
```

Le code suivant est un exemple de cette syntaxe.

```xml
<PropertyGroup>
    <Path1>c:\users\</Path1>
    <Path2>c:\users\username\</Path2>
</PropertyGroup>

<Target Name = "Go">
    <Message Text ="$([MSBuild]::MakeRelative($(Path1), $(Path2)))" />
    <Message Text ="$([MSBuild]::MakeRelative($(Path2), $(Path1)))" />
</Target>

<!--
Output:
   username\
   ..\
-->
```

## <a name="msbuild-valueordefault"></a>Fonction MSBuild ValueOrDefault

La fonction de propriété MSBuild `ValueOrDefault` retourne le premier argument, sauf s'il est null ou vide. Si le premier argument est null ou vide, la fonction retourne le second argument.

L'exemple suivant montre comment cette fonction est utilisée.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
        <Value1>$([MSBuild]::ValueOrDefault(`$(UndefinedValue)`, `a`))</Value1>
        <Value2>$([MSBuild]::ValueOrDefault(`b`, `$(Value1)`))</Value2>
    </PropertyGroup>

    <Target Name="MyTarget">
        <Message Text="Value1 = $(Value1)" />
        <Message Text="Value2 = $(Value2)" />
    </Target>
</Project>

<!--
Output:
  Value1 = a
  Value2 = b
-->
```

## <a name="see-also"></a>Voir aussi

[Propriétés MSBuild](../msbuild/msbuild-properties.md)

[Vue d’ensemble de MSBuild](../msbuild/msbuild.md)
