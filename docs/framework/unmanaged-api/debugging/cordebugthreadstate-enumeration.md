---
title: Enumerazione CorDebugThreadState
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba8bca6d14308284c869b923853f7e27e045bca5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugthreadstate-enumeration"></a>Enumerazione CorDebugThreadState
Specifica lo stato di un thread per il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`THREAD_RUN`|Il thread viene eseguito liberamente, a meno che non si verifica un evento di debug.|  
|`THREAD_SUSPEND`|Impossibile eseguire il thread.|  
  
## <a name="remarks"></a>Note  
 Il debugger usa il `CorDebugThreadState` enumerazione per controllare l'esecuzione di un thread. Lo stato di un thread può essere impostato utilizzando il [ICorDebugThread:: SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) metodo.  
  
 Un callback fornito per il [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md) consente la distribuzione dei messaggi, pertanto non è necessario uno stato interrotto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, CorDegug.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
