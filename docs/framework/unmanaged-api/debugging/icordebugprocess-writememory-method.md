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
ms.openlocfilehash: eaf5b9980d55b0efb473b4631a8c052b013d0796
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137262"
---
# <a name="icordebugprocesswritememory-method"></a>Metodo ICorDebugProcess::WriteMemory
Scrive i dati in un'area di memoria in questo processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 in Valore `CORDB_ADDRESS` che rappresenta l'indirizzo di base dell'area di memoria in cui vengono scritti i dati. Prima che si verifichi il trasferimento dei dati, il sistema verifica che l'area di memoria della dimensione specificata, a partire dall'indirizzo di base, sia accessibile per la scrittura. Se non è accessibile, il metodo ha esito negativo.  
  
 `size`  
 in Numero di byte da scrivere nell'area di memoria.  
  
 `buffer`  
 in Buffer contenente i dati da scrivere.  
  
 `written`  
 out Puntatore a una variabile che riceve il numero di byte scritti nell'area di memoria del processo. Se `written` è NULL, questo parametro viene ignorato.  
  
## <a name="remarks"></a>Note  
 I dati vengono scritti automaticamente dietro i punti di interruzione. In .NET Framework versione 2,0 i debugger nativi non devono usare questo metodo per inserire i punti di interruzione nel flusso di istruzioni. Usare invece [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) .  
  
 Il metodo `WriteMemory` deve essere utilizzato solo all'esterno del codice gestito. Questo metodo può danneggiare il runtime se usato in modo errato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
