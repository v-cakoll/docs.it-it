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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e18097dd380ee354e5652886544d40da074f1230
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747618"
---
# <a name="icordebugcodegetcode-method"></a>Metodo ICorDebugCode::GetCode
Ottiene tutto il codice per la funzione specificata, formattata per il disassembly. Questo metodo è stato deprecato in .NET Framework versione 2.0. Uso [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) invece.  
  
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
 [in] L'offset dell'inizio della funzione.  
  
 `endOffset`  
 [in] L'offset della fine della funzione.  
  
 `cBufferAlloc`  
 [in] Le dimensioni del `buffer` della matrice in cui verrà restituito il codice.  
  
 `buffer`  
 [out] Matrice in cui verrà restituito il codice.  
  
 `pcBufferSize`  
 [out] Il numero di byte restituiti.  
  
## <a name="remarks"></a>Note  
 Se il codice della funzione è stato diviso in più blocchi, questi vengono concatenati in ordine crescente offset nativo. I limiti di istruzioni non vengono controllati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
