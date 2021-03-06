---
title: Outils XML dans Visual Studio | Microsoft Docs
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
- vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET Framework classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 56c4fe7671751b7a7cd16c7065205978728f8f99
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49234128"
---
# <a name="xml-tools-in-visual-studio"></a>Outils XML dans Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Langage XML (Extensible Markup) * est un langage de balisage qui fournit un format de description des données. Il permet d'effectuer des déclarations de contenu plus précises et d'obtenir des résultats de recherche plus pertinents entre plusieurs plateformes. De plus, le langage XML permet de séparer la présentation des données. Par exemple, en HTML, vous utilisez des balises pour indiquer au navigateur d'afficher des données en caractères gras ou italiques, tandis qu'en langage XML, vous utilisez des balises uniquement pour décrire les données, telles qu'un nom de ville, une température ou une pression barométrique. En XML, vous utilisez des feuilles de style, telles que des feuilles de style en cascade (CSS) ou de type XSL (eXtensible Stylesheet Language) pour présenter les données dans un navigateur. Le langage XML sépare les données de la présentation et du processus. Cela vous permet d'afficher et de traiter les données comme vous le souhaitez, en appliquant différentes feuilles de style et applications.  
  
 Le langage XML est un sous-ensemble du langage SGML qui est optimisé pour une distribution via Internet. Il a été défini par le World Wide Web Consortium (W3C). Cette normalisation garantit que les données structurées seront uniformes et indépendantes des applications et des fournisseurs.  
  
 XML est au cœur de nombreuses fonctionnalités de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] et du [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. Les rubriques répertoriées ci-dessous nomment les outils et les fonctionnalités associés au langage XML qui sont proposés dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] et le [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].  
  
 Pour plus d’informations, consultez le [centre de développement XML](http://go.microsoft.com/fwlink/?LinkID=100176), qui fournit la documentation la plus récente, des informations techniques, des téléchargements, des groupes de discussion et d’autres ressources pour les développeurs XML.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Utilisation de données XML](../xml-tools/working-with-xml-data.md)  
 Présente le rôle du langage XML dans la manière dont les données sont traitées dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 [Débogage XSLT](../xml-tools/debugging-xslt.md)  
 Fournit des liens vers des rubriques relatives à l'utilisation du débogueur Visual Studio pour déboguer XSLT.  
  
## <a name="reference"></a>Référence  
 [Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699)  
 Expose les [éditeur XML](http://go.microsoft.com/fwlink/?LinkId=228249) arborescence par le biais d’analyse [System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250) pour tous les documents XML.  
  
 [Référence du standard XML](http://msdn.microsoft.com/en-us/79c78508-c9d0-423a-a00f-672e855de401)  
 Fournit des informations sur les technologies XML, y compris le langage XML, la définition de type de document (DTD), le langage XSD (XML Schema Definition) et XSLT.  
  
 <xref:System.Xml?displayProperty=fullName>  
 Décrit les classes et d'autres éléments qui composent l'espace de noms <xref:System.Xml> et fournit des liens vers des informations plus détaillées sur chaque élément.  
  
 <xref:System.Xml.Serialization?displayProperty=fullName>  
 Décrit les classes et d'autres éléments qui composent l'espace de noms <xref:System.Xml.Serialization> et fournit des liens vers des informations plus détaillées sur chaque élément.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [DOM (Document Object Model) XML](http://msdn.microsoft.com/library/b5e52844-4820-47c0-a61d-de2da33e9f54)  
 Décrit comment la classe <xref:System.Xml.XmlDocument> et les classes qui lui sont associées se conforment aux spécifications de prise en charge d'espace de noms des modèles DOM (Document Object Model) (principaux) de niveau 1 et de niveau 2 du W3C.  
  
 [Lecture de XML avec XmlReader](http://msdn.microsoft.com/en-us/3029834c-a27e-4331-b7aa-711924062182)  
 Décrit comment la classe <xref:System.Xml.XmlReader> fournit un accès en lecture seule, avant uniquement et non mis en cache aux données XML via un flux XML.  
  
 [Écriture de XML avec XmlWriter](http://msdn.microsoft.com/en-us/ea41f72c-e1d3-4e0a-ab0f-f0eb1c27ab86)  
 Décrit comment la classe <xref:System.Xml.XmlWriter> fournit une manière avant uniquement et sans mise en cache de générer des flux XML, et vous aide à générer des documents XML conformes à la norme W3C.  
  
 [Transformations XSLT](http://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03)  
 Décrit comment la classe <xref:System.Xml.Xsl.XslCompiledTransform> implémente la recommandation XSLT 1.0.  
  
 [Traitement des données XML à l’aide du modèle de données XPath](http://msdn.microsoft.com/library/536c6fce-1453-4654-9c72-bca54d47e081)  
 Décrit comment la classe <xref:System.Xml.XPath.XPathNavigator> peut traiter des données XML stockées dans un objet <xref:System.Xml.XPath.XPathDocument> ou <xref:System.Xml.XmlDocument>. La classe <xref:System.Xml.XPath.XPathNavigator> est basée sur le modèle de données XQuery 1.0 et XPath 2.0, et peut être utilisée pour parcourir et modifier des données XML.  
  
 [Modèle Objet du schéma (SOM) XML](http://msdn.microsoft.com/library/a897a599-ffd1-43f9-8807-e58c8a7194cd)  
 Décrit les classes utilisées pour créer et manipuler des schémas XML, en fournissant une classe <xref:System.Xml.Schema.XmlSchema> pour charger et modifier un schéma.



