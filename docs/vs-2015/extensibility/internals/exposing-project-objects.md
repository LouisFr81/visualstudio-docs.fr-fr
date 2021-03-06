---
title: Exposer des objets de projet | Microsoft Docs
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
- project objects, exposing
- extensibility, project objects
ms.assetid: 5bb24967-434a-4ef4-87a0-2f3250c9e22d
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c4af521a8c6044742d69a1d71dcf605145d600d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51731412"
---
# <a name="exposing-project-objects"></a>Exposition des objets de projet
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Les types de projet personnalisés peuvent fournir des objets automation afin d’autoriser l’accès au projet à l’aide des interfaces d’automatisation. Chaque type de projet est censé fournir la norme <xref:EnvDTE.Project> objet automation qui est accessible à partir de <xref:EnvDTE.Solution>, qui contient une collection de tous les projets qui sont ouverts dans l’IDE. Chaque élément dans le projet doit être exposé par un <xref:EnvDTE.ProjectItem> objet accédé avec <xref:EnvDTE.Project.ProjectItems>. Outre ces objets automation standard, les projets peuvent choisir de fournir des objets automation de projet spécifique.  
  
 Vous pouvez créer des personnalisés au niveau racine objets automation que vous pouvez accéder à liaison tardive à partir de l’objet DTE racine à l’aide `DTE.<customeObjectName>` ou `DTE.GetObject(“<customObjectName>”)`. Par exemple, Visual C++ crée la collection de projet spécifique à un projet C++ appelée « VCProjects » que vous pouvez accéder à l’aide de DTE. VCProjects ou DTE. Par exemple, DTE. Vous pouvez également créer un Project.Object, qui est unique pour le type de projet, Project.CodeModel, ce qui peut être interrogé pour son objet plus dérivé, ProjectItem, qui expose ProjectItem.Object et un ProjectItem.FileCodeModel.  
  
 Il est couramment utilisée pour les projets exposer une collection de projets personnalisés, spécifiques au projet. Par exemple, [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] crée une collection de projets spécifiques de C++ que vous pouvez ensuite accéder à l’aide de `DTE.VCProjects` ou `DTE.GetObject("VCProjects")`. Vous pouvez également créer un `Project.Object`, qui est unique pour le type de projet, un `Project.CodeModel`, qui peut être interrogée pour son objet plus dérivé, un `ProjectItem`, qui expose `ProjectItem.Object`et un `ProjectItem.FileCodeModel`.  
  
### <a name="to-contribute-a-vspackage-specific-object-for-a-project"></a>De contribuer un objet VSPackage spécifique pour un projet  
  
1.  Ajoutez les clés appropriées au fichier .pkgdef de votre VSPackage.  
  
     Par exemple, voici les paramètres .pkgdef pour le projet de langage C++ :  
  
    ```  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\Automation]  
    "VCProjects"=""  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\AutomationEvents]  
    "VCProjectEngineEventsObject"=""  
    ```  
  
2.  Implémenter le code dans le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> méthode, comme dans l’exemple suivant.  
  
    ```cpp  
    STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
    {  
    ExpectedPtrRet(pszPropName);  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
        if (m_fZombie)  
            return E_UNEXPECTED;  
  
        if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)  
        {  
            return GetAutomationProjects(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        return E_INVALIDARG;  
    }   
    ```  
  
     Dans le code, `g_wszAutomationProjects` est le nom de votre collection de projets. Le `GetAutomationProjects` méthode crée un objet qui implémente le `Projects` interface et retourne un `IDispatch` pointeur vers l’objet appelant, comme indiqué dans l’exemple de code suivant.  
  
    ```cpp  
    HRESULT CVsPackage::GetAutomationProjects(/* [out] */ IDispatch ** ppIDispatch)  
    {  
        ExpectedPtrRet(ppIDispatch);  
        *ppIDispatch = NULL;  
  
        if (!m_srpAutomationProjects)  
        {  
            HRESULT hr = CACProjects::CreateInstance(&m_srpAutomationProjects);  
            IfFailRet(hr);  
            ExpectedExprRet(m_srpAutomationProjects != NULL);  
        }  
        return m_srpAutomationProjects.CopyTo(ppIDispatch);  
    }  
    ```  
  
     Vous devez choisir un nom unique pour votre objet automation. Conflits de noms sont imprévisibles, entraînant des collisions d’un nom d’objet en conflit à arbitrairement exclues si plusieurs types de projets utilisent le même nom. Vous devez inclure le nom de votre société ou de certains aspects uniques de son nom de produit dans le nom de l’objet automation.  
  
     Personnalisé `Projects` objet de collection est un point d’entrée plus de commodité pour la partie restante de votre modèle automation de projet. Votre objet de projet est également accessible depuis le <xref:EnvDTE.Solution> collection de projets. Une fois que vous avez créé les entrées appropriées de code et de Registre qui fournissent des consommateurs disposant de `Projects` objets de collection, votre implémentation doit fournir restant des objets standards pour le modèle de projet. Pour plus d’informations, consultez [projet de modélisation](../../extensibility/internals/project-modeling.md).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>

