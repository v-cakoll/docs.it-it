---
title: Metodo ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: c2e8aaa2774e3e2699a73c40804391ca245047b1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976590"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>Metodo ICorDebugController::SetAllThreadsDebugState
Imposta lo stato di debug di tutti i thread gestiti nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `state`  
 in Valore dell'enumerazione "CorDebugThreadState" che specifica lo stato del thread per il debug.  
  
 `pExceptThisThread`  
 in Puntatore a un oggetto "ICorDebugThread" che rappresenta un thread da esentare dall'impostazione dello stato di debug. Se questo valore è null, non viene esentato alcun thread.  
  
## <a name="remarks"></a>Osservazioni  
 Il `SetAllThreadsDebugState` metodo può influire sui thread che non sono visibili tramite il [Metodo EnumerateThreads](icordebugcontroller-enumeratethreads-method.md), quindi i thread sospesi con il `SetAllThreadsDebugState` metodo dovranno essere ripresi con `SetAllThreadsDebugState` il metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
