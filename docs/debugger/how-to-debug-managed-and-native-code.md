---
title: 'Tutoriel : Déboguer du code C# et C++ (mode mixte)'
description: Découvrez comment déboguer une DLL native d’une application .NET Core ou .NET Framework avec le débogage en mode mixte
ms.custom: seodec18
ms.date: 11/02/2018
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- mixed mode debugging
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: c9bdc4afb0d5f2b9f9f4ae0385b63372644929f8
ms.sourcegitcommit: 0f7411c1a47d996907a028e920b73b53c2098c9f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55690240"
---
# <a name="tutorial-debug-c-and-c-in-the-same-debugging-session"></a>Tutoriel : Déboguer du code C# et C++ dans la même session de débogage

Visual Studio vous permet d’activer plusieurs types de débogueur dans une session de débogage, qui est appelée « débogage en mode mixte ». Dans ce tutoriel, vous découvrez comment déboguer du code managé et du code natif dans une même session de débogage. 

Ce tutoriel montre comment déboguer le code natif d’une application managée, mais vous pouvez également [déboguer le code managé d’une application native](../debugger/how-to-debug-in-mixed-mode.md). Le débogueur prend également en charge d’autres types de débogage en mode mixte, comme le débogage [de code Python et de code natif](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md), ainsi que l’utilisation du débogueur de script dans des types d’applications comme ASP.NET.

Dans ce didacticiel, vous allez effectuer les actions suivantes :

> [!div class="checklist"]
> * Créer une DLL native simple
> * Créer une application .NET Core ou .NET Framework simple pour appeler la DLL
> * Configurer le débogage en mode mixte
> * Démarrer le débogueur
> * Atteindre un point d’arrêt dans l’application managée
> * Effectuer un pas à pas détaillé dans le code natif

## <a name="prerequisites"></a>Prérequis

Vous devez disposer de Visual Studio avec les charges de travail suivantes :
- **Développement Desktop avec C++**
- **Développement .NET Desktop** ou **Développement multiplateforme .NET Core**, selon le type d’application que vous voulez créer.

Si vous n’avez pas Visual Studio, accédez à la page  [Téléchargements de Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)  pour l’installer gratuitement.

Si vous disposez d’une version installée de Visual Studio, mais que vous n’avez pas les charges de travail nécessaires, sélectionnez **Ouvrir Visual Studio Installer** dans le volet gauche de la boîte de dialogue **Nouveau projet**. Dans Visual Studio Installer, sélectionnez les charges de travail nécessaires, puis sélectionnez **Modifier**.

## <a name="create-a-simple-native-dll"></a>Créer une DLL native simple

**Pour créer les fichiers du projet de DLL :**

1. Dans Visual Studio, sélectionnez **Fichier** > **Nouveau** > **Projet**.

1. Dans la boîte de dialogue **Nouveau projet**, sous **Visual C++**, sélectionnez **Autres**, puis sélectionnez **Projet vide** dans le volet central.

1. Dans le champ **Nom**, tapez **Mixed_Mode_Debugging**, puis sélectionnez **OK**.

   Visual Studio crée le projet vide et l’affiche dans **l’Explorateur de solutions**.

1. Dans **l’Explorateur de solutions**, sélectionnez **Fichiers sources**, puis sélectionnez **Projet** > **Ajouter un nouvel élément**. Vous pouvez aussi cliquer avec le bouton droit sur **Fichiers sources** et sélectionner **Ajouter** > **Nouvel élément**. 

1. Dans la boîte de dialogue **Nouvel élément**, sélectionnez **Fichier C++ (.cpp)**. Tapez **Mixed_Mode.cpp** dans le champ **Nom**, puis sélectionnez **Ajouter**.

    Visual Studio ajoute le nouveau fichier C++ à **l’Explorateur de solutions**.

1. Copiez le code suivant dans *Mixed_Mode.cpp* :

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. Dans **l’Explorateur de solutions**, sélectionnez **Fichiers d’en-tête**, puis sélectionnez **Projet** > **Ajouter un nouvel élément**. Vous pouvez aussi cliquer avec le bouton droit sur **Fichiers d’en-tête** et sélectionner **Ajouter** > **Nouvel élément**. 

1. Dans la boîte de dialogue **Nouvel élément**, sélectionnez **Fichier d’en-tête (.h)**. Tapez **Mixed_Mode.h** dans le champ **Nom**, puis sélectionnez **Ajouter**.

   Visual Studio ajoute le nouveau fichier d’en-tête à **l’Explorateur de solutions**.

1. Copiez le code suivant dans *Mixed_Mode.h* :

    ```cpp
    #ifndef MIXED_MODE_MULTIPLY_HPP
    #define MIXED_MODE_MULTIPLY_HPP

    extern "C"
    {
        __declspec(dllexport) int __stdcall mixed_mode_multiply(int a, int b) {
            return a * b;
        }
    }
    #endif
    ```

1. Sélectionnez **Fichier** > **Enregistrer tout** ou appuyez sur **Ctrl**+**Maj**+**S** pour enregistrer les fichiers.

**Pour configurer et générer le projet DLL :**

1. Dans la barre d’outils de Visual Studio, sélectionnez la configuration **Débogage** et la plateforme **x86** ou **x64**. Si votre application appelante est .NET Core, qui s’exécute toujours en mode 64 bits, sélectionnez **x64** comme plateforme.

1. Dans **l’Explorateur de solutions**, sélectionnez le nœud du projet **Mixed_Mode_Debugging** et sélectionnez l’icône **Propriétés**, ou cliquez avec le bouton droit sur le nœud du projet et sélectionnez **Propriétés**.

1. En haut du volet **Propriétés**, vérifiez que **Configuration** est défini sur **Active (Déboguer)** et que la **Plateforme** est identique à ce que vous avez défini dans la barre d’outils : **x64**, ou **Win32** pour la plateforme x86. 

   > [!IMPORTANT]
   > Si vous faites passer la plateforme de **x86** à **x64** ou vice versa, vous devez reconfigurer les propriétés pour la nouvelle plateforme. 

1. Sous **Propriétés de configuration** dans le volet gauche, sélectionnez **Éditeur de liens** > **Avancé** et, dans la liste déroulante en regard de **Aucun point d’entrée**, sélectionnez **Non**. Si vous avez dû le changer en **Non**, sélectionnez **Appliquer**.

1. Sous **Propriétés de configuration**, sélectionnez **Général** et, dans la liste déroulante en regard de **Type de configuration**, sélectionnez **Bibliothèque dynamique (.dll)**. Sélectionnez **Appliquer**, puis **OK**.

   ![Passer à une DLL native](../debugger/media/mixed-mode-set-as-native-dll.png)

1. Sélectionnez le projet dans **l’Explorateur de solutions**, puis sélectionnez **Générer** > **Générer la solution**, appuyez sur **F7**, ou cliquez avec le bouton droit sur le projet et sélectionnez **Générer**.

   Le projet doit être généré sans erreur.

## <a name="create-a-simple-managed-app-to-call-the-dll"></a>Créer une application managée simple pour appeler la DLL

1. Dans Visual Studio, choisissez **Fichier** > **Nouveau** > **Projet**.

   > [!NOTE]
   > Bien que vous puissiez aussi ajouter le nouveau projet managé à votre solution C++ existante, la création d’une nouvelle solution prend en charge plus de scénarios de débogage.

1. Dans la boîte de dialogue **Nouveau projet**, sélectionnez **Visual C#**  et, dans le volet central :

   - Pour une application .NET Framework, sélectionnez **Application console (.NET Framework)**.
   
   - Pour une application .NET Core, sélectionnez **Application console (.NET Core)**.

1. Dans le champ **Nom**, tapez **Mixed_Mode_Calling_App**, puis sélectionnez **OK**.

   Visual Studio crée le projet vide et l’affiche dans **l’Explorateur de solutions**.

1. Remplacez tout le code de *Program.cs* par le code suivant :

    ```csharp
    using System;
    using System.Runtime.InteropServices;

    namespace Mixed_Mode_Calling_App
    {
        public class Program
        {
            // Replace the file path shown here with the
            // file path on your computer. For .NET Core, the typical (default) path
            // for a 64-bit DLL might look like this:
            // C:\Users\username\source\repos\Mixed_Mode_Debugging\x64\Debug\Mixed_Mode_Debugging.dll
            // Here, we show a typical path for a DLL targeting the **x86** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed_Mode_Debugging\Debug\Mixed_Mode_Debugging.dll", EntryPoint =
            "mixed_mode_multiply", CallingConvention = CallingConvention.StdCall)]
            public static extern int Multiply(int x, int y);
            public static void Main(string[] args)
            {
                int result = Multiply(7, 7);
                Console.WriteLine("The answer is {0}", result);
                Console.ReadKey();
            }
        }
    }
    ```

1. Dans le nouveau code, remplacez le chemin de fichier dans `[DllImport]` par votre chemin de fichier vers *Mixed_Mode_Debugging.dll* que vous venez de créer. Consultez le commentaire du code pour des conseils. Veillez à remplacer l’espace réservé *username* (nom d’utilisateur).

1. Sélectionnez **Fichier** > **Enregistrer Program.cs** ou appuyez sur **Ctrl**+**S** pour enregistrer le fichier.

## <a name="configure-mixed-mode-debugging"></a>Configurer le débogage en mode mixte 

### <a name="to-configure-mixed-mode-debugging-for-a-net-framework-app"></a>Pour configurer le débogage en mode mixte pour une application .NET Framework 

1. Dans **l’Explorateur de solutions**, sélectionnez le nœud du projet **Mixed_Mode_Calling_App** et sélectionnez l’icône **Propriétés**, ou cliquez avec le bouton droit sur le nœud du projet et sélectionnez **Propriétés**.

1. Sélectionnez **Déboguer** dans le volet gauche, cochez la case **Activer le débogage du code natif**, puis fermez la page des propriétés pour enregistrer les modifications.

    ![Activer le débogage en mode mixte](../debugger/media/mixed-mode-enable-native-code-debugging.png)

### <a name="to-configure-mixed-mode-debugging-for-a-net-core-app"></a>Pour configurer le débogage en mode mixte pour une application .NET Core 

Dans la plupart des versions de Visual Studio 2017, vous devez utiliser le fichier *launchSettings.json* au lieu des propriétés du projet pour activer le débogage en mode mixte pour le code natif dans une application .NET Core. Pour effectuer le suivi des mises à jour de l’interface utilisateur pour cette fonctionnalité, consultez ce [problème GitHub](https://github.com/dotnet/project-system/issues/1125).

1. Dans **l’Explorateur de solutions**, développez **Propriétés**, puis ouvrez le fichier *launchSettings.json*. 

   >[!NOTE]
   >Par défaut, *launchSettings.json* se trouve dans *C:\Users\username\source\repos\Mixed_Mode_Calling_App\Properties*. Si *launchSettings.json* n’existe pas, sélectionnez le nœud du projet **Mixed_Mode_Calling_App** dans **l’Explorateur de solutions**, puis sélectionnez l’icône **Propriétés**, ou cliquez avec le bouton droit sur le projet et sélectionnez **Propriétés**. Faites une modification temporaire dans l’onglet **Déboguer** et générez le projet. Ceci crée un fichier *launchSettings.json*. Annulez la modification que vous avez apportée dans l’onglet **Déboguer**.

1. Dans le fichier *lauchsettings.json*, ajoutez la ligne suivante :

    ```csharp
    "nativeDebugging": true
    ```

    Le fichier complet se présente alors comme l’exemple suivant :

    ```csharp
    {
      "profiles": {
        "Mixed_Mode_Calling_App": {
          "commandName": "Project",
          "nativeDebugging": true
        }
      }
    }
    ```

## <a name="set-a-breakpoint-and-start-debugging"></a>Définir un point d’arrêt et démarrer le débogage

1. Dans le projet C#, ouvrez *Program.cs*. Définissez un point d’arrêt sur la ligne de code suivante en cliquant dans la marge de gauche, en sélectionnant la ligne et en appuyant sur **F9**, ou en cliquant avec le bouton droit sur la ligne et en sélectionnant **Point d’arrêt**  > **Insérer un point d’arrêt**.

    ```csharp
    int result = Multiply(7, 7);
    ```

    Un cercle rouge apparaît là dans la marge gauche où vous avez défini le point d’arrêt.

1. Appuyez sur **F5**, sélectionnez la flèche verte dans la barre d’outils de Visual Studio, ou sélectionnez **Déboguer** > **Démarrer le débogage** pour démarrer le débogage.

   Le débogueur se met en pause sur point d’arrêt que vous avez défini. Une flèche jaune indique l’endroit où le débogueur est actuellement en pause.

## <a name="step-in-and-out-of-native-code"></a>Effectuer un pas à pas détaillé et un pas à pas sortant du code natif

1. Avec le débogage en pause dans l’application managée, appuyez sur **F11** ou sélectionnez **Déboguer** > **Pas à pas détaillé**.

   Le fichier d’en-tête natif *Mixed_Mode.h* s’ouvre et vous voyez la flèche jaune où le débogueur est en pause.

   ![Effectuer un pas à pas détaillé dans du code natif](../debugger/media/mixed-mode-step-into-native-code.png)

1. Vous pouvez maintenant définir et atteindre des points d’arrêt, et inspecter les variables dans le code natif ou dans le code managé.

   - Placez le curseur sur des variables dans le code source pour voir leur valeur.

   - Examinez des variables et leur valeur dans les fenêtres **Automatique** et **Variables locales**.

   - Avec le débogueur en pause, vous pouvez également utiliser la fenêtre **Espion** et la fenêtre **Pile des appels**.

1. Appuyez à nouveau sur **F11** pour faire avancer le débogueur d’une ligne.

1. Appuyez sur **Maj**+**F11** ou sélectionnez **Déboguer** > **Pas à pas sortant** pour continuer l’exécution et placer à nouveau le débogueur en pause dans l’application managée.

1. Appuyez sur **F5** ou sélectionnez la flèche verte pour continuer le débogage de l’application.

Félicitations ! Vous avez terminé le didacticiel sur le débogage en mode mixte.

## <a name="next-step"></a>Étape suivante

Dans ce didacticiel, vous avez découvert comment déboguer du code natif à partir d’une application managée en activant le débogage en mode mixte. Pour une vue d’ensemble des autres fonctionnalités du débogueur, consultez :

> [!div class="nextstepaction"]
> [Présentation du débogueur](../debugger/debugger-feature-tour.md)
