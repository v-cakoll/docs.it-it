---
title: Metodo ICorDebugThread::SetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66f60b2342b6ff64f1329cbe57032291d5139384
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770596"
---
# <a name="icordebugthreadsetdebugstate-method"></a>Metodo ICorDebugThread::SetDebugState
Imposta i flag che descrivono lo stato di debug di ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `state`  
 [in] Combinazione bit per bit dei valori di enumerazione CorDebugThreadState che specificano lo stato di debug di questo thread.  
  
## <a name="remarks"></a>Note  
 `SetDebugState` Imposta lo stato di debug corrente del thread. (Lo "stato di debug corrente" rappresenta lo stato di debug se il processo di proseguire, non lo stato attuale). Il valore normale è THREAD_RUNNING. Solo il debugger può influire sullo stato di debug di un thread. Eseguire il debug di stati nelle ultime continua in modo che se si desidera mantenere un thread THREAD_SUSPEND più continua, è possibile impostarla una sola volta e successivamente non è necessario preoccuparsene. Sospensione di thread e la ripresa del processo può causare deadlock, anche se è in genere improbabile. Questa è una funzione intrinseca qualità di thread e processi e da progettazione. Un debugger in modo asincrono può interrompere e riprendere i thread per interrompere il deadlock. Se lo stato del thread utente include USER_UNSAFE_POINT, il thread può bloccare un'operazione di garbage collection (GC). Ciò significa che il thread sospeso dispone di una maggiore opportunità di causando un deadlock. Ciò potrebbe non influire sulle debug eventi già in coda. Pertanto un debugger debba svuotare la coda degli eventi intero (chiamando [HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) prima della sospensione o ripresa di thread. Altrimenti potrebbero ottenere gli eventi in un thread che ritiene di che avere già sospeso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
