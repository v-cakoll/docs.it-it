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
ms.openlocfilehash: 4599bf310a0b819bc662b90a5a86e87ac27c37b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737011"
---
# <a name="icordebugprocesswritememory-method"></a>Metodo ICorDebugProcess::WriteMemory
Scrive dati in un'area di memoria di questo processo.  
  
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
 [in] Oggetto `CORDB_ADDRESS` valore, ovvero l'indirizzo di base dell'area di memoria a dati che viene scritto. Prima che si verifichi il trasferimento dei dati, il sistema verifica che l'area di memoria della dimensione specificata, iniziando in corrispondenza l'indirizzo di base, sia accessibile in scrittura. Se non è accessibile, il metodo ha esito negativo.  
  
 `size`  
 [in] Il numero di byte da scrivere nell'area di memoria.  
  
 `buffer`  
 [in] Un buffer contenente dati da scrivere.  
  
 `written`  
 [out] Un puntatore a una variabile che riceve il numero di byte scritti nell'area di memoria di questo processo. Se `written` è NULL, questo parametro viene ignorato.  
  
## <a name="remarks"></a>Note  
 Dati vengono scritti automaticamente protetti da qualsiasi punto di interruzione. In .NET Framework versione 2.0, debugger nativo non devono usare questo metodo per inserire i punti di interruzione nel flusso di istruzioni. Uso [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) invece.  
  
 Il `WriteMemory` metodo deve essere usato solo all'esterno di codice gestito. Questo metodo può danneggiare il runtime se utilizzato in modo non corretto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
