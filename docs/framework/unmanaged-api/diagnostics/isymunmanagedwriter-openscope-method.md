---
title: Metodo ISymUnmanagedWriter::OpenScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
ms.openlocfilehash: 2808606be24399c9a4fe03df4c53202d31cbbe91
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501716"
---
# <a name="isymunmanagedwriteropenscope-method"></a>Metodo ISymUnmanagedWriter::OpenScope
Apre un nuovo ambito lessicale nel metodo corrente. L'ambito diventa il nuovo ambito corrente e viene inserito in uno stack di ambiti. Gli ambiti devono formare una gerarchia. Gli elementi di pari livello non possono sovrapporsi.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Parametri  
 `startOffset`  
 in Offset della prima istruzione nell'ambito lessicale, in byte, dall'inizio del metodo.  
  
 `pRetVal`  
 out Puntatore a un oggetto `ULONG32` che riceve l'identificatore dell'ambito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="remarks"></a>Osservazioni  
 `ISymUnmanagedWriter::OpenScope`Restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) per definire un offset iniziale e finale dell'ambito in un secondo momento. In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) vengono ignorati. Gli identificatori di ambito sono validi solo nel metodo corrente.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
