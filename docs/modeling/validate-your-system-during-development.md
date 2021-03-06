---
title: Validation de votre système pendant le développement
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ce0822f5731e7c09a6f6dff9116e70b97a529206
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316754"
---
# <a name="validate-your-system-during-development"></a>Validation de votre système pendant le développement
Visual Studio peut vous aider à garder votre logiciel en cohérence avec les besoins des utilisateurs et avec l’architecture de votre système.

 Pour connaître les versions de Visual Studio qui prennent en charge chacune de ces fonctionnalités, consultez [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="key-tasks"></a>Tâches clés
 Utilisez les tâches suivantes pour valider votre logiciel.

|**Tâches**|**Rubriques associées**|
|-|-|
|**Assurez-vous que votre logiciel répond aux besoins des utilisateurs**:<br /><br /> Vous pouvez utiliser les spécifications et les modèles architecturaux pour mieux organiser les tests de votre système et de ses composants. Cette pratique vous permet de vous assurer que vous testez les besoins importants des utilisateurs et des autres parties prenantes, et vous aide à mettre rapidement à jour les tests quand les besoins changent.|-   [Développer des tests à partir d’un modèle](../modeling/develop-tests-from-a-model.md)|
|**Assurez-vous que votre logiciel reste cohérent avec la conception prévue de votre système :**<br /><br /> Diagrammes de dépendance décrivent les dépendances prévues entre les composants de votre application. Pendant le développement, vous pouvez vérifier que les dépendances actuelles dans le code sont conformes à la conception prévue.|-   [Créer des diagrammes de dépendance à partir de votre code](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Valider du code avec des diagrammes de dépendance](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>Ressources externes

|**Catégorie**|**Liens**|
|-|-|
|**Vidéos**|![lien vers la vidéo](../data-tools/media/playvideo.gif) [Channel 9 : Doug Seven : Présentation du code et conception du système avec Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![lien vers la vidéo](../data-tools/media/playvideo.gif) [Channel 9 : Architecture d’une Application à l’aide d’un diagramme de dépendances](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![lien vers la vidéo](../data-tools/media/playvideo.gif) [série MSDN Comment faire : Comment valider du Code à l’aide de diagrammes de dépendance](http://go.microsoft.com/fwlink/?LinkID=214405)|
|**Forums**|-   [Outils de visualisation et de modélisation Visual Studio](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Kit de développement logiciel (SDK) Visual Studio Visualization and Modeling (outils DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogs**|-   [Microsoft DevOps](https://devblogs.microsoft.com/devops/)|
|**Articles et journaux techniques**|[Centre d’architecture MSDN](http://go.microsoft.com/fwlink/?LinkId=201343)|

## <a name="see-also"></a>Voir aussi

- [Test de l’application](/azure/devops/test/overview?view=vsts)
- [Modéliser les besoins des utilisateurs](../modeling/model-user-requirements.md)
- [Analyse et modélisation de l’architecture](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
