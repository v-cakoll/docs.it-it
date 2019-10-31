---
title: Enumerazione CorDebugDebugEventKind
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
ms.openlocfilehash: de4ac1f39ea9cfb4b616bd4e2c85e5de530dbb0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132222"
---
# <a name="cordebugdebugeventkind-enumeration"></a>Enumerazione CorDebugDebugEventKind
Indica il tipo di evento le cui informazioni sono decodificate dal metodo [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|Evento di caricamento del modulo.|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|Evento di scaricamento del modulo.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|Eccezione first-chance.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|Eccezione utente first-chance.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|Eccezione per la quale esiste un gestore `catch`.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|Eccezione non gestita.|  
  
## <a name="remarks"></a>Note  
 Un membro dell'enumerazione `CorDebugDebugEventKind` viene restituito chiamando il metodo [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .  
  
> [!NOTE]
> Questa enumerazione è progettata per l'uso solo in scenari di debug di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
