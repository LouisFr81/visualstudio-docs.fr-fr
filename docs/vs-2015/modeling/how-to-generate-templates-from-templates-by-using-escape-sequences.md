---
title: 'Comment : générer des modèles à partir de modèles à l’aide de séquences d’échappement | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: fd3a54c69b33e503908217b9d0d83c6f61c6380a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49249409"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Comment : générer des modèles à partir de modèles à l'aide de séquences d'échappement
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez créer un modèle de texte qui crée un autre modèle de texte en tant que sortie de texte générée. Pour ce faire, vous devez utiliser des séquences d’échappement pour délimiter les balises de modèle de texte. Si vous n’utilisez pas de séquences d’échappement, votre modèle de texte généré aura une signification prédéfinie. Pour plus d’informations sur l’utilisation de séquences d’échappement dans les modèles de texte, consultez [à l’aide de séquences d’échappement dans les modèles de texte](../modeling/using-escape-sequences-in-text-templates.md).  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Pour générer un modèle de texte à partir d’un modèle de texte  
  
-   Utilisez la barre oblique inverse (\\) en tant que caractère d’échappement pour produire les balises nécessaires dans le modèle de texte pour les directives, les instructions, expressions et fonctions dans un fichier de modèle de texte séparé de la classe.  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise des caractères d’échappement pour produire un modèle de texte à partir d’un modèle de texte. Le `output` directive définit le type de fichier de destination pour le type de fichier de modèle de texte (.tt).  
  
```csharp  
\<#@ output extension=".tt" \#>  
\<#@ assembly name="System.Xml.dll" \#>  
\<#@ import namespace="System.Xml" \#>  
\<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {\#>  
           \<#= attr.Name \#>  
       \<#}  
     }  
\#>  
```  
  
 La sortie de texte générée est un modèle de texte.  
  
```  
<#@ output extension=".tt" #>  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {#>  
           <#= attr.Name #>  
       <#}  
     }  
#>  
```



