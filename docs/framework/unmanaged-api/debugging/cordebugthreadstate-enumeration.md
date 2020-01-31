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
ms.openlocfilehash: 69a8aabd1d79bb9bb4248259c99124ce50677600
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789236"
---
# <a name="cordebugthreadstate-enumeration"></a>Enumerazione CorDebugThreadState
Specifica lo stato di un thread per il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`THREAD_RUN`|Il thread viene eseguito liberamente, a meno che non si verifichi un evento di debug.|  
|`THREAD_SUSPEND`|Impossibile eseguire il thread.|  
  
## <a name="remarks"></a>Note  
 Il debugger usa l'enumerazione `CorDebugThreadState` per controllare l'esecuzione di un thread. Lo stato di un thread può essere impostato tramite il metodo [ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) .  
  
 Un callback fornito all' [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md) consente il pumping dei messaggi, pertanto non è necessario uno stato interrotto.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
