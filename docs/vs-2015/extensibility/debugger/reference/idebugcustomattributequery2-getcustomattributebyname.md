---
title: IDebugCustomAttributeQuery2::GetCustomAttributeByName | Microsoft Docs
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
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
helpviewer_keywords:
- IDebugCustomAttributeQuery2::GetCustomAttributeByName
ms.assetid: 7428dfeb-8929-41b2-9b99-cb343a86c02d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 80e67c26924a906cada5dec022b8a385f0f4afad
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51796114"
---
# <a name="idebugcustomattributequery2getcustomattributebyname"></a>IDebugCustomAttributeQuery2::GetCustomAttributeByName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obtient les octets d’attributs personnalisés étant données le nom de l’attribut personnalisé.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetCustomAttributeByName(   
   LPCOLESTR pszCustomAttributeName,  
   BYTE*     ppBlob,  
   DWORD*    pdwLen  
);  
```  
  
```csharp  
int GetCustomAttributeByName(  
   [In] string        pszCustomAttributeName,   
   [In, Out] byte[]   ppBlob,   
   [In, Out] ref uint pdwLen  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszCustomAttributeName`  
 [in] Chaîne contenant le nom de l’attribut personnalisé à rechercher.  
  
 `ppBlob`  
 [in, out] Tableau qui contient les octets de l’attribut personnalisé.  
  
 `pdwLen`  
 [in, out] Spécifie le nombre maximal d’octets à renvoyer dans le `ppBlob` de tableau et retourne le nombre d’octets réellement écrits dans le tableau.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne S_OK ou S_FALSE si l’attribut personnalisé n’existe pas. Sinon, retourne un code d'erreur.  
  
## <a name="remarks"></a>Notes  
 Définir le `ppBlob` des attributs de paramètre à une valeur null pour retourner le nombre d’octets disponibles. Allouez un tableau, puis passer ce tableau dans pour la `ppBlob` paramètre.  
  
 Les octets d’attribut représentent les données brutes de l’attribut personnalisé.  
  
 Si le `ppBlob` et `pdwLen` paramètres sont définis sur une valeur null, cette méthode peut être utilisée pour déterminer si l’attribut personnalisé existe simplement. Une alternative plus simple, cependant, consiste à appeler le [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md) (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)

