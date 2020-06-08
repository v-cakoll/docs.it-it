---
title: Metodo ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: e2e911fb1d737ebb6b2106c89ac11335788ace4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501729"
---
# <a name="isymunmanagedwriterclosescope-method"></a>Metodo ISymUnmanagedWriter::CloseScope
Chiude l'ambito lessicale corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a>Parametri  
 `endOffset`  
 in Offset dall'inizio del metodo del punto alla fine dell'ultima istruzione nell'ambito lessicale, espresso in byte.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Osservazioni  
 Una volta chiuso un ambito, non è possibile definire altre variabili al suo interno.  
  
 [ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) per definire in un secondo momento l'offset iniziale e finale dell'ambito. In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` saranno ignorati. Gli identificatori di ambito sono validi solo nel metodo corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
