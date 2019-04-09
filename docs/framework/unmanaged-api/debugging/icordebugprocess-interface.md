---
title: Interfaccia ICorDebugProcess
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d96d66f16cd956d8fab1afe00486d564e37953
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216795"
---
# <a name="icordebugprocess-interface"></a>Interfaccia ICorDebugProcess
Rappresenta un processo che esegue codice gestito. Questa interfaccia è una sottoclasse di ICorDebugController.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Cancella l'eccezione non gestita corrente sul thread specificato.|  
|[Metodo EnableLogMessages](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Abilita e disabilita l'invio di messaggi di log per il debugger.|  
|[Metodo EnumerateAppDomains](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Enumera tutti i domini applicazione nel processo.|  
|[Metodo EnumerateObjects](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Non implementato.|  
|[Metodo GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Ottiene un handle per il processo.|  
|[Metodo GetHelperThreadID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Ottiene l'ID del thread del sistema operativo (OS) per il thread di supporto interno del debugger.|  
|[Metodo GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Ottiene l'ID del sistema operativo (OS) del processo.|  
|[Metodo GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Non implementato.|  
|[Metodo GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Ottiene l'istanza ICorDebugThread con il thread del sistema operativo specificato ID.|  
|[Metodo GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Ottiene il contesto per il thread specificato.|  
|[Metodo IsOSSuspended](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Determina se il thread è stata sospesa a causa del debugger l'interruzione del processo.|  
|[Metodo IsTransitionStub](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Determina se un indirizzo è all'interno di uno stub che causa una transizione al codice gestito.|  
|[Metodo ModifyLogSwitch](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Imposta il livello di gravità dell'opzione di log specificato.|  
|[Metodo ReadMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Legge memoria dal processo.|  
|[Metodo SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Imposta il contesto per il thread specificato.|  
|[Metodo ThreadForFiberCookie](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Deprecato.|  
|[Metodo WriteMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Scrive dati in un'area di memoria del processo.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
