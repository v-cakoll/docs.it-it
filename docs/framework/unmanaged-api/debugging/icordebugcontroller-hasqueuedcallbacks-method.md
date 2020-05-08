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
ms.openlocfilehash: bd656445c2451d0583ddbc45e71c9e090bb80305
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892784"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>Metodo ICorDebugController::HasQueuedCallbacks
Ottiene un valore che indica se i callback gestiti sono attualmente in coda per il thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pThread`  
 in Puntatore a un oggetto "ICorDebugThread" che rappresenta il thread.  
  
 `pbQueued`  
 out Puntatore a un valore che è `true` se sono attualmente presenti callback gestiti in coda per il thread specificato. in caso `false`contrario,.  
  
 Se viene specificato null per il `pThread` parametro, `HasQueuedCallbacks` restituirà `true` se sono presenti callback attualmente gestiti in coda per qualsiasi thread.  
  
## <a name="remarks"></a>Osservazioni  
 I callback verranno inviati uno alla volta, ogni volta che viene chiamato [ICorDebugController:: continue](icordebugcontroller-continue-method.md) . Il debugger può verificare questo flag se desidera segnalare più eventi di debug che si verificano simultaneamente.  
  
 Quando gli eventi di debug sono accodati, si sono già verificati, pertanto il debugger deve svuotare l'intera coda per assicurarsi che lo stato dell'oggetto del debug. (Chiamare `ICorDebugController::Continue` per svuotare la coda). Se, ad esempio, la coda contiene due eventi di debug sul thread *x*e il debugger sospende il thread *x* dopo il primo evento di debug e `ICorDebugController::Continue`quindi chiama, il secondo evento di debug per il thread *x* verrà inviato anche se il thread è stato sospeso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
