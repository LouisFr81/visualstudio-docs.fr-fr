---
title: IDebugSourceServerModule::GetSourceServerData | Microsoft Docs
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
- IDebugSourceServerModule::GetSourceServerData
ms.assetid: f15d86aa-1bd9-4b16-a64a-21b01c27db2e
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8404ab81f9ba797f5dc81ab23188492f4a4d1393
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51741597"
---
# <a name="idebugsourceservermodulegetsourceserverdata"></a>IDebugSourceServerModule::GetSourceServerData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Récupère un tableau d’informations du serveur source.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetSourceServerData(  
   ULONG* pDataByteCount,   
   BYTE** ppData  
);  
```  
  
```csharp  
public int GetSourceServerData(  
   out uint  pDataByteCount,   
   out int[] ppData  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pDataByteCount`  
 [out] Nombre d’octets dans le tableau de données.  
  
 `ppData`  
 [out] Référence au tableau de données.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment implémenter cette méthode pour un **CModule** objet qui expose le [IDebugSourceServerModule](../../../extensibility/debugger/reference/idebugsourceservermodule.md) interface.  
  
```cpp#  
HRESULT CModule::GetSourceServerData(ULONG* pDataByteCount, BYTE** ppData)  
{  
    HRESULT hr = S_OK;  
    CComPtr<ISymUnmanagedReader> pSymReader;  
    CComPtr<ISymUnmanagedSourceServerModule> pSourceServerModule;  
  
    IfFalseGo( pDataByteCount && ppData, E_INVALIDARG );  
    *pDataByteCount = 0;  
    *ppData = NULL;  
  
    IfFailGo( this->GetUnmanagedSymReader( &pSymReader ) );  
    IfFailGo( pSymReader->QueryInterface( &pSourceServerModule ) );  
  
    IfFailGo( pSourceServerModule->GetSourceServerData( pDataByteCount, ppData ) );  
  
Error:  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugSourceServerModule](../../../extensibility/debugger/reference/idebugsourceservermodule.md)

