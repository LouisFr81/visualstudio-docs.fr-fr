---
title: Interfaces de Service de langage hérité | Microsoft Docs
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
- IVsLanguageInfo interface
- language services, objects
ms.assetid: 03b2d507-f463-417e-bc22-bdac68eeda52
caps.latest.revision: 25
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a5e574267ac83d145c5f3fb44117534127e3f1fd
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51785844"
---
# <a name="legacy-language-service-interfaces"></a>Interfaces du service de langage hérité
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Pour n’importe quel langage de programmation particulier, il peut y avoir qu’une seule instance d’un service de langage à la fois. Toutefois, un service de langage unique peut servir plusieurs éditeurs.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] n’associe pas un service de langage à n’importe quel éditeur particulier. Par conséquent, lorsque vous demandez une opération de service de langage, vous devez identifier l’éditeur approprié en tant que paramètre.  
  
## <a name="common-interfaces-associated-with-language-services"></a>Interfaces courantes associées aux Services de langage  
 L’éditeur obtient votre service de langage en appelant <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> sur le VSPackage approprié. L’ID (SID) passée dans cet appel de service identifie le service de langage demandé.  
  
 Vous pouvez implémenter les interfaces de service de langage core sur n’importe quel nombre de classes distincts. Toutefois, une approche courante consiste à implémenter les interfaces suivantes dans une classe unique :  
  
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>  
  
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>  
  
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>  
  
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageBlock> (facultatif)  
  
  Le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> interface doit être implémentée sur tous les services de langage. Il fournit des informations sur votre service de langage, tels que le nom localisé du langage, les extensions de nom de fichier associés avec le service de langage et comment récupérer un Coloriseur.  
  
## <a name="additional-language-service-interfaces"></a>Interfaces de Service de langage supplémentaire  
 Autres interfaces peuvent être fournies avec votre service de langage. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] demande une instance distincte de ces interfaces pour chaque instance de la mémoire tampon de texte. Par conséquent, vous devez implémenter chacune de ces interfaces sur son propre objet. Le tableau suivant montre les interfaces qui nécessitent une seule instance par instance de mémoire tampon de texte.  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|Gère des ornements de fenêtre de code, tels que la barre déroulante. Vous pouvez obtenir cette interface à l’aide de la <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> (méthode). Il y a un <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> par fenêtre de code.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>|Colore les délimiteurs et les mots clés du langage. Vous pouvez obtenir cette interface à l’aide de la <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> (méthode). <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> est appelé au moment de la peinture. Éviter le travail de calcul intensif à l’intérieur de <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> ou de performances peut en pâtir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>|Fournit des info-bulles du paramètre IntelliSense. Lorsque le service de langage reconnaît un caractère qui indique les données de cette méthode doit être affiché, par exemple une parenthèse ouvrante, il appelle le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> méthode pour informer le texte qui permet d’afficher le service de langage est prêt à afficher une info-bulle d’informations de paramètre. L’affichage de texte rappelle ensuite le service de langage en utilisant les méthodes de la <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> interface permettant d’obtenir les informations requises pour afficher l’info-bulle.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet>|Fournit la saisie semi-automatique des instructions IntelliSense. Lorsque le service de langage est prêt à afficher une liste de saisie semi-automatique, il appelle le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> méthode sur l’affichage de texte. L’affichage de texte rappelle ensuite le service de langage à l’aide des méthodes sur le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> objet.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter>|Autorise la modification de la vue de texte en utilisant le Gestionnaire de commandes. La classe dans laquelle vous implémentez le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> interface doit également implémenter le <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interface. L’affichage de texte récupère le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> objet en interrogeant le <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objet qui est passé dans le <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> (méthode). Vous devez avoir un <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> objet pour chaque vue.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Intercepte des commandes que l’utilisateur tape dans la fenêtre de code. Surveiller la sortie à partir de votre <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> implémentation pour fournir des informations de saisie semi-automatique personnalisés et afficher la modification<br /><br /> Pour passer votre <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objet à l’affichage de texte, appel <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>.|  
  
## <a name="see-also"></a>Voir aussi  
 [Développement d’un Service de langage hérité](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [Liste de vérification : création d’un service de langage hérité](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)

