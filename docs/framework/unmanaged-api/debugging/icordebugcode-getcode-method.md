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
ms.openlocfilehash: db24228de7e8c98fd97f890b1e408515172299b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125662"
---
# <a name="icordebugcodegetcode-method"></a>Metodo ICorDebugCode::GetCode
Ottiene tutto il codice per la funzione specificata, formattato per il disassembly. Questo metodo è stato deprecato nella versione .NET Framework 2,0. Usare invece [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .  
  
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
 in Offset dell'inizio della funzione.  
  
 `endOffset`  
 in Offset della fine della funzione.  
  
 `cBufferAlloc`  
 in Dimensioni della matrice di `buffer` in cui verrà restituito il codice.  
  
 `buffer`  
 out Matrice nella quale verrà restituito il codice.  
  
 `pcBufferSize`  
 out Numero di byte restituiti.  
  
## <a name="remarks"></a>Note  
 Se il codice della funzione è stato diviso in più blocchi, viene concatenato in ordine di aumento dell'offset nativo. I limiti delle istruzioni non sono controllati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 1,1, 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
