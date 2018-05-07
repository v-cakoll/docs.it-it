---
title: Metodo ICorDebugController::HasQueuedCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eba265b727d00690ab77c6ae831e954d59df7c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>Metodo ICorDebugController::HasQueuedCallbacks
Ottiene un valore che indica se i callback gestiti attualmente in coda per il thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pThread`  
 [in] Un puntatore a un oggetto "ICorDebugThread" che rappresenta il thread.  
  
 `pbQueued`  
 [out] Un puntatore a un valore che è `true` se qualsiasi callback gestiti sono attualmente in coda per il thread specificato; in caso contrario, `false`.  
  
 Se si specifica null per il `pThread` parametro `HasQueuedCallbacks` restituirà `true` se non esistono attualmente callback gestiti in coda per uno o più thread.  
  
## <a name="remarks"></a>Note  
 I callback saranno inviati uno alla volta, ogni volta che [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) viene chiamato. Il debugger è possibile controllare questo flag se si desiderano segnalare gli eventi di debug più che si verificano simultaneamente.  
  
 Quando si trovano nella coda degli eventi di debug, che si è già verificata, affinché il debugger deve svuotare l'intera coda per essere certi che dello stato dell'oggetto del debug. (Chiamare `ICorDebugController::Continue` per svuotare la coda.) Ad esempio, se la coda contiene due eventi di debug nel thread *X*, e il debugger sospende il thread *X* dopo il primo evento di debug, quindi chiama `ICorDebugController::Continue`, il secondo evento di debug per thread *X* verranno inviati anche se il thread è stata sospesa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 
