---
title: Emplacement de document | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: b59d739c-7572-427f-a70d-4e5df63d02c1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2f025ca2d73e98f8191969510f866cb7eb1d0eea
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695951"
---
# <a name="document-position"></a>Position du document
Dans [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] débogage, un *document position*:

-   Fournit une abstraction d’une position dans un fichier source connues de l’IDE. Pour la plupart des langages aujourd'hui, une position de document peut être considérée comme une position dans un fichier source.

-   Décrit une position dans un document source pour un moteur de débogage.

-   Est implémentée par un [IDebugDocumentPosition2](../../extensibility/debugger/reference/idebugdocumentposition2.md) interface.

## <a name="see-also"></a>Voir aussi
- [Contexte de code](../../extensibility/debugger/code-context.md)
- [Contexte de document](../../extensibility/debugger/document-context.md)
- [Fournisseur de symboles](../../extensibility/debugger/symbol-provider.md)
- [Interfaces de fournisseur de symboles](../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [Contextes du débogueur](../../extensibility/debugger/debugger-contexts.md)