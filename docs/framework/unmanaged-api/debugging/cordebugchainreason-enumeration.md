---
title: Enumerazione CorDebugChainReason
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e46118e97a4b888a16f12cf6705d2b7e67bbf7ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740355"
---
# <a name="cordebugchainreason-enumeration"></a>Enumerazione CorDebugChainReason
Indica i motivi che determinano l'avvio di una catena di chiamate.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`CHAIN_NONE`|Non è stata avviata alcuna catena di chiamate.|  
|`CHAIN_CLASS_INIT`|La catena è stata avviata da un costruttore.|  
|`CHAIN_EXCEPTION_FILTER`|La catena è stata avviata da un filtro di eccezione.|  
|`CHAIN_SECURITY`|La catena è stata avviata dal codice che applica la sicurezza.|  
|`CHAIN_CONTEXT_POLICY`|La catena è stata avviata da un criterio di contesto.|  
|`CHAIN_INTERCEPTION`|Non usato.|  
|`CHAIN_PROCESS_START`|Non usato.|  
|`CHAIN_THREAD_START`|La catena è stata avviata dall'avvio dell'esecuzione di un thread.|  
|`CHAIN_ENTER_MANAGED`|La catena è stata avviata da una voce nel codice gestito.|  
|`CHAIN_ENTER_UNMANAGED`|La catena è stata avviata da una voce nel codice non gestito.|  
|`CHAIN_DEBUGGER_EVAL`|Non usato.|  
|`CHAIN_CONTEXT_SWITCH`|Non usato.|  
|`CHAIN_FUNC_EVAL`|La catena è stata avviata da una valutazione della funzione.|  
  
## <a name="remarks"></a>Note  
 Usare la [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) metodo per accertare i motivi per l'avvio di una catena di chiamate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
