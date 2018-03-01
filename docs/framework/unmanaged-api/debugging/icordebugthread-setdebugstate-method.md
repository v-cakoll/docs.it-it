---
title: Metodo ICorDebugThread::SetDebugState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2754caf11f89358b3e81e6324835d5b2e12f17e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a>Metodo ICorDebugThread::SetDebugState
Imposta i flag che descrivono lo stato di debug di ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `state`  
 [in] Combinazione bit per bit dei valori di enumerazione CorDebugThreadState che specificano lo stato di debug di questo thread.  
  
## <a name="remarks"></a>Note  
 `SetDebugState`Imposta lo stato di debug corrente del thread. (Lo "stato di debug corrente" rappresenta lo stato di debug se il processo continua, non lo stato attuale). Il valore normale è THREAD_RUNNING. Solo il debugger può incidere lo stato di debug di un thread. Gli stati di debug ultimo attraverso continua, pertanto se si desidera mantenere un thread THREAD_SUSPEND più continua, è possibile impostarla una sola volta e successivamente non è necessario preoccuparsene. Sospensione di thread e riprendere il processo può provocare deadlock, anche se è in genere improbabile. Si tratta di una qualità intrinseca dei thread e processi e da progettazione. Un debugger in modo asincrono può interrompere e riprendere i thread per interrompere il deadlock. Se lo stato del thread utente include USER_UNSAFE_POINT, il thread può bloccare un'operazione di garbage collection (GC). Ciò significa che il thread sospeso è più facile di causare un deadlock. Questo potrebbe non influire sulle già in coda gli eventi di debug. Pertanto, un debugger deve svuotare la coda degli eventi intero (chiamando [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) prima della sospensione o ripresa di thread. In caso contrario, può ottenere eventi in un thread che ritiene di che avere già sospeso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
