---
title: Metodo ISymUnmanagedWriter::SetScopeRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d7fe8f36c7a5dbe6e715402fd7253092b64e68e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078967"
---
# <a name="isymunmanagedwritersetscoperange-method"></a>Metodo ISymUnmanagedWriter::SetScopeRange
Definisce l'intervallo di offset per l'ambito lessicale specificato. L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti. Gli ambiti devono formare una gerarchia. Elementi di pari livello non possono sovrapporsi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a>Parametri  
 `scopeId`  
 [in] L'identificatore di ambito per l'ambito.  
  
 `startOffset`  
 [in] Offset, in byte, della prima istruzione dell'ambito lessicale a partire dall'inizio del metodo.  
  
 `endOffset`  
 [in] Offset, in byte, dell'ultima istruzione nell'ambito lessicale a partire dall'inizio del metodo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="remarks"></a>Note  
 [ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere usato con `ISymUnmanagedWriter::SetScopeRange` per definire un ambito dell'offset iniziale e finale in un secondo momento. In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati. Gli identificatori di ambito solo sono validi nel metodo corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
