---
title: IntelliTrace | Documents de Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.historicaldebug.overview
helpviewer_keywords:
- debugger, recording execution history
- debugging, recording execution history
- IntelliTrace [Visual Studio ALM]
- IntelliTrace, debugging applications
- debugger, (See also IntelliTrace [Visual Studio ALM])
- debugging, (See also IntelliTrace [Visual Studio ALM])
- IntelliTrace, collecting data from Test Manager
- IntelliTrace
- Test Manager, debugging with IntelliTrace
- IntelliTrace, debugging after a crash
ms.assetid: 486bfec2-39bd-4d78-892a-42352128ee52
caps.latest.revision: 142
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a1cd1cc041970588cf7c90c2c6275100687e1bcb
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51737214"
---
# <a name="intellitrace"></a>IntelliTrace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [IntelliTrace](https://docs.microsoft.com/visualstudio/debugger/intellitrace) .  
  
Vous pouvez consacrer moins de temps au débogage de votre application quand vous utilisez IntelliTrace pour enregistrer et effectuer le suivi de l'historique d'exécution de votre code. Vous pouvez trouver des bogues facilement car IntelliTrace vous permet d'effectuer les tâches suivantes :  
  
- enregistrer des événements spécifiques ;  
  
   Examinez le code associé, les données qui apparaissent dans les **variables locales** fenêtre pendant les événements de débogueur et des informations d’appel de fonction  
  
- déboguer les erreurs qu'il est difficile de reproduire ou qui interviennent lors du déploiement.  
  
  Vous pouvez utiliser IntelliTrace dans Visual Studio Enterprise Edition (mais pas dans les éditions Professional ou Community).  
  
## <a name="what-do-you-want-to-do"></a>Que voulez-vous faire ?  
  
|||  
|-|-|  
|**Déboguer mon application avec IntelliTrace :**<br /><br /> -Afficher les événements passés.<br />-Afficher m’appeler des informations avec les événements passés.<br />-Enregistrer ma session IntelliTrace.<br />-Contrôle les données collectées par IntelliTrace.|-   [Procédure pas à pas : À l’aide d’IntelliTrace](../debugger/walkthrough-using-intellitrace.md)<br />     [Fonctionnalités IntelliTrace](../debugger/intellitrace-features.md)<br />-   [Configurez IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e)<br />-   [Débogage d’historique](../debugger/historical-debugging.md)|  
|**Collecter des données IntelliTrace au cours d’une session de test dans Gestionnaire de tests**|-   [Collecter des données de diagnostic plus de tests manuels](http://msdn.microsoft.com/library/bb5a2cc0-84f5-4dfe-9560-ca3d313aefd2)|  
|**Collecter des données IntelliTrace à partir des applications déployées**|-   [L’utilisation du collecteur autonome IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md)|  
|**Démarrage du débogage depuis un fichier de journal IntelliTrace (.iTrace fichier).**|-   [Utilisation des données IntelliTrace enregistrées](../debugger/using-saved-intellitrace-data.md)|  
  
##  <a name="IntelliTraceSupport"></a> Quelles applications puis-je déboguer avec IntelliTrace ?  
  
|||  
|-|-|  
|**Prise en charge**|-Applications Visual Basic et Visual c# qui utilisent .NET Framework 2.0 ou versions ultérieures.<br />     Vous pouvez déboguer la plupart des applications, notamment ASP.NET, Microsoft Azure, Windows Forms, WCF, WPF, Windows Workflow, SharePoint 2010 et SharePoint 2013, ainsi que les applications 64 bits.<br />     Pour déboguer des applications SharePoint avec IntelliTrace, consultez [procédure pas à pas : débogage d’une Application SharePoint par IntelliTrace d’à l’aide de](http://msdn.microsoft.com/library/4bd80d2f-f680-4bf4-81c3-f14e8185f6a4).<br />     Pour déboguer des applications de Microsoft Azure avec IntelliTrace, consultez [débogage d’un Service Cloud publié avec IntelliTrace et Visual Studio](http://go.microsoft.com/fwlink/?LinkID=262248).|  
|**Prise en charge limitée**|- F# applications à titre expérimental<br />-Les applications Windows Store pris en charge pour les événements uniquement|  
|**Non pris en charge**|-C++, d’autres langages et d’un script<br />-Windows Services, Silverlight, Xbox ou [!INCLUDE[winmobile](../includes/winmobile-md.md)] applications|  
  
> [!NOTE]
>  Si vous souhaitez déboguer un processus qui est déjà en cours d'exécution, vous ne pouvez pas utiliser IntelliTrace. Vous devez démarrer IntelliTrace lorsque le processus commence.  
  
##  <a name="IntelliTraceVSTraditional"></a> Pourquoi le débogage avec IntelliTrace ?  
 Traditionnel ou *live* débogage affiche uniquement de votre application à l’état actuel, avec des données limitées sur des événements passés. Vous devez déduire ces événements en fonction de l'état actuel de l'application ou recréer ces événements en réexécutant votre application.  
  
 IntelliTrace développe cette expérience de débogage traditionnel en enregistrant les événements et les données spécifiques à ces instants donnés dans le temps. Cela vous permet de voir ce qui s'est produit dans votre application sans la redémarrer, surtout si vous avez dépassé l'emplacement où se trouve le bogue. IntelliTrace est activé par défaut pendant un débogage traditionnel et collecte les données automatiquement et de façon invisible. Cela vous permet de basculer facilement entre le débogage traditionnel et le débogage IntelliTrace pour consulter les informations enregistrées. Voir [les fonctionnalités IntelliTrace](../debugger/intellitrace-features.md) et [les données IntelliTrace collecte ?](#WhatData)  
  
 IntelliTrace peut également vous aider à déboguer des erreurs difficiles à reproduire ou celles qui se produisent lors du déploiement. Vous pouvez collecter les données IntelliTrace et les enregistrer dans un fichier journal IntelliTrace (fichier .iTrace). Un fichier .iTrace contient des informations détaillées sur les exceptions, les événements de performance, les requêtes web, les données de test, les threads, les modules et autres informations système. Vous pouvez ouvrir ce fichier dans Visual Studio Ultimate, sélectionner un élément et démarrer le débogage avec IntelliTrace. Cela vous permet d'accéder à n'importe quel événement dans le fichier et de consulter les détails spécifiques relatifs à votre application à ce moment-là.  
  
 Vous pouvez enregistrer les données IntelliTrace à partir des sources suivantes :  
  
- Session IntelliTrace dans Visual Studio 2015 Enterprise ou des versions antérieures de Visual Studio Ultimate.  
  
- Une session de test dans Microsoft Test Manager.  
  
- Applications Web ASP.NET hébergées sur IIS, ou applications SharePoint 2010 et SharePoint 2013 qui s'exécutent dans le déploiement lorsque vous utilisez Microsoft Monitoring Agent, seul ou conjointement à System Center 2012. Consultez [à l’aide du collecteur autonome IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md) et [surveillance avec Microsoft Monitoring Agent](http://technet.microsoft.com/library/dn465153.aspx).  
  
  Voici quelques exemples pour vous aider à effectuer un débogage avec IntelliTrace :  
  
- Votre application a endommagé un fichier de données, mais vous ignorez à quel emplacement cet événement s'est produit.  
  
   Sans IntelliTrace, vous devez parcourir le code pour rechercher tous les accès possibles au fichier, placer des points d'arrêt sur ces accès, puis réexécuter votre application pour identifier l'emplacement où le problème s'est produit. Grâce à IntelliTrace, vous pouvez consulter tous les événements d'accès au fichier et des détails spécifiques relatifs à votre application quand chaque événement s'est produit.  
  
- Une exception se produit.  
  
   Sans IntelliTrace, vous recevez un message concernant une exception, mais vous avez peu d'informations relatives aux événements qui ont abouti à l'exception. Vous pouvez examiner la pile des appels pour consulter la chaîne des appels qui ont conduit à l'exception, mais ne pouvez pas consulter la séquence des événements qui s'est produite pendant ces appels. Grâce à IntelliTrace, vous pouvez examiner les événements antérieurs à l'exception.  
  
- Votre application se bloque sur un ordinateur de test, mais s'exécute correctement sur un ordinateur de développement.  
  
   Vous pouvez collecter les données IntelliTrace avec Microsoft Test Manager, enregistrer les données dans un fichier .iTrace et attacher ce fichier à un élément de travail Team Foundation Server pour un examen approfondi. Consultez [collecter des données de diagnostic plus dans les tests manuels](http://msdn.microsoft.com/library/bb5a2cc0-84f5-4dfe-9560-ca3d313aefd2) et [à l’aide des données IntelliTrace enregistrée](../debugger/using-saved-intellitrace-data.md).  
  
- Un bogue ou un incident se produit dans une application déployée.  
  
   Pour les applications basées sur Microsoft Azure, vous pouvez configurer la collecte de données IntelliTrace avant de publier l'application. Pendant que votre application s'exécute, IntelliTrace enregistre les données dans un fichier .iTrace. Consultez [débogage d’un Service Cloud publié avec IntelliTrace et Visual Studio](http://go.microsoft.com/fwlink/?LinkID=262248).  
  
   Pour les applications web ASP.NET hébergées sur IIS 7.0, 7.5 et 8.0, et les applications SharePoint 2010 ou SharePoint 2013, utilisez Microsoft Monitoring Agent, seul ou avec System Center 2012, pour enregistrer les données IntelliTrace dans un fichier .iTrace.  
  
   Cela est utile lorsque vous souhaitez diagnostiquer les problèmes liés aux applications du déploiement. Consultez [à l’aide du collecteur autonome IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md).  
  
##  <a name="WhatData"></a> Quelles sont les données IntelliTrace collecte ?  
 **Collecte des informations sur les événements**  
  
 Par défaut, IntelliTrace enregistre uniquement les événements IntelliTrace : événements de débogueur, exceptions, événements .NET Framework et autres événements système qui peuvent vous aider lors d’un débogage. Déterminez le type d’événements IntelliTrace à collecter, à l’exception des événements et des exceptions du débogueur, qui sont collectés systématiquement. Consultez [configurer IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
- **Événements de débogueur**  
  
   IntelliTrace enregistre systématiquement les événements intervenus dans le débogueur Visual Studio. Par exemple, le démarrage de votre application est un événement du débogueur. Les autres événements du débogueur sont les événements d'arrêt, qui interrompent l'exécution de votre application. Par exemple, votre programme atteint un point d’arrêt, atteint un point de trace ou s’il exécute une **étape** commande.  
  
   Pour améliorer les performances, IntelliTrace n'enregistre pas toutes les valeurs possibles pour un événement du débogueur. En revanche, il enregistre les valeurs suivantes :  
  
  -   Les valeurs dans le **variables locales** fenêtre. Conserver la **variables locales** fenêtre ouverte pour afficher ces valeurs.  
  
  -   Les valeurs dans le **automatique** fenêtre uniquement lorsque la **automatique** fenêtre est ouverte  
  
  -   Valeurs situées dans DataTips qui apparaissent lorsque vous déplacez le pointeur de la souris au-dessus d'une variable dans la fenêtre source pour afficher sa valeur. IntelliTrace ne collecte pas de valeurs dans les DataTips épinglés.  
  
- **Exceptions**  
  
   IntelliTrace enregistre le type et le message d'exception pour ces types d'exceptions :  
  
  -   Exceptions traitées où l'exception est levée et interceptée  
  
  -   Exceptions non traitées  
  
- **Événements .NET framework**  
  
   Par défaut, IntelliTrace enregistre les événements .NET Framework les plus courants. Par exemple :  
  
  -   Pour un événement d'accès au fichier, IntelliTrace collecte le nom de fichier.  
  
  -   Pour un événement de case à cocher, IntelliTrace collecte l'état et le texte de la case à cocher.  
  
- **Événements d’application SharePoint 2010 et SharePoint 2013**  
  
   Vous pouvez enregistrer des événements de profil utilisateur et un sous-ensemble d'événements ULS (Unified Logging System) pour les applications SharePoint 2010 et 2013 qui s'exécutent en dehors de Visual Studio. Vous pouvez enregistrer ces événements dans un fichier .iTrace. Nécessite Visual Studio Enterprise 2015, une version antérieure de Visual Studio Ultimate ou [Microsoft Monitoring Agent](http://go.microsoft.com/fwlink/?LinkId=320384) en cours d’exécution **Trace** mode.  
  
   Lorsque vous ouvrez le fichier .iTrace, vous pouvez entrer un ID de corrélation SharePoint pour rechercher sa requête web correspondante, afficher les événements inscrits, puis démarrer le débogage à partir d'un événement spécifique. Si le fichier contient des exceptions non gérées, vous pouvez choisir un ID de corrélation pour commencer à déboguer une exception.  
  
   Consultez :  
  
  -   [Utilisation du collecteur autonome IntelliTrace](../debugger/using-the-intellitrace-stand-alone-collector.md)  
  
  -   [Utilisation des données IntelliTrace enregistrées](../debugger/using-saved-intellitrace-data.md)  
  
  -   [Procédure pas à pas : débogage d’une application SharePoint avec IntelliTrace](http://msdn.microsoft.com/library/4bd80d2f-f680-4bf4-81c3-f14e8185f6a4)  
  
  **Collecte des informations sur les appels de fonction**  
  
  Configurez IntelliTrace pour collecter les informations sur les appels de fonctions. Ces informations vous permettent de consulter un historique de la pile des appels et d'exécuter en mode pas à pas des appels dans le code vers l'avant et vers l'arrière. Pour chaque appel de fonction, IntelliTrace enregistre les données suivantes :  
  
- Nom de la fonction  
  
- Valeurs des types de données primitifs passées comme paramètres aux points d'entrée de fonction et retournées aux points de sortie de fonction  
  
- Valeurs des propriétés automatiques lorsqu'elles sont lues ou modifiées  
  
- Pointeurs désignant des objets enfants de premier niveau, mais non leurs valeurs sauf si elles sont nulles ou pas  
  
> [!NOTE]
>  IntelliTrace collecte uniquement les 256 premiers objets des tableaux et les 256 premiers caractères des chaînes.  
  
 Consultez [configurer IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
 **Collecte des informations de module**  
  
 Pour contrôler la quantité d'informations sur les appels qu'IntelliTrace collecte, spécifiez uniquement les modules qui vous intéressent. Cela peut améliorer les performances de votre application pendant la collection. Consultez [configurer IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
##  <a name="AffectPerformance"></a> IntelliTrace va ralentir mon application ?  
 Par défaut, IntelliTrace collecte uniquement les données des événements IntelliTrace sélectionnés. Votre application peut être ralentie ou non, en fonction de la structure et de l'organisation de votre code. Par exemple, si IntelliTrace enregistre souvent un événement, cela peut ralentir votre application. Cela peut aussi vous inciter à refactoriser votre application.  
  
 La collecte d'informations sur les appels peut ralentir votre application de manière significative. Cela peut également augmenter la taille des fichiers journaux IntelliTrace (.iTrace) que vous enregistrez sur le disque. Pour minimiser ces effets, collectez des informations sur les appels uniquement pour les modules qui vous intéressent.  Pour modifier la taille maximale de vos fichiers .iTrace, accédez à **outils**, **Options**, **IntelliTrace**, **avancé**. Consultez [configurer IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
## <a name="in-this-section"></a>Dans cette section  
 [Fonctionnalités IntelliTrace](../debugger/intellitrace-features.md)  
  
 [Configurez IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e)  
  
 [Y compris les données de Trace de Diagnostic dans des bogues difficiles à reproduire](http://msdn.microsoft.com/library/944ae9af-5a55-4c58-b520-0108c03b3564)  
  
 [Diagnostiquer des problèmes après le déploiement](../debugger/diagnose-problems-after-deployment.md)  
  
 [Utilisation des données IntelliTrace enregistrées](../debugger/using-saved-intellitrace-data.md)  
  
### <a name="blogs"></a>Blogs  
 [Visual Studio ALM + Team Foundation Server](http://go.microsoft.com/fwlink/?LinkID=201340)  
  
### <a name="forums"></a>Forums  
 [Diagnostics Visual Studio](http://go.microsoft.com/fwlink/?LinkId=262263)





