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
ms.openlocfilehash: 96dedcd27e87c5afc504e7840100eb121410675e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130751"
---
# <a name="icordebugmanagedcallback-interface"></a>Interfaccia ICorDebugManagedCallback
Fornisce metodi per l'elaborazione dei callback del debugger.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Break](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Notifica al debugger quando viene eseguita un'istruzione <xref:System.Reflection.Emit.OpCodes.Break> nel flusso di codice.|  
|[Metodo Breakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Notifica al debugger quando viene rilevato un punto di interruzione.|  
|[Metodo BreakpointSetError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Notifica al debugger che la Common Language Runtime (CLR) non è stata in grado di associare accuratamente un punto di interruzione impostato prima della compilazione JIT (just-in-Time) di una funzione.|  
|[Metodo ControlCTrap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Notifica al debugger che la combinazione di tasti CTRL + C è bloccata nel processo di cui è in corso il debug.|  
|[Metodo CreateAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Notifica al debugger che è stato creato un dominio dell'applicazione.|  
|[Metodo CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Notifica al debugger il momento in cui un processo è stato collegato o avviato per la prima volta.|  
|[Metodo CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Notifica al debugger che un thread ha avviato l'esecuzione del codice gestito.|  
|[Metodo DebuggerError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento da CLR.|  
|[Metodo EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Deprecato. Notifica al debugger che è stato inviato un evento di modifica del mapping all'IDE.|  
|[Metodo EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Notifica al debugger che la valutazione è stata completata.|  
|[Metodo EvalException](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Notifica al debugger che una valutazione è stata terminata con un'eccezione non gestita.|  
|[Metodo Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Notifica al debugger che è stata generata un'eccezione dal codice gestito.|  
|[Metodo ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Notifica al debugger che un dominio applicazione è stato terminato.|  
|[Metodo ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Notifica al debugger che un processo è stato terminato.|  
|[Metodo ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Notifica al debugger che un thread che stava eseguendo il codice gestito è stato terminato.|  
|[Metodo LoadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Notifica al debugger che un assembly CLR è stato caricato correttamente.|  
|[Metodo LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Notifica al debugger che è stata caricata una classe.|  
|[Metodo LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Notifica al debugger che un modulo CLR è stato caricato correttamente.|  
|[Metodo LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Notifica al debugger che un thread gestito da CLR ha chiamato un metodo nella classe <xref:System.Diagnostics.EventLog> per registrare un evento.|  
|[Metodo LogSwitch](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Notifica al debugger che un thread gestito da CLR ha chiamato un metodo nella classe <xref:System.Diagnostics.Switch> per creare, modificare o eliminare un'opzione di debug/traccia.|  
|[Metodo NameChange](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Notifica al debugger che il nome di un dominio dell'applicazione o di un thread è stato modificato.|  
|[Metodo StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Notifica al debugger il completamento di un passaggio.|  
|[Metodo UnloadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Notifica al debugger che è stato scaricato un assembly CLR.|  
|[Metodo UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Notifica al debugger che una classe viene scaricata.|  
|[Metodo UnloadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Notifica al debugger che un modulo CLR (DLL) è stato scaricato.|  
|[Metodo UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Notifica al debugger che i simboli per un modulo CLR sono stati modificati.|  
  
## <a name="remarks"></a>Note  
 Tutti i callback vengono serializzati, chiamati nello stesso thread e chiamati con il processo nello stato SYNCHRONIZED.  
  
 Ogni implementazione di callback deve chiamare [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per riprendere l'esecuzione. Se `ICorDebugController::Continue` non viene chiamato prima che il callback venga restituito, il processo resterà interrotto e non si verificheranno ulteriori callback di evento fino a quando non viene chiamato `ICorDebugController::Continue`.  
  
 Un debugger deve implementare [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) se esegue il debug di applicazioni .NET Framework versione 2,0. Un'istanza di `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` viene passata come oggetto callback a [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
