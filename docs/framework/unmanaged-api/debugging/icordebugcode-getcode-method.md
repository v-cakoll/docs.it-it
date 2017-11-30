---
title: Metodo ICorDebugCode::GetCode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12820d0be725c92754640aaa4eebca56bbc33ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcodegetcode-method"></a>Metodo ICorDebugCode::GetCode
Ottiene il codice per la funzione specificata, formattata per il disassembly. Questo metodo è obsoleto in .NET Framework versione 2.0. Utilizzare [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
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
 Se il codice della funzione è stato suddiviso in più blocchi, questi vengono concatenati in ordine crescente di offset nativo. Non vengono controllati i limiti di istruzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche  
 [GetCodeChunks (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
