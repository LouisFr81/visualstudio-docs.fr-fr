﻿---
title: 'Procédure : Déboguer en Mode mixte | Microsoft Docs'
ms.date: 11/05/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e1da9b01c32b82948718ef5045005eb0d9beb37
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54968529"
---
# <a name="how-to-debug-in-mixed-mode-c-c-visual-basic"></a>Procédure : Déboguer en mode mixte (C#, C++, Visual Basic)

Les procédures suivantes décrivent comment activer le débogage de code managé et natif simultanément, également appelé en mode mixte. Il existe deux scénarios de débogage en mode mixte :

- L’application qui appelle une DLL est écrite en code natif, et la DLL est gérée.

- L’application qui appelle une DLL est écrite en code managé, et la DLL est en code natif. Pour obtenir un didacticiel qui vous guide tout au long de ce scénario plus en détail, consultez [déboguer le code managé et natif](../debugger/how-to-debug-managed-and-native-code.md).

Vous pouvez activer les débogueurs managés et natifs dans le projet application appelant **propriété** pages. Les paramètres diffèrent entre les applications natives et managées.

Si vous n’avez pas accès au projet de l’appel d’une application, vous pouvez déboguer la DLL à partir du projet DLL. Vous n’avez pas besoin en mode mixte pour déboguer uniquement le projet DLL. Pour plus d'informations, voir [Procédure : Déboguer à partir d’un projet DLL](../debugger/how-to-debug-from-a-dll-project.md).

> [!NOTE]
> Les boîtes de dialogue et les commandes que vous voyez peuvent différer de ceux de cet article, en fonction de vos paramètres Visual Studio ou votre édition. Pour modifier vos paramètres, choisissez **outils** > **importation et exportation de paramètres**. Pour plus d’informations, consultez [Réinitialiser les paramètres](../ide/environment-settings.md#reset-settings).

## <a name="enable-mixed-mode-debugging-for-a-native-calling-app"></a>Activer le débogage en mode mixte pour une application d’appel native

1. Sélectionnez le projet C++ dans **l’Explorateur de solutions** et cliquez sur le **propriétés** icône, appuyez sur **Alt**+**entrée**, ou avec le bouton droit et choisissez **propriétés**.

1. Dans le  **\<projet > Pages de propriétés** boîte de dialogue, développez **propriétés de Configuration**, puis sélectionnez **débogage**.

1. Définissez **Type de débogueur** sur **Mixte** ou **Automatique**.

1. Sélectionnez **OK**.

   ![Activer le débogage en mode mixte](../debugger/media/dbg-mixed-mode-from-native.png "activer le débogage en mode mixte")

## <a name="enable-mixed-mode-debugging-for-a-managed-calling-app"></a>Activer le débogage en mode mixte pour une application gérée par appelante

1. Sélectionnez le C# ou un projet Visual Basic dans **l’Explorateur de solutions** et sélectionnez le **propriétés** icône, appuyez sur **Alt**+**entrée**, ou avec le bouton droit et choisissez **propriétés**.

1. Sélectionnez le **déboguer** onglet, puis sélectionnez **activer le débogage du code natif**.

1. Fermez la page de propriétés pour enregistrer les modifications.

   ![Activer le débogage du code natif](../debugger/media/dbg-mixed-mode-from-csharp.png "activer le débogage du code natif")

> [!NOTE]
> Dans la plupart des versions de Visual Studio 2017, vous devez utiliser le fichier *launchSettings.json* au lieu des propriétés du projet pour activer le débogage en mode mixte pour le code natif dans une application .NET Core. Pour plus d’informations, consultez [déboguer le code managé et natif](../debugger/how-to-debug-managed-and-native-code.md).

## <a name="see-also"></a>Voir aussi

- [Guide pratique pour déboguer à partir d’un projet DLL](../debugger/how-to-debug-from-a-dll-project.md)