---
title: Synchroniser les paramètres
ms.date: 12/10/2018
ms.topic: conceptual
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6faaf37c3a1c8e67412898ca631210eb551f3331
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926045"
---
# <a name="synchronize-visual-studio-settings-across-multiple-computers"></a>Synchroniser les paramètres Visual Studio sur plusieurs ordinateurs

Quand vous vous connectez à Visual Studio sur plusieurs ordinateurs en utilisant le même compte de personnalisation, vos paramètres peuvent être synchronisés entre les ordinateurs.

## <a name="synchronized-settings"></a>Paramètres synchronisés

Par défaut, les paramètres suivants sont synchronisés :

- Paramètres de développement. Vous sélectionnez un ensemble de paramètres la première fois que vous ouvrez Visual Studio, mais vous pouvez les changer quand vous voulez. Pour plus d’informations, consultez [Paramètres d’environnement](../ide/environment-settings.md).

- Alias de commande définis par l'utilisateur. Pour plus d’informations sur la façon de définir des alias de commande, consultez [Alias de commandes Visual Studio](../ide/reference/visual-studio-command-aliases.md).

- Dispositions de fenêtres définies par l’utilisateur dans la page **Fenêtre** > **Gérer les dispositions de fenêtres**.

- Les options suivantes des pages **Outils** > **Options** :

   - Paramètres de thème et de mise en majuscules de la barre de menus, dans la page d’options **Environnement** > **Général**

   - Tous les paramètres de la page d’options **Environnement** > **Polices et couleurs**

   - Tous les raccourcis clavier de la page d’options **Environnement** > **Clavier**

   - Tous les paramètres de la page d’options **Environnement** > **Onglets et fenêtre**

   - Tous les paramètres de la page d’options **Environnement** > **Démarrage**

   - Tous les paramètres des pages d’options de l’**Éditeur de texte**

   - Tous les paramètres des pages d’options du **Concepteur XAML**

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>Désactiver les paramètres synchronisés sur un ordinateur particulier

Les paramètres synchronisés pour Visual Studio sont activés par défaut. Vous pouvez désactiver les paramètres synchronisés sur un ordinateur en accédant à la page **Outils** > **Options** > **Environnement** > **Comptes**, et en décochant la case **Synchroniser les paramètres entre les appareils quand ils sont connectés à Visual Studio**.

Par exemple, si vous décidez de ne pas synchroniser les paramètres de Visual Studio sur l’ordinateur « A », les changements apportés aux paramètres sur l’ordinateur « A » n’apparaissent pas sur l’ordinateur « B » ou « C ». Les ordinateurs « B » et « C » continuent à se synchroniser entre eux, mais pas avec l’ordinateur « A ».

> [!NOTE]
> Si vous choisissez de ne pas synchroniser les paramètres en désélectionnant l’option sur la page **Outils** > **Options** > **Environnement**  >  **Comptes**, les autres versions ou éditions de Visual Studio dont vous disposez sur le même ordinateur ne sont pas affectées. Ces installations côte à côte de Visual Studio continuent de synchroniser leurs paramètres (sauf si vous décochez l’option).

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>Synchroniser les paramètres entre les éditions et les produits de la famille Visual Studio

Les paramètres sont synchronisés entre les versions et éditions de Visual Studio installées *côte à côte*. Les paramètres sont également synchronisés entre les produits de la famille Visual Studio, notamment Blend pour Visual Studio. Toutefois, chacun de ces produits de famille peut avoir ses propres paramètres, lesquels ne sont pas partagés avec Visual Studio. Par exemple, les paramètres spécifiques à Blend pour Visual Studio sur l’ordinateur « A » ne sont pas partagés avec Visual Studio sur les ordinateurs « A » ou « B ».

## <a name="side-by-side-synchronized-settings"></a>Paramètres synchronisés côte à côte

Dans Visual Studio 2017 version 15.3 et ultérieure, certains paramètres tels que la disposition de la fenêtre Outil ne sont pas partagés entre les différentes installations côte à côte de Visual Studio 2017. Le fichier *CurrentSettings.vssettings* dans *%userprofile%\Documents\Visual Studio 2017\Settings* se trouve dans un dossier spécifique à l’installation semblable à *%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx\Settings*.

> [!NOTE]
> Pour utiliser les nouveaux paramètres spécifiques à l’installation, effectuez une nouvelle installation. Quand vous effectuez une mise à niveau d’une installation existante de Visual Studio 2017 vers la mise à jour la plus récente, elle utilise l’emplacement partagé existant.

Si vous disposez d’installations côte à côte de Visual Studio 2017 et si vous souhaitez utiliser le nouvel emplacement du fichier de paramètres spécifiques à l’installation, effectuez les étapes suivantes :

1. Effectuez une mise à niveau vers Visual Studio 2017 version 15.3 ou ultérieure.

1. Utilisez l’Assistant **Importation et exportation de paramètres** pour exporter tous vos paramètres existants vers un emplacement situé en dehors du dossier *%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx*.

1. Ouvrez l’**Invite de commandes développeur pour VS 2017** correspondant à l’installation mise à niveau de Visual Studio, puis exécutez `devenv /resetuserdata`.

1. Lancez Visual Studio et importez les paramètres enregistrés du fichier de paramètres exportés.

## <a name="see-also"></a>Voir aussi

- [Personnaliser l’IDE](../ide/personalizing-the-visual-studio-ide.md)
- [Paramètres d’environnement](../ide/environment-settings.md)
- [Environnement > Comptes, boîte de dialogue Options](reference/accounts-environment-options-dialog-box.md)
