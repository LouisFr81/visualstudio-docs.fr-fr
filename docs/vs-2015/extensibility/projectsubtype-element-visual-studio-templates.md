---
title: ProjectSubType, élément (modèles Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectSubType
helpviewer_keywords:
- ProjectSubType element [Visual Studio Templates]
- <ProjectSubType> element [Visual Studio Templates]
ms.assetid: f6895cd4-3e95-4f0e-aa9e-8c7750f46ed4
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bfc64d4f5a1de6223178321eecb3050478ed9960
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807762"
---
# <a name="projectsubtype-element-visual-studio-templates"></a>ProjectSubType, élément (modèles Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Classe le modèle dans une sous-catégorie de la valeur spécifiée dans le `ProjectType` élément.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProjectSubType >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ProjectSubType> SubType </ProjectSubType>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
 Aucun.  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Élément requis.<br /><br /> Définit la catégorie du modèle et comment il s’affiche dans la boîte de dialogue **Nouveau projet** ou **Ajouter un nouvel élément** .|  
  
## <a name="text-value"></a>Valeur texte  
 Une valeur texte est requise.  
  
 Cette valeur spécifie la sous-catégorie du modèle.  
  
## <a name="remarks"></a>Notes  
 `ProjectSubType` est un élément enfant facultatif de `TemplateData`.  
  
 Le `ProjectSubType` élément fournit une sous-catégorie à la [ProjectType](../extensibility/projecttype-element-visual-studio-templates.md) élément. Cette valeur peut inclure :  
  
- `SmartDevice-NETCFv1`: Spécifie que le modèle cible le [!INCLUDE[Compact](../includes/compact-md.md)] version 1.0.  
  
- `SmartDevice-NETCFv2`: Spécifie que le modèle concerne la [!INCLUDE[Compact](../includes/compact-md.md)] version 2.0.  
  
  Si un modèle contient un `ProjectType` élément avec une valeur de `Web`, le `ProjectSubType` élément spécifie le langage de programmation du modèle. Cet élément peut avoir les valeurs suivantes :  
  
- `CSharp`: Spécifie que le modèle crée un [!INCLUDE[csprcs](../includes/csprcs-md.md)] projet Web ou un élément.  
  
- `VisualBasic`: Spécifie que le modèle crée un [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] projet Web ou un élément.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre les métadonnées d’un modèle de projet pour un [!INCLUDE[csprcs](../includes/csprcs-md.md)] appareil application ciblant le [!INCLUDE[Compact](../includes/compact-md.md)] version 2.0.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic device template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProjectSubType>SmartDevice-NETCFv2</ProjectSubType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Élément ProjectType (modèles Visual Studio)](../extensibility/projecttype-element-visual-studio-templates.md)

