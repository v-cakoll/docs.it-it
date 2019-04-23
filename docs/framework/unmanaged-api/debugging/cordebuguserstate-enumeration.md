---
title: Enumerazione CorDebugUserState
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54b2af6e7a200db89bfd7335868a629d7a886fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141310"
---
# <a name="cordebuguserstate-enumeration"></a>Enumerazione CorDebugUserState
Indica lo stato utente di un thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>Membri  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|È stata richiesta la terminazione del thread.|  
|`USER_SUSPEND_REQUESTED`|È stata richiesta una sospensione del thread.|  
|`USER_BACKGROUND`|Il thread è in esecuzione in background.|  
|`USER_UNSTARTED`|Il thread non ha avviato l'esecuzione.|  
|`USER_STOPPED`|Il thread è stato terminato.|  
|`USER_WAIT_SLEEP_JOIN`|Il thread è in attesa di un altro thread completare un'attività.|  
|`USER_SUSPENDED`|Il thread è stato sospeso.|  
|`USER_UNSAFE_POINT`|Il thread è in un punto non sicuro. Vale a dire, il thread è in un punto nell'esecuzione in cui potrebbe bloccare l'operazione di garbage collection.<br /><br /> Eseguire il debug gli eventi possono essere inviati dai punti di tipo unsafe, ma la sospensione di un thread in un punto dell'unsafe molto probabilmente provocherà un deadlock finché non viene ripreso il thread. I punti sicuri e sono determinati dalla just-in-time (JIT) e dall'implementazione di garbage collection.|  
|`USER_THREADPOOL`|Il thread è il pool di thread.|  
  
## <a name="remarks"></a>Note  
 Lo stato utente di un thread è lo stato in cui il thread ha quando lo esamina il debugger. Un thread può avere una combinazione di stati utente.  
  
 Usare la [GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) metodo per recuperare lo stato utente del thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
