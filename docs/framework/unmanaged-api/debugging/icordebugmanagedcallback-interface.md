---
title: Interfaccia ICorDebugManagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback
helpviewer_keywords:
- ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: b47f1d61-c7dc-4196-b926-0b08c94f7041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eacd10eecf2a8a2fc1b73a7f97eef5cb5eabafd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133718"
---
# <a name="icordebugmanagedcallback-interface"></a>Interfaccia ICorDebugManagedCallback
Fornisce metodi per l'elaborazione dei callback del debugger.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Break](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Notifica al debugger quando un <xref:System.Reflection.Emit.OpCodes.Break> un'istruzione nel flusso del codice.|  
|[Metodo Breakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Notifica il debugger quando viene rilevato un punto di interruzione.|  
|[Metodo BreakpointSetError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Notifica al debugger che common language runtime (CLR) è stato possibile associare con precisione un punto di interruzione è stata impostata prima di una funzione si trovava just-in-time (JIT) compilato.|  
|[Metodo ControlCTrap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Notifica al debugger che CTRL + C viene intercettata nel processo sottoposto a debug.|  
|[Metodo CreateAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Notifica al debugger che è stato creato un dominio dell'applicazione.|  
|[Metodo CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Quando un processo è stato collegato o avviato per la prima volta, invia una notifica del debugger.|  
|[Metodo CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Notifica al debugger che ha avviato un thread esegue codice gestito.|  
|[Metodo DebuggerError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento da CLR.|  
|[Metodo EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Deprecato. Notifica al debugger che è stato inviato un evento di modifica del mapping all'IDE.|  
|[Metodo EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Notifica al debugger che è stata completata una valutazione.|  
|[Metodo EvalException](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Notifica al debugger che una versione di valutazione è stata terminata con un'eccezione non gestita.|  
|[Metodo Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Notifica al debugger che è stata generata un'eccezione dal codice gestito.|  
|[Metodo ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Notifica al debugger che è stato chiuso un dominio dell'applicazione.|  
|[Metodo ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Notifica al debugger che un processo è stato terminato.|  
|[Metodo ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Notifica al debugger che un thread che stava eseguendo codice gestito è stato terminato.|  
|[Metodo LoadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Notifica al debugger che è stato caricato correttamente un assembly CLR.|  
|[Metodo LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Notifica al debugger che una classe è stata caricata.|  
|[Metodo LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Notifica al debugger che un modulo CLR è stato caricato correttamente.|  
|[Metodo LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Notifica al debugger che un thread gestito CLR ha chiamato un metodo <xref:System.Diagnostics.EventLog> classe per registrare un evento.|  
|[Metodo LogSwitch](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Notifica al debugger che un thread gestito CLR ha chiamato un metodo <xref:System.Diagnostics.Switch> classe da creare, modificare o eliminare un'opzione di debug/traccia.|  
|[Metodo NameChange](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Notifica al debugger che il nome del dominio dell'applicazione o thread è stato modificato.|  
|[Metodo StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Notifica al debugger che è stato completato un passaggio.|  
|[Metodo UnloadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Notifica al debugger che è stato scaricato un assembly CLR.|  
|[Metodo UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Notifica al debugger che è in corso lo scaricamento di una classe.|  
|[Metodo UnloadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Notifica al debugger che è stato scaricato un modulo CLR (DLL).|  
|[Metodo UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Notifica al debugger che sono stati modificati i simboli per un modulo CLR.|  
  
## <a name="remarks"></a>Note  
 Tutte le richiamate vengono serializzate, denominate nello stesso thread e denominate con il processo in stato sincronizzato.  
  
 Ogni implementazione del callback deve chiamare [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per riprendere l'esecuzione. Se `ICorDebugController::Continue` non viene chiamato prima del completamento del callback, il processo continuerà a rimanere arrestato e finché non si verificherà alcun callback degli eventi più `ICorDebugController::Continue` viene chiamato.  
  
 È necessario implementare un debugger [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) se il debug delle applicazioni di .NET Framework versione 2.0. Un'istanza di `ICorDebugManagedCallback` oppure `ICorDebugManagedCallback2` viene passato come oggetto di callback da [SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
