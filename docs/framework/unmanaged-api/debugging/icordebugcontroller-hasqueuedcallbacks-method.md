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
ms.openlocfilehash: c33193bd64030852441c7ca60cee4a000b09156c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788918"
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
 out Puntatore a un valore `true` se sono attualmente presenti callback gestiti in coda per il thread specificato. in caso contrario, `false`.  
  
 Se viene specificato null per il parametro `pThread`, `HasQueuedCallbacks` restituirà `true` se sono presenti callback attualmente gestiti in coda per qualsiasi thread.  
  
## <a name="remarks"></a>Note  
 I callback verranno inviati uno alla volta, ogni volta che viene chiamato [ICorDebugController:: continue](icordebugcontroller-continue-method.md) . Il debugger può verificare questo flag se desidera segnalare più eventi di debug che si verificano simultaneamente.  
  
 Quando gli eventi di debug sono accodati, si sono già verificati, pertanto il debugger deve svuotare l'intera coda per assicurarsi che lo stato dell'oggetto del debug. Chiamare `ICorDebugController::Continue` per svuotare la coda. Se, ad esempio, la coda contiene due eventi di debug sul thread *x*e il debugger sospende il thread *x* dopo il primo evento di debug e quindi chiama `ICorDebugController::Continue`, il secondo evento di debug per il thread *x* verrà inviato anche se il thread è stato sospeso.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
