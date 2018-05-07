---
title: Metodo ICorDebugProcess::WriteMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6da4c282c7f969a406a657d1e30dd6120a32b4e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocesswritememory-method"></a>Metodo ICorDebugProcess::WriteMemory
Scrive dati in un'area di memoria nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a>Parametri  
 `address`  
 [in] Oggetto `CORDB_ADDRESS` valore corrispondente all'indirizzo di base dell'area di memoria per i dati viene scritto. Prima che si verifichi il trasferimento dei dati, il sistema verifica che l'area di memoria della dimensione specificata, a partire dall'indirizzo di base, sia accessibile in scrittura. Se non è accessibile, il metodo ha esito negativo.  
  
 `size`  
 [in] Il numero di byte da scrivere nell'area di memoria.  
  
 `buffer`  
 [in] Un buffer contenente dati da scrivere.  
  
 `written`  
 [out] Un puntatore a una variabile che riceve il numero di byte scritti nell'area di memoria nel processo. Se `written` è NULL, questo parametro viene ignorato.  
  
## <a name="remarks"></a>Note  
 Dati vengono scritti automaticamente dietro i punti di interruzione. In .NET Framework versione 2.0, il debugger nativo non deve utilizzare questo metodo per inserire punti di interruzione nel flusso di istruzioni. Utilizzare [ICorDebugProcess2::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) invece.  
  
 Il `WriteMemory` metodo deve essere utilizzato solo all'esterno di codice gestito. Questo metodo può danneggiare il runtime, se utilizzato in modo non corretto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
