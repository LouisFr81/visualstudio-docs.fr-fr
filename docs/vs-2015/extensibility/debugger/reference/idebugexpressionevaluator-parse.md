---
title: IDebugExpressionEvaluator::Parse | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4d772ce5eda094b80a520d8fba4bd41f0b90d17
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51804518"
---
# <a name="idebugexpressionevaluatorparse"></a>IDebugExpressionEvaluator::Parse
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette méthode convertit une chaîne d’expression en une expression analysée.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Parse(   
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
int Parse(  
   string                     upstrExpression,   
   enum_PARSEFLAGS            dwFlags,   
   uint                       nRadix,   
   out string                 pbstrError,   
   out uint                   pichError,   
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `upstrExpression`  
 [in] La chaîne d’expression à analyser.  
  
 `dwFlags`  
 [in] Une collection de [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) constantes qui déterminent comment l’expression doit être analysé.  
  
 `nRadix`  
 [in] Base à utiliser pour interpréter toutes les informations numériques.  
  
 `pbstrError`  
 [out] Retourne l’erreur sous forme de texte lisible.  
  
 `pichError`  
 [out] Retourne la position de caractère de début de l’erreur dans la chaîne d’expression.  
  
 `ppParsedExpression`  
 [out] Retourne l’expression analysée dans un [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) objet.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Cette méthode génère une expression analysée, pas une valeur réelle. Une expression analysée est prête à être évaluée, autrement dit, convertie en une valeur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)

