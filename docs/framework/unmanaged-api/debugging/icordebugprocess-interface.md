---
title: ICorDebugProcess Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess
helpviewer_keywords: ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee526a79d89a9e4e3483daa07a512b6b7f920e70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess-interface1"></a>ICorDebugProcess Interface1
Rappresenta un processo che esegue codice gestito. Questa interfaccia è una sottoclasse di ICorDebugController.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ClearCurrentException (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Cancella l'eccezione non gestita corrente sul thread specificato.|  
|[EnableLogMessages (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Abilita e disabilita l'invio di messaggi di log al debugger.|  
|[EnumerateAppDomains (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Enumera tutti i domini applicazione nel processo.|  
|[EnumerateObjects (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Non implementato.|  
|[GetHandle (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Ottiene un handle per il processo.|  
|[GetHelperThreadID (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Ottiene l'ID di thread del sistema operativo (sistema operativo) per il thread di supporto interno del debugger.|  
|[GetID (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Ottiene l'ID del sistema operativo () del processo.|  
|[GetObject (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Non implementato.|  
|[GetThread (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Ottiene l'ID istanza ICorDebugThread che contiene il thread del sistema operativo specificato.|  
|[GetThreadContext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Ottiene il contesto per il thread specificato.|  
|[IsOSSuspended (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Determina se il thread è stata sospesa a causa del debugger arrestando il processo.|  
|[IsTransitionStub (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Determina se un indirizzo è all'interno di uno stub che causerà una transizione da codice gestito.|  
|[ModifyLogSwitch (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Imposta il livello di gravità dell'opzione di log specificato.|  
|[ReadMemory (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Legge memoria dal processo.|  
|[SetThreadContext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Imposta il contesto per il thread specificato.|  
|[ThreadForFiberCookie (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Deprecato.|  
|[WriteMemory (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Scrive dati in un'area di memoria del processo.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
