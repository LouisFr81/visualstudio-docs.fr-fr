---
title: Problèmes connus liés aux conteneurs
description: Découvrez les problèmes connus susceptibles de se produire quand vous installez Visual Studio Build Tools 2017 dans un conteneur Windows.
ms.date: 04/18/2018
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f1fdfcc71f2bd17bf8ab4be0796350799af2c35
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55935015"
---
# <a name="known-issues-for-containers"></a>Problèmes connus liés aux conteneurs

Quelques problèmes nous ont été signalés concernant l’installation de Visual Studio dans un conteneur Docker.

## <a name="windows-container"></a>Conteneur Windows

Les problèmes suivants se produisent lorsque vous installez Visual Studio Build Tools 2017 dans un conteneur Windows.

* Vous ne pouvez pas installer Visual Studio dans un conteneur basé sur l’image microsoft/windowsservercore:10.0.14393.1593. Les images marquées avec des versions de Windows antérieures ou ultérieures à la version 10.0.14393 doivent normalement fonctionner.
* Vous ne pouvez pas installer le SDK Windows 10.0.14393 ou version ultérieure. Certains packages ne peuvent pas être installés, si bien que les charges de travail qui en dépendent ne peuvent pas fonctionner.
* Passez `-m 2GB` (ou plus) au moment de la génération de l’image. L’installation de certaines charges de travail nécessite plus de mémoire que la valeur par défaut (1 Go).
* Configurez Docker pour utiliser des disques ayant une capacité supérieure à la valeur par défaut (20 Go).
* Passez `--norestart` sur la ligne de commande. Au moment de la rédaction de cet article, le redémarrage d’un conteneur Windows au sein même de celui-ci retourne `ERROR_TOO_MANY_OPEN_FILES` à l’hôte.
* Si vous basez votre image directement sur microsoft/windowsservercore, l’installation du .NET Framework risque de ne pas s’effectuer correctement. De plus, aucune erreur d’installation ne sera signalée. Le code managé risque de ne pas s’exécuter, une fois l’installation effectuée. Basez plutôt votre image sur [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) ou une version ultérieure. Par exemple, vous pouvez voir s’afficher l’erreur suivante durant la génération avec MSBuild :

  > C:\BuildTools\MSBuild\15.0\bin\Roslyn\Microsoft.CSharp.Core.targets(84,5) : erreur MSB6003 : L’exécutable de tâche spécifié, « csc.exe », n’a pas pu être exécuté. Impossible de charger le fichier ou l’assembly 'System.IO.FileSystem, Version=4.0.1.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a', ou l’une de ses dépendances. Le système ne trouve pas le fichier spécifié.

* Vous ne pouvez pas installer Visual Studio 2017 version 15.8 ou antérieure (n’importe quel produit) sur mcr<span></span>.microsoft.com/windows/servercore:1809 ou version ultérieure. Pour plus d'informations, voir https://aka.ms/setup/containers/servercore1809.

## <a name="build-tools-container"></a>Conteneur Build Tools

Les problèmes connus suivants peuvent se produire lorsque vous utilisez un conteneur Build Tools. Pour voir si des problèmes ont été résolus ou s’il existe d’autres problèmes connus, rendez-vous sur le site https://developercommunity.visualstudio.com.

* L’utilisation d’IntelliTrace au sein d’un conteneur peut ne pas fonctionner dans [certains scénarios](https://github.com/Microsoft/vstest/issues/940).

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Voir aussi

* [Installer les outils de génération dans un conteneur](build-tools-container.md)
* [Exemple avancé pour les conteneurs](advanced-build-tools-container.md)
* [ID de composant et de charge de travail de Visual Studio Build Tools 2017](workload-component-id-vs-build-tools.md)
