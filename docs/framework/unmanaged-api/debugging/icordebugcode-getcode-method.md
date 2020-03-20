---
title: Metodo ICorDebugCode::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178991"
---
# <a name="icordebugcodegetcode-method"></a>Metodo ICorDebugCode::GetCode
Ottiene tutto il codice per la funzione specificata, formattato per il disassembly. Questo metodo è stato deprecato in .NET Framework versione 2.0. Utilizzare [invece ICorDebugCode2::GetCodeChunks.](icordebugcode2-getcodechunks-method.md)  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `startOffset`  
 [in] Offset dell'inizio della funzione.  
  
 `endOffset`  
 [in] Offset della fine della funzione.  
  
 `cBufferAlloc`  
 [in] Dimensione della `buffer` matrice in cui verrà restituito il codice.  
  
 `buffer`  
 [fuori] Matrice in cui verrà restituito il codice.  
  
 `pcBufferSize`  
 [fuori] Numero di byte restituiti.  
  
## <a name="remarks"></a>Osservazioni  
 Se il codice della funzione è stato suddiviso in più blocchi, vengono concatenati in ordine di offset nativo crescente. I limiti delle istruzioni non vengono controllati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 Versioni di **.NET Framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetCodeChunks](icordebugcode2-getcodechunks-method.md)
