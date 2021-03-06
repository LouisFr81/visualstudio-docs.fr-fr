---
title: '&lt;Chaînes&gt; élément (programme d’amorçage) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- MSBuild.GenerateBootstrapper.NoStringsForCulture
- MSBuild.GenerateBootstrapper.ProductCultureNotFound
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Strings> element [bootstrapper]
ms.assetid: d5ea3613-5fc9-4a11-bef3-46a01178bf60
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 15f39ca0170ca7ecf84c5ad6ef48bf5803624b55
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54947404"
---
# <a name="ltstringsgt-element-bootstrapper"></a>&lt;Chaînes&gt; élément (programme d’amorçage)
Définit des chaînes localisées pour les noms de produits, les noms de package et les messages d’erreur d’installation.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<Strings>  
    <String  
        Name  
    >  
    </String>  
</Strings>  
```  
  
## <a name="elements-and-attributes"></a>Éléments et attributs  
 Le `Strings` élément est un enfant de le `Package` élément. Il a pas d’attributs.  
  
## <a name="string"></a>Chaîne  
 Le `String` élément est un enfant de le `Strings` élément. Un `Strings` élément peut avoir un ou plusieurs `String` éléments.  
  
 `String` a l’attribut suivant.  
  
|Attribut|Description|  
|---------------|-----------------|  
|`Name`|Obligatoire. Le nom de la chaîne.|  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant spécifie toutes les chaînes en anglais pour le [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] programme d’installation.  
  
```xml  
<Strings>  
    <String Name="DisplayName">.NET Framework 2.0</String>  
    <String Name="Culture">en</String>  
    <String Name="AdminRequired">Administrator permissions are required to install the .NET Framework 2.0. Contact your administrator.</String>  
    <String Name="InvalidPlatformWin9x">Installation of the .NET Framework 2.0 is not supported on Windows 95. Contact your application vendor.</String>  
    <String Name="InvalidPlatformWinNT">Installation of the .NET Framework 2.0 is not supported on Windows NT 4.0. Contact your application vendor.</String>  
    <String Name="InvalidPlatformIE">Installation of the .NET Framework 2.0 requires Internet Explorer 5.01 or greater. Contact your application vendor.</String>  
    <String Name="InvalidPlatformArchitecture">This version of the .NET Framework 2.0 is not supported on a 64-bit operating system. Contact your application vendor.</String>  
    <String Name="WindowsInstallerImproperInstall">Due to an error with Windows Installer, the installation of the .NET Framework 2.0 cannot proceed.</String>  
    <String Name="AnotherInstanceRunning">Another instance of setup is already running. The running instance must complete before this setup can proceed.</String>  
    <String Name="BetaNDPFailure">A beta version of the .NET Framework was detected on the computer. Uninstall any previous beta versions of .NET Framework before continuing.</String>  
    <String Name="GeneralFailure">A failure occurred attempting to install the .NET Framework 2.0.</String>  
    <String Name="DotNetFXExe">http://go.microsoft.com/fwlink/?LinkId=37283</String>  
    <String Name="InstMsiAExe">http://go.microsoft.com/fwlink/?LinkId=37285</String>  
    <String Name="Msi30Exe">http://go.microsoft.com/fwlink/?LinkId=37287</String>  
</Strings>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<Package > élément](../deployment/package-element-bootstrapper.md)