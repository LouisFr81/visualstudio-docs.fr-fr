---
title: Guide pratique pour faire migrer et publier une application web sur un service cloud Azure
description: Découvrez comment migrer et publier une application web sur un service cloud Azure à partir de Visual Studio
author: ghogen
manager: jillfra
ms.assetid: 9394adfd-a645-4664-9354-dd5df08e8c91
ms.custom: seodec18
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/10/2017
ms.author: ghogen
ms.openlocfilehash: bb470e245f41bc83245d8c2234753ad84c0ee8db
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936302"
---
# <a name="how-to-migrate-and-publish-a-web-application-to-an-azure-cloud-service-from-visual-studio"></a>Procédure : Migrer et publier une application web sur un service cloud Azure à partir de Visual Studio

Pour tirer parti des services d’hébergement et de l’extensibilité d’Azure, vous pouvez migrer et déployer votre application web sur un service cloud Azure. Seules de légères modifications sont nécessaires. Cet article couvre le déploiement dans des services cloud uniquement ; pour App Service, voir [Déployer une application web dans Azure App Service](/azure/app-service/app-service-deploy-local-git).

> [!Important]
> Cette migration est uniquement prise en charge pour les projets spécifiques ASP.NET, Silverlight, WCF et WCF Workflow. Elle n'est pas prise en charge pour les projets ASP.NET Core. Voir [Modèles de projet pris en charge](#supported-project-templates).

## <a name="migrate-a-project-to-cloud-services"></a>Migration d'un projet vers des services cloud

1. Cliquez avec le bouton droit sur le projet d'application web et sélectionnez **Convertir > Convertir en projet de service cloud Microsoft Azure**. (Notez que cette commande n’apparaît pas si vous avez déjà un projet de rôle web dans la solution.)
1. Visual Studio crée un projet de service cloud dans la solution qui contient le rôle web requis. Le nom de ce projet est le même que celui de votre projet d'application, avec le suffixe `.Azure`.
1. Visual Studio définit également la propriété **Copie locale** sur vrai pour tous les assemblys qui sont nécessaires pour MVC 2, MVC 3, MVC 4 et Silverlight Business Applications. Cette propriété ajoute ces assemblys au package de services qui est utilisé pour le déploiement.

   > [!Important]
   > Si vous avez d’autres assemblys ou fichiers qui sont requis pour cette application web, vous devez définir manuellement les propriétés de ces fichiers. Pour plus d’informations sur la configuration de ces propriétés, consultez [Inclure des fichiers dans le package de services](#include-files-in-the-service-package).

### <a name="errors-and-warnings"></a>Erreurs et avertissements

Les avertissements ou erreurs qui se produisent indiquent les problèmes à résoudre avant le déploiement sur Azure, par exemple des assemblys manquants.

Si vous générez votre application, si vous l’exécutez localement à l’aide de l’émulateur de calcul ou si vous la publiez sur Azure, vous pouvez voir l’erreur suivante : « Le chemin d’accès spécifié, le nom de fichier ou les deux sont trop longs. » Cette erreur indique que la longueur du nom qualifié complet du projet Azure dépasse 146 caractères. Pour résoudre le problème, déplacez votre solution vers un autre dossier avec un chemin d'accès plus court.

Pour plus d’informations sur la façon de traiter les avertissements comme des erreurs, consultez [Configurer un projet de service cloud Azure avec Visual Studio](vs-azure-tools-configuring-an-azure-project.md).

### <a name="test-the-migration-locally"></a>Test local de la migration

1. Dans Visual Studio, dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le projet de service mobile ajouté, puis sélectionnez **Définir comme projet de démarrage**.
1. Sélectionnez **Déboguer > Démarrer le débogage** (F5) pour lancer l'environnement de débogage Azure. Cet environnement fournit spécifiquement l'émulation des divers services Azure.

### <a name="use-an-azure-sql-database-for-your-application"></a>Utilisation d’une base de données SQL Azure pour votre application

Si vous avez une chaîne de connexion pour votre application web qui utilise une base de données SQL Server sur site, vous devez migrer votre base de données vers Azure SQL Database et mettre à jour votre chaîne de connexion. Pour plus d'informations sur ce processus, consultez les rubriques suivantes :

- [Migration de base de données SQL Server vers SQL Database dans le cloud](/azure/sql-database/sql-database-cloud-migrate)
- [Utilisation de NET (C#) avec Visual Studio pour se connecter à une base de données SQL Azure et l’interroger](/azure/sql-database/sql-database-connect-query-dotnet-visual-studio).

## <a name="publish-the-application-to-azure-cloud-service"></a>Publication de l'application sur un service cloud Azure

1. Créez le service cloud et les comptes de stockage nécessaires dans votre abonnement Azure, comme indiqué dans [Préparer la publication ou le déploiement d’une application Azure à partir de Visual Studio](vs-azure-tools-cloud-service-publish-set-up-required-services-in-visual-studio.md).
1. Dans Visual Studio, cliquez avec le bouton droit sur le projet d'application et sélectionnez **Publier sur Microsoft Azure...** (ce qui est différent de la commande « Publier... »).
1. Dans la fenêtre **Publication d'application Azure** qui s'affiche, connectez-vous à l'aide du compte de votre abonnement Azure puis sélectionnez **Suivant >**.
1. Dans l'onglet **Paramètres > Paramètres communs**, sélectionnez le service cloud cible dans la liste déroulante **Service cloud** ainsi que l'environnement et les configurations de votre choix.
1. Dans **Paramètres > Paramètres avancés**, choisissez le compte de stockage à utiliser, puis sélectionnez **Suivant >**.
1. Dans **Diagnostics**, indiquez si vous souhaitez envoyer les informations à Application Insights.
1. Sélectionnez **Suivant >** pour afficher un résumé, puis sélectionnez **Publier** pour lancer le déploiement.
1. Visual Studio ouvre une fenêtre du journal d'activité dans laquelle vous pouvez suivre la progression :

    ![VST_AzureActivityLog](./media/vs-azure-tools-migrate-publish-web-app-to-cloud-service/IC744149.png)

1. (Facultatif) Pour annuler le processus de déploiement, cliquez avec le bouton droit sur la ligne dans le journal des activités, puis choisissez **Annuler et supprimer**. Cette commande arrête le processus de déploiement et supprime l'environnement de déploiement d'Azure. Remarque : pour supprimer cet environnement de déploiement après son déploiement, vous devez utiliser le [portail Azure](https://portal.azure.com).
1. (Facultatif) Une fois vos instances de rôle démarrées, Visual Studio affiche automatiquement l’environnement de déploiement dans le nœud **Explorateur de serveurs > Services cloud**. À partir de là, vous pouvez consulter l'état de chaque instance de rôle.
1. Pour accéder à votre application après le déploiement, cliquez sur la flèche en regard de votre déploiement quand le statut **Terminé** s’affiche dans le **journal des activités Azure** avec l'URL. Consultez le tableau suivant pour plus d'informations sur le démarrage d'un type spécifique de l'application web à partir d’Azure.

## <a name="using-the-compute-emulator-and-starting-application-in-azure"></a>Utilisation de l'émulateur de calcul et démarrage de l'application dans Azure

Tous les types d'applications peuvent être démarrés dans un navigateur connecté au débogueur Visual Studio en sélectionnant **Déboguer > Démarrer le débogage** (F5). Avec un projet d'application web ASP.NET vide, vous devez d'abord ajouter une page `.aspx` à votre application puis la définir comme page de démarrage pour votre projet web.

Le tableau suivant fournit des détails sur le démarrage de l'application dans Azure :

   | Type d’application web | Exécution dans Azure |
   | --- | --- | --- |
   | Application web ASP.NET<br/>(y compris MVC 2, MVC 3, MVC 4) | Sélectionnez l'URL dans l'onglet **Déploiement** du **journal d'activité Azure**. |
   | Application Web vide ASP.NET | Si vous utilisez une page `.aspx` par défaut dans votre application, sélectionnez l'URL dans l'onglet **Déploiement** du **journal d'activité Azure**. Pour accéder à une autre page, entrez une URL au format suivant dans un navigateur : `<deployment_url>/<page_name>.aspx` |
   | Application Silverlight<br/>Silverlight Business Application<br/>Silverlight Navigation Application | Accédez à la page spécifique de votre application en utilisant le format d'URL suivant : `<deployment_url>/<page_name>.aspx` |
    Application de service WCF<br/>Application de service de workflow WCF | Définissez le fichier `.svc` comme page de démarrage de votre projet de service WCF. Puis accédez à `<deployment_url>/<service_file>.svc` |
   | ASP.NET Dynamic Entities<br/>ASP.NET Dynamic Data Linq to SQL | Mettez à jour la chaîne de connexion comme décrit dans la section suivante. Puis accédez à `<deployment_url>/<page_name>.aspx`. Pour Linq to SQL, vous devez utiliser une base de données Azure SQL. |

## <a name="update-a-connection-string-for-aspnet-dynamic-entities"></a>Mise à jour d’une chaîne de connexion pour ASP.NET Dynamic Entities

1. Créez une base de données SQL Azure pour une application web ASP.NET Dynamic Entities comme décrit précédemment dans (#use-an-azuresql-database-for-your-application).
1. Ajoutez les tables et les champs dont vous avez besoin pour cette base de données à partir du portail Azure.
1. Spécifiez une chaîne de connexion dans le fichier `web.config` au format suivant, puis enregistrez le fichier :

    ```xml
    <add name="tempdbEntities"
     connectionString="metadata=res://*/Model1.csdl|res://*/Model1.ssdl|res://*/Model1.msl;provider=System.Data.SqlClient;provider connection string=&quot;data source=<server name>\SQLEXPRESS;initial catalog=<database name>;integrated security=True;multipleactiveresultsets=True;App=EntityFramework&quot;"
     providerName="System.Data.EntityClient"/>
    ```

    Mettez à jour la valeur *connectionString* avec la chaîne de connexion ADO.NET pour votre base de données SQL Azure comme suit :

    ```xml
    <add name="tempdbEntities"
     connectionString="metadata=res://*/Model1.csdl|res://*/Model1.ssdl|res://*/Model1.msl;provider=System.Data.SqlClient;provider connection string=&quot;Server=tcp:<SQL Azure server name>.database.windows.net,1433;Database=<database name>;User ID=<user name>;Password=<password>;Trusted_Connection=False;Encrypt=True;multipleactiveresultsets=True;App=EntityFramework&quot;"
     providerName="System.Data.EntityClient"/>
    ```

## <a name="supported-project-templates"></a>Modèles de projet pris en charge

Les applications qui peuvent être migrées et publiées sur des services cloud doivent utiliser l'un des modèles du tableau ci-dessous. ASP.NET Core n'est pas pris en charge.

| Groupe de modèles | Modèle de projet |
| --- | --- |
| Web | Application Web ASP.NET (.NET Framework) |
| Web | Application Web ASP.NET MVC 2 |
| Web | Application Web ASP.NET MVC 3 |
| Web | Application Web ASP.NET MVC 4 |
| Web | Application Web vide ASP.NET (ou site) |
| Web | Application Web vide ASP.NET MVC 2 |
| Web | Application Web ASP.NET Dynamic Data Entities |
| Web | Application Web ASP.NET Dynamic Data Linq to SQL |
| Silverlight | Application Silverlight |
| Silverlight | Silverlight Business Application |
| Silverlight | Silverlight Navigation Application |
| WCF | WCF Service Application |
| WCF | Application de service de workflow WCF |
| Workflow | Application de service de workflow WCF |

## <a name="next-steps"></a>Étapes suivantes

- [Préparer la publication ou le déploiement d’une application Azure à partir de Visual Studio](vs-azure-tools-cloud-service-publish-set-up-required-services-in-visual-studio.md)
- [Configuration des informations d’authentification nommées](vs-azure-tools-setting-up-named-authentication-credentials.md).
