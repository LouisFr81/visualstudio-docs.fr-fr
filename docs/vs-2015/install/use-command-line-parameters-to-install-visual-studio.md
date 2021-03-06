---
title: Utilisez les paramètres de ligne de commande pour installer Visual Studio 2015 | Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
f1_keywords:
- command-line parameters
- switches
- command prompt
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
caps.latest.revision: 10
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: cd61d03b5639038612e305697f4245e582ee3efe
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54794037"
---
# <a name="use-command-line-parameters-to-install-visual-studio"></a>Utiliser les paramètres de ligne de commande pour installer Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour la documentation la plus récente pour Visual Studio 2017, consultez [utiliser des paramètres de ligne de commande pour installer Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/use-command-line-parameters-to-install-visual-studio).

Quand vous installez Visual Studio 2015 à partir d’une invite de commandes, vous pouvez utiliser les paramètres de ligne de commande suivants (également appelés commutateurs).

> [!NOTE]
>  Assurez-vous que vous utilisez le programme d’installation réelle et pas le fichier de programme d’amorçage. Par exemple, vérifiez que vous utilisez **`vs_enterprise.exe`** au lieu de vs_enterprise_*GUID*.exe. Vous pouvez télécharger un programme d’installation à partir de [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015).

## <a name="list-of-command-line-parameters"></a>Liste des paramètres de ligne de commande
 Les paramètres de ligne de commande Visual Studio ne respectent pas la casse.

|Paramètre|Description|
|---------------|-----------------|
|**/?**<br /><br /> **/help**<br /><br /> **/h**|Affiche les paramètres de la ligne de commande.|
|**/AddRemoveFeatures**|Spécifie les fonctionnalités à ajouter ou à supprimer du produit installé.|
|**/AdminFile** *AdminDeployment.xml*|Installe Visual Studio à l'aide du fichier de données que vous avez spécifié pour l'installation administrative.|
|**/ChainingPackage** *BundleName*|Spécifie le groupe qui effectue le chaînage vers ce groupe. Peut également servir à spécifier une cohorte d'amélioration de l'expérience utilisateur.|
|**/Createadminfile \<filename >**|Spécifie l'emplacement pour créer un fichier de contrôle qui peut être utilisé avec /AdminFile|
|**/CustomInstallPath** *InstallationDirectory*|Installe tous les packages reciblables dans le répertoire que vous spécifiez.|
|**/ForceRestart**|Redémarre toujours l'ordinateur après l'installation.|
|**/full**|Installe toutes les fonctionnalités du produit.|
|**/InstallSelectableItems \<nom de l’élément 1>[;\<nom de l’élément 2>]**|Liste d’éléments de l’arborescence de sélection à cocher sur l’écran de sélection de l’Assistant Installation.|
|**/l**<br /><br /> **/ Journal** *nom de fichier*|Spécifie l'emplacement du fichier journal.|
|**/ Layout** *directory*|Copie les fichiers sur le média d'installation dans le répertoire que vous spécifiez.|
|**/NoCacheOnlyMode**|Empêche le préremplissage du cache du package.|
|**/NoRefresh**|Empêche la vérification des versions plus récentes de ce produit, qu'il s'agisse de versions mises à jour requises ou recommandées.|
|**/norestart**|Empêche l'application d'installation de redémarrer l'ordinateur pendant ou après l'installation. Consultez la section Codes de retour du [Guide de l’administrateur Visual Studio](../install/visual-studio-administrator-guide.md) pour les codes de retour à rechercher.|
|**/noweb**|Empêche l'installation à partir d'Internet.|
|**/Overridefeeduri \<chemin d’accès au flux de fichier >**|Chemin d’accès vers un flux externe local qui décrit les éléments logiciels.|
|**/ProductKey**<br /><br /> *ProductKey*|Définit une clé de produit personnalisée qui ne contient aucun tiret et moins de 25 caractères.|
|**/PromptRestart**|Invite l'utilisateur avant de redémarrer l'ordinateur.|
|**/q**<br /><br /> **/quiet**<br /><br /> **/s**<br /><br /> **/silent**|Supprime l'interface utilisateur (UI) de l'application d'installation. Si Visual Studio est déjà installé et que vous ne spécifiez pas de paramètres à l’exception de celui-ci, l’application d’installation s’exécute en mode de maintenance.|
|**/qb**<br /><br /> **/passive**|Indique la progression, mais n'attend pas de saisie utilisateur.|
|**/repair**|Répare Visual Studio.|
|**/SuppressRefreshPrompt**|Empêche l'affichage de la boîte de dialogue des mises à jour disponibles dans l'Assistant Installation. Ce dernier accepte donc automatiquement toute version mise à jour requise ou recommandée.|
|**/u**<br /><br /> **/Uninstall**|Désinstalle [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|
|**/Uninstall /Force**<br /><br /> **/u /force**|Désinstalle Visual Studio et toutes les fonctionnalités partagées avec d’autres produits. **Avertissement :** si vous utilisez ce paramètre, autres produits qui sont installés sur le même ordinateur fonctionne plus correctement.|

## <a name="see-also"></a>Voir aussi
 [Guide de l’administrateur Visual Studio](../install/visual-studio-administrator-guide.md)