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
ms.openlocfilehash: b2429052173a187297b67c756213e5d27a79298b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792596"
---
# <a name="icordebugprocess-interface"></a>Interfaccia ICorDebugProcess
Rappresenta un processo che esegue codice gestito. Questa interfaccia è una sottoclasse di ICorDebugController.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ClearCurrentException](icordebugprocess-clearcurrentexception-method.md)|Cancella l'eccezione non gestita corrente sul thread specificato.|  
|[Metodo EnableLogMessages](icordebugprocess-enablelogmessages-method.md)|Abilita e Disabilita l'invio di messaggi di log al debugger.|  
|[Metodo EnumerateAppDomains](icordebugprocess-enumerateappdomains-method.md)|Enumera tutti i domini applicazione nel processo.|  
|[Metodo EnumerateObjects](icordebugprocess-enumerateobjects-method.md)|Non implementato.|  
|[Metodo GetHandle](icordebugprocess-gethandle-method.md)|Ottiene un handle per il processo.|  
|[Metodo GetHelperThreadID](icordebugprocess-gethelperthreadid-method.md)|Ottiene l'ID del thread del sistema operativo per il thread helper interno del debugger.|  
|[Metodo GetID](icordebugprocess-getid-method.md)|Ottiene l'ID del sistema operativo (OS) del processo.|  
|[Metodo GetObject](icordebugprocess-getobject-method.md)|Non implementato.|  
|[Metodo GetThread](icordebugprocess-getthread-method.md)|Ottiene l'istanza di ICorDebugThread con l'ID del thread del sistema operativo specificato.|  
|[Metodo GetThreadContext](icordebugprocess-getthreadcontext-method.md)|Ottiene il contesto per il thread specificato.|  
|[Metodo IsOSSuspended](icordebugprocess-isossuspended-method.md)|Determina se il thread è stato sospeso a causa dell'arresto del processo da parte del debugger.|  
|[Metodo IsTransitionStub](icordebugprocess-istransitionstub-method.md)|Determina se un indirizzo si trova all'interno di uno stub che provocherà una transizione al codice gestito.|  
|[Metodo ModifyLogSwitch](icordebugprocess-modifylogswitch-method.md)|Imposta il livello di gravità dell'opzione di log specificata.|  
|[Metodo ReadMemory](icordebugprocess-readmemory-method.md)|Legge la memoria dal processo.|  
|[Metodo SetThreadContext](icordebugprocess-setthreadcontext-method.md)|Imposta il contesto per il thread specificato.|  
|[Metodo ThreadForFiberCookie](icordebugprocess-threadforfibercookie-method.md)|Deprecato.|  
|[Metodo WriteMemory](icordebugprocess-writememory-method.md)|Scrive i dati in un'area di memoria nel processo.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
