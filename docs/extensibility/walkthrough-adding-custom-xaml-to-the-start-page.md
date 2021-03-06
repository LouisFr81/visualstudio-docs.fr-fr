---
title: 'Procédure pas à pas : Ajout de XAML personnalisé à la Page de démarrage | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: 992937ea0c90e3734a38ba6f2e56b19918fd7375
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709172"
---
# <a name="walkthrough-add-custom-xaml-to-the-start-page"></a>Procédure pas à pas : Ajoutez le XAML personnalisé à la page de démarrage

Cette procédure pas à pas montre comment créer une page de démarrage personnalisée Visual Studio qui contient un navigateur Web.

## <a name="add-custom-xaml"></a>Ajoutez le XAML personnalisé

1.  Créer une page de démarrage en suivant les instructions dans [créer une page de démarrage personnalisée](../extensibility/creating-a-custom-start-page.md).

2.  Dans le *MainWindow.xaml* de fichiers, recherchez le \<grille > section.

3.  Ajouter un \<TabControl > élément et un \<TabItem > à l’intérieur de la \< grille > élément, comme indiqué dans l’exemple suivant.

    ```xml
    <Grid>
        <TabControl>
            <TabItem Header="Bing" Height="Auto">
                <Frame Source="http://www.bing.com" />
            </TabItem>
        </TabControl>
    </Grid>
    ```

4.  Ajoutez une deuxième \<TabItem >, avec un \<bouton > élément qui ouvre un nouveau projet :

    ```xml
    <Grid>
        <TabControl>
            <TabItem Header="MyButton" Height="Auto">
                <Button Name="btnNewProj" Content="New Project"
                    Command="{x:Static vscom:VSCommands.ExecuteCommand}"
                    CommandParameter="File.NewProject" >
                </Button>
            </TabItem>
            <TabItem Header="Bing" Height="Auto">
                <Frame Source="http://www.bing.com" />
            </TabItem>
        </TabControl>
    </Grid>
    ```

## <a name="test-the-custom-start-page"></a>Tester la page de démarrage personnalisée

1.  Appuyez sur **F5**.

     L’instance expérimentale de Visual Studio s’ouvre, avec la page de démarrage personnalisée installée mais ne pas sélectionnée.

2.  Dans l’instance expérimentale de Visual Studio, ouvrez le **Outils /Options / environnement** page.

3.  Sélectionnez **démarrage**. Sur le **personnaliser la Page de démarrage** liste, sélectionnez votre *.xaml* de fichiers, puis cliquez sur **OK**.

4.  Dans le menu **Affichage** , cliquez sur **Page de démarrage**.

5.  Cliquez sur le **Bing** onglet.

     Vous devez voir une page web de Bing.

6.  Cliquez sur le **MyButton** onglet.

     Vous devez voir un **MonProjet** bouton, ce qui ouvre le **nouveau projet** boîte de dialogue.

7.  Fermez l’instance expérimentale.

Pour appliquer la page de démarrage personnalisée dans **outils** > **Options** > **environnement**, sélectionnez **démarrage**. Sur le **personnaliser la Page de démarrage** liste, sélectionnez votre *.xaml* de fichiers, puis cliquez sur **OK**.

## <a name="next-steps"></a>Étapes suivantes

La page de démarrage de Visual Studio propose désormais un onglet qui affiche un onglet de navigateur Web et un onglet MyButton. Vous pouvez créer des pages de démarrage personnalisées qui ont d’autres fonctionnalités à l’aide de la *code-behind* modèle pour ajouter un fichier .dll personnalisé, comme illustré dans [ajouter le contrôle utilisateur à la Page de démarrage](../extensibility/adding-user-control-to-the-start-page.md). Vous pouvez partager des pages de démarrage personnalisées avec d’autres utilisateurs en publiant le fichier .vsix résultant de la [galerie Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) site Web, ou vers un autre site Web ou réseau de partage. Pour plus d’informations, consultez [Deploying Custom Start Pages](../extensibility/deploying-custom-start-pages.md).

## <a name="see-also"></a>Voir aussi

- [Personnaliser la page de démarrage](../ide/customizing-the-start-page-for-visual-studio.md)
- [Conteneur des contrôles WPF](https://msdn.microsoft.com/library/a0177167-d7db-4205-9607-8ae316952566)