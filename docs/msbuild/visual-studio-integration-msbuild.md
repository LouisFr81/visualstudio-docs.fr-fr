---
title: Intégration de Visual Studio (MSBuild)
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, reference resolution
- MSBuild, well-known target names
- MSBuild, hosting
- MSBuild, editing project files
- MSBuild, Visual Studio integration
- MSBuild, IntelliSense
- MSBuild, output groups
- MSBuild, in-process compilers
- MSBuild, design-time target execution
ms.assetid: 06cd6d7f-8dc1-4e49-8a72-cc9e331d7bca
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f1c9428c2ee0c6d27e6a0ce707ec3e322005dab1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54973354"
---
# <a name="visual-studio-integration-msbuild"></a>Intégration de Visual Studio (MSBuild)
Visual Studio héberge [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pour charger et générer des projets managés. Dans la mesure où [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] est responsable du projet, la plupart des projets au format [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] peut être utilisé sans problème dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], même si le projet a été créé par un outil différent et possède un processus de génération personnalisé.  
  
 Cet article décrit des aspects spécifiques de l'hébergement de [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]dans [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] qui doivent être pris en compte lors de la personnalisation des projets et des fichiers *.targets* que vous souhaitez charger et générer dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Vous serez ainsi assuré que les fonctionnalités [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , telles qu'IntelliSense et le débogage fonctionnent pour votre projet personnalisé.  
  
 Pour plus d’informations sur les projets C++, consultez [Fichiers projet](/cpp/ide/project-files).  
  
## <a name="project-file-name-extensions"></a>Extensions de nom de fichier projet  
 *MSBuild.exe* reconnaît n'importe quelle extension de nom de fichier projet correspondant au modèle *.\*proj*. En revanche, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] reconnaît uniquement un sous-ensemble de ces extensions, lesquelles déterminent le système de projet spécifique au langage qui chargera le projet. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ne possède pas de système de projet basé sur [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] , indépendant du langage.  
  
 Par exemple, le système de projet [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] charge des fichiers *.csproj*, mais [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] n'est pas en mesure de charger un fichier *.xxproj*. Un fichier projet pour les fichiers sources dans un langage arbitraire doit utiliser la même extension que les fichiers projet [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ou [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] pour être chargé dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="well-known-target-names"></a>Noms de cibles connus  
 Lorsque vous cliquez sur la commande **Générer** dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , la cible par défaut est exécutée dans le projet. Dans de nombreux cas, cette cible est également nommée `Build`. La sélection de la commande **Régénérer** ou **Nettoyer** entraîne une tentative d'exécution d'une cible du même nom dans le projet. Un clic sur **Publier** se traduit par l'exécution d'une cible nommée `PublishOnly` dans le projet.  
  
## <a name="configurations-and-platforms"></a>Configurations et plateformes  
 Les configurations sont représentées dans les projets [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] par des propriétés regroupées dans un élément `PropertyGroup` qui contient un attribut `Condition` . [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] examine ces conditions pour créer une liste de configurations de projet et de plateformes à afficher. Pour réussir à extraire cette liste, les conditions doivent avoir un format similaire à ce qui suit :  
  
```xml  
Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' "  
Condition=" '$(Configuration)' == 'Release' "   
Condition=" '$(Something)|$(Configuration)|$(SomethingElse)' == 'xxx|Debug|yyy' "  
```  
  
 À cette fin,[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] examine les conditions définies sur les éléments `PropertyGroup`, `ItemGroup`, `Import`, de propriétés et item.  
  
## <a name="additional-build-actions"></a>Actions de génération supplémentaires  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vous permet de modifier le nom du type d’élément d’un fichier dans un projet avec la propriété **Action de génération** de la fenêtre **Propriétés du fichier**. Les noms des types d'éléments **Compiler**, **EmbeddedResource**, **Contenu** et **Aucun** sont toujours répertoriés dans ce menu, avec tous les autres noms de types d'éléments figurant déjà dans votre projet. Pour garantir la disponibilité permanente de tous les noms de types d'éléments personnalisés dans ce menu, vous pouvez ajouter les noms à un type d'élément nommé `AvailableItemName`. Par exemple, en ajoutant ce qui suit à votre fichier projet, le type personnalisé **JScript** est ajouté à ce menu pour tous les projets qui l'importent :  
  
```xml  
<ItemGroup>  
    <AvailableItemName Include="JScript"/>  
</ItemGroup>  
```  
  
> [!NOTE]
>  Certains noms de types d'éléments sont spécifiques à [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mais ne sont pas répertoriés dans cette liste déroulante.  
  
## <a name="in-process-compilers"></a>Compilateurs in-process  
 Lorsque c'est possible, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tente d'utiliser la version intra-processus du compilateur [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] pour améliorer les performances. (Non applicable à [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].) Pour un fonctionnement correct, les conditions suivantes doivent être respectées :  
  
- Une cible du projet doit contenir une tâche nommée `Vbc` pour les projets [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)].  
  
- Le paramètre `UseHostCompilerIfAvailable` de la tâche doit avoir la valeur true.  
  
## <a name="design-time-intellisense"></a>IntelliSense au moment du design  
 Pour bénéficier de la prise en charge d'IntelliSense dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] avant la génération d'un assembly de sortie, les conditions suivantes doivent être respectées :  
  
-   Il doit exister une cible nommée `Compile`.  
  
-   La cible `Compile` ou l'une de ses dépendances doit appeler la tâche du compilateur du projet, par exemple `Csc` ou `Vbc`.  
  
-   La cible `Compile` ou l'une de ses dépendances doit faire en sorte que le compilateur reçoive tous les paramètres nécessaires à IntelliSense, en particulier toutes les références.  
  
-   Les conditions répertoriées dans la section [Compilateurs in-process](#in-process-compilers) doivent être respectées.  
  
## <a name="build-solutions"></a>Solutions de build  
 Dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], l'ordre des générations de projets et du fichier solution est contrôlé par [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] lui-même. Lors de la génération d'une solution avec *msbuild.exe* à partir de la ligne de commande, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] analyse le fichier solution et classe les générations de projets. Dans les deux cas, les projets sont générés individuellement en fonction de l'ordre des dépendances et les références entre projets ne sont pas parcourues. En revanche, lors de la génération de projets individuels avec *msbuild.exe*, les références entre projets sont parcourues.  
  
 Lors de la génération dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], la propriété `$(BuildingInsideVisualStudio)` a la valeur `true`. Vous pouvez l'utiliser dans vos fichiers projet ou *.targets* pour que la génération se comporte différemment.  
  
## <a name="display-properties-and-items"></a>Afficher des propriétés et des éléments  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] reconnaît certains noms et valeurs de propriété. Par exemple, la présence de la propriété suivante dans un projet entraîne l'affichage de **Application Windows** dans la zone **Type d'application** du **Concepteur de projets**.  
  
```xml  
<OutputType>WinExe</OutputType>  
```  
  
 La valeur de la propriété peut être modifiée dans le **Concepteur de projets** et enregistrée dans le fichier projet. Si valeur non valide est affectée à une telle propriété lors d'une modification manuelle, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] affiche un avertissement lors du chargement du projet et remplace la valeur non valide par une valeur par défaut.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] reconnaît les valeurs par défaut de certaines propriétés. Ces propriétés ne sont pas rendues persistantes dans le fichier projet sauf si elles possèdent des valeurs non définies par défaut.  
  
 Les propriétés portant des noms arbitraires ne sont pas affichées dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Pour modifier des propriétés arbitraires dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], vous devez ouvrir le fichier projet dans l'Éditeur XML et les modifier manuellement. Pour plus d’informations, consultez la section [Modifier les fichiers projet dans Visual Studio](#edit-project-files-in-visual-studio) plus loin dans cette rubrique.  
  
 Les éléments définis dans le projet avec des noms de types d'éléments arbitraires sont affichés par défaut dans l'**Explorateur de solutions** sous leur nœud de projet. Pour masquer un élément, attribuez la valeur `Visible` aux métadonnées `false`. Par exemple, l'élément suivant participera au processus de génération, mais ne s'affichera pas dans l'**Explorateur de solutions**.  
  
```xml  
<ItemGroup>  
    <IntermediateFile Include="cache.temp">  
        <Visible>false</Visible>  
    </IntermediateFile>  
</ItemGroup>  
```  
  
 Les éléments déclarés dans les fichiers importés dans le projet ne sont pas affichés par défaut. Les éléments créés pendant le processus de génération ne sont jamais affichés dans l'**Explorateur de solutions**.  
  
## <a name="conditions-on-items-and-properties"></a>Conditions appliquées aux éléments et aux propriétés  
 Pendant une génération, toutes les conditions sont respectées pleinement.  
  
 Lors de la détermination des valeurs de propriétés à afficher, les propriétés que [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] considère comme dépendantes de la configuration sont évaluées différemment des propriétés considérées comme indépendantes de la configuration. Pour les propriétés dépendantes de la configuration, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] définit les propriétés `Configuration` et `Platform` de la façon appropriée et indique à [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] de réévaluer le projet. Pour les propriétés indépendantes de la configuration, le mode d'évaluation des conditions n'est pas déterminé.  
  
 Lorsqu'il faut déterminer l'affichage de l'élément dans l'**Explorateur de solutions**, les expressions conditionnelles associées à des éléments sont toujours ignorées.  
  
## <a name="debugging"></a>Débogage  
 Pour rechercher et lancer l'assembly de sortie ainsi qu'attacher le débogueur, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a besoin des propriétés `OutputPath`, `AssemblyName`et `OutputType` correctement définies. Il ne sera pas possible d'attacher le débogueur si le processus de génération n'a pas donné lieu à la génération d'un fichier *.pdb* par le compilateur.  
  
## <a name="design-time-target-execution"></a>Exécution des cibles au moment du design  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tente d'exécuter des cibles portant certains noms lorsqu'il charge un projet. Il s'agit notamment des cibles `Compile`, `ResolveAssemblyReferences`, `ResolveCOMReferences`, `GetFrameworkPaths` et `CopyRunEnvironmentFiles`. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] exécute ces cibles afin que le compilateur puisse être initialisé pour fournir IntelliSense, que le débogueur puisse être initialisé et que les références affichées dans l'Explorateur de solutions puissent être résolues. En l'absence de ces cibles, le projet se charge et effectue une génération correcte, mais l'expérience au moment du design dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ne sera pas complètement fonctionnelle.  
  
##  <a name="edit-project-files-in-visual-studio"></a>Modifier des fichiers projet dans Visual Studio  
 Pour modifier directement un projet [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] , vous pouvez ouvrir le fichier projet dans l'Éditeur XML de Visual Studio.  
  
#### <a name="to-unload-and-edit-a-project-file-in-visual-studio"></a>Pour décharger et modifier un fichier projet dans Visual Studio  
  
1.  Dans l' **Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Décharger le projet**.  
  
     Le projet est alors marqué **(non disponible)**.  
  
2.  Dans l’**Explorateur de solutions**, ouvrez le menu contextuel du projet indisponible et choisissez **Modifier \<Fichier projet>**.  
  
     Le fichier projet s'ouvre dans l'Éditeur XML de Visual Studio.  
  
3.  Modifiez, enregistrez, puis fermez le fichier projet.  
  
4.  Dans l' **Explorateur de solutions**, ouvrez le menu contextuel du projet indisponible et choisissez **Recharger le projet**.  
  
## <a name="intellisense-and-validation"></a>IntelliSense et validation  
 Lors de l'utilisation de l'Éditeur XML pour modifier des fichiers projet, IntelliSense et la validation sont pilotés par les fichiers de schéma [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] . Ceux-ci sont installés dans le cache des schémas, qui se trouve dans *\<Répertoire d’installation de Visual Studio>\Xml\Schemas\1033\MSBuild*.  
  
 Les types [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] principaux sont définis dans *Microsoft.Build.Core.xsd* et les types communs utilisés par [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sont définis dans *Microsoft.Build.CommonTypes.xsd*. Pour personnaliser les schémas afin de disposer d'IntelliSense et de la validation pour les noms, les propriétés et les tâches des types d'éléments personnalisés, vous pouvez modifier *Microsoft.Build.xsd* ou créer votre propre schéma incluant les schémas CommonTypes ou Core. Si vous créez votre propre schéma, vous devez indiquer à l'Éditeur XML de l'utiliser à l'aide de la fenêtre **Propriétés** .  
  
## <a name="edit-loaded-project-files"></a>Modifier des fichiers projet chargés  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] met en cache le contenu des fichiers projet et des fichiers importés par les fichiers projet. Si vous modifiez un fichier projet chargé, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vous invite automatiquement à recharger le projet afin que les modifications soient appliquées. Toutefois, si vous modifiez un fichier importé par un projet chargé, aucune invite de rechargement ne s'affiche et vous devez décharger et recharger manuellement le projet pour que les modifications prennent effet.  
  
## <a name="output-groups"></a>Groupes de sortie  
 Plusieurs cibles définies dans *Microsoft.Common.targets* possèdent des noms se terminant par `OutputGroups` ou `OutputGroupDependencies`. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] appellent ces cibles pour obtenir des listes spécifiques de sorties de projet. Ainsi, la cible `SatelliteDllsProjectOutputGroup` crée une liste de tous les assemblys satellites créés par une génération. Ces groupes de sorties sont utilisés par des fonctionnalités, telles que la publication, le déploiement et les références entre projets. Les projets qui ne les définissent pas seront chargés et générés dans [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], mais il se peut que certaines fonctionnalités ne fonctionnent pas correctement.  
  
## <a name="reference-resolution"></a>Résolution de référence  
 La résolution des références est le processus consistant à utiliser des éléments de référence stockés dans un fichier projet pour localiser les assemblys actifs. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] doit déclencher la résolution de références pour afficher les propriétés détaillées de chaque référence dans la fenêtre **Propriétés** . La liste suivante décrit les trois types de références et leur mode de résolution.  
  
- Références d'assembly :  
  
   Le système de projet appelle une cible avec le nom connu `ResolveAssemblyReferences`. Cette cible doit produire des éléments avec le nom de type d'élément `ReferencePath`. Chacun de ces éléments doit avoir une spécification d'élément (la valeur de l'attribut `Include` d'un élément) qui contient le chemin d'accès complet à la référence. Les éléments doivent avoir toutes les métadonnées des éléments d'entrée passés en plus des nouvelles métadonnées suivantes :  
  
  - `CopyLocal`, indiquant si l'assembly doit être copié dans le dossier de sortie ; la valeur peut être true ou false.  
  
  - `OriginalItemSpec`, contenant la spécification d'élément d'origine de la référence.  
  
  - `ResolvedFrom`, avec la valeur "{TargetFrameworkDirectory}" s'il a été résolu à partir du répertoire [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] .  
  
- Références COM :  
  
   Le système de projet appelle une cible avec le nom connu `ResolveCOMReferences`. Cette cible doit produire des éléments avec le nom de type d'élément `ComReferenceWrappers`. Chacun de ces éléments doit posséder une spécification d'élément qui contient le chemin d'accès complet à l'assembly d'interopérabilité pour la référence COM. Les éléments doivent avoir toutes les métadonnées des éléments d'entrée passés, en plus de nouvelles métadonnées portant le nom `CopyLocal`, qui indiquent si l'assembly doit être copié dans le dossier de sortie ; la valeur peut être true ou false.  
  
- Références natives  
  
   Le système de projet appelle une cible avec le nom connu `ResolveNativeReferences`. Cette cible doit produire des éléments avec le nom de type d'élément `NativeReferenceFile`. Les éléments doivent avoir toutes les métadonnées des éléments d'entrée passés, en plus d'une nouvelle métadonnée nommée `OriginalItemSpec`, contenant la spécification d'élément d'origine de la référence.  
  
## <a name="performance-shortcuts"></a>Raccourcis de performances  
 Si vous démarrez le débogage dans l'interface utilisateur de Visual Studio (en choisissant la touche F5 ou en choisissant **Déboguer** > **, dans le menu Démarrer le débogage**), le processus de génération utilise une vérification des mises à jour rapide pour améliorer les performances. Dans les cas où les générations personnalisées créent les fichiers qui sont générés à leur tour, la vérification de mise à jour rapide n'identifie pas correctement les fichiers modifiés. Les projets qui ont besoin de vérifications de mise à jour plus complètes peuvent désactiver la vérification rapide en définissant la variable d'environnement `DISABLEFASTUPTODATECHECK=1`. Les projets peuvent également définir cela comme une propriété MSBuild dans le projet ou dans un fichier que le projet importe.  
  
 Pour des builds classiques dans Visual Studio, la vérification des mises à jour rapide ne s'applique pas, et le projet est généré comme si vous appeliez la build dans une invite de commandes.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour étendre le processus de génération Visual Studio](../msbuild/how-to-extend-the-visual-studio-build-process.md)   
 [Démarrer une build à partir de l’environnement IDE](../msbuild/starting-a-build-from-within-the-ide.md)   
 [Inscrire des extensions du .NET Framework](../msbuild/registering-extensions-of-the-dotnet-framework.md)   
 [Concepts MSBuild](../msbuild/msbuild-concepts.md)   
 [Item, élément (MSBuild)](../msbuild/item-element-msbuild.md)   
 [Élément de propriété (MSBuild)](../msbuild/property-element-msbuild.md)   
 [Target, élément (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Csc, tâche](../msbuild/csc-task.md)   
 [Vbc, tâche](../msbuild/vbc-task.md)