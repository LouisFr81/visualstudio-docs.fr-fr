---
title: 'Procédure pas à pas : Accès à l’objet DTE à partir d’une Extension de l’éditeur | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
caps.latest.revision: 23
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b86f33390068b04d9e54c0022e8adeb77ed4700f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51720756"
---
# <a name="walkthrough-accessing-the-dte-object-from-an-editor-extension"></a>Procédure pas à pas : accès à l’objet DTE à partir d’une extension de l’éditeur
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dans les VSPackages, vous pouvez obtenir l’objet DTE en appelant le <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> méthode avec le type de l’objet DTE. Dans les extensions Managed Extensibility Framework (MEF), vous pouvez importer <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> , puis appelez le <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> méthode avec un type de <xref:EnvDTE.DTE>.  
  
## <a name="prerequisites"></a>Prérequis  
 Pour suivre cette procédure pas à pas, vous devez installer le Kit de développement logiciel (SDK) Visual Studio. Pour plus d’informations, consultez [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="getting-the-dte-object"></a>Obtention de l’objet DTE  
  
#### <a name="to-get-the-dte-object-from-the-serviceprovider"></a>Pour obtenir de l’objet DTE à partir de ServiceProvider  
  
1.  Créez un projet VSIX c# nommé `DTETest`. Ajouter un modèle d’élément de classifieur d’éditeur et nommez-le `DTETest`. Pour plus d’informations, consultez [création d’une Extension avec un éditeur de modèle d’élément](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
2.  Ajoutez les références d’assembly suivantes au projet :  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.Shell.Immutable.10.0  
  
3.  Accédez au fichier DTETest.cs, puis ajoutez le code suivant `using` directives :  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio.Shell;  
  
    ```  
  
4.  Dans le `GetDTEProvider` class, importer un <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.  
  
    ```csharp  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  Dans la méthode `GetClassifier()`, ajoutez le code suivant.  
  
    ```csharp  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  Si vous devez utiliser le <xref:EnvDTE80.DTE2> interface, vous pouvez effectuer un cast de l’objet DTE.  
  
## <a name="see-also"></a>Voir aussi  
 [Points d’extension du service de langage et de l’éditeur](../extensibility/language-service-and-editor-extension-points.md)

