---
title: IDebugDisassemblyStream2::Read | Microsoft Docs
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
- IDebugDisassemblyStream2::Read
helpviewer_keywords:
- IDebugDisassemblyStream2::Read
ms.assetid: 7db5f6bb-73ee-45bc-b187-c1b6aa2dfdd5
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9bfa4fec20b715493a4f2f74c4a19aa845a44916
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51725783"
---
# <a name="idebugdisassemblystream2read"></a>IDebugDisassemblyStream2::Read
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Lit les instructions à partir de la position actuelle dans le flux de code machine.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Read(   
   DWORD                     dwInstructions,  
   DISASSEMBLY_STREAM_FIELDS dwFields,  
   DWORD*                    pdwInstructionsRead,  
   DisassemblyData*          prgDisassembly  
);  
```  
  
```csharp  
int Read(   
   uint                           dwInstructions,  
   enum_DISASSEMBLY_STREAM_FIELDS dwFields,  
   out uint                       pdwInstructionsRead,  
   DisassemblyData[]              prgDisassembly  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dwInstructions`  
 [in] Le nombre d’instructions à désassembler. Cette valeur est également la longueur maximale de la `prgDisassembly` tableau.  
  
 `dwFields`  
 [in] Une combinaison d’indicateurs de la [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) énumération qui indiquent quels champs de `prgDisassembly` doivent être remplis.  
  
 `pdwInstructionsRead`  
 [out] Retourne le nombre d’instructions réellement désassemblé.  
  
 `prgDisassembly`  
 [out] Un tableau de [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) structures qui contient le code désassemblé, une structure par instruction désassemblée. La longueur de ce tableau est déterminée par le `dwInstructions` paramètre.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Le nombre maximal d’instructions qui sont disponibles dans l’étendue actuelle peut être obtenu en appelant le [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md) (méthode).  
  
 La position actuelle où l’instruction suivante est lue à partir de peut être modifiée en appelant le [recherche](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) (méthode).  
  
 Le `DSF_OPERANDS_SYMBOLS` indicateur peut être ajouté à la `DSF_OPERANDS` indicateur dans le `dwFields` paramètre pour indiquer que les noms de symboles doivent être utilisés lors du désassemblage d’instructions.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)   
 [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)

