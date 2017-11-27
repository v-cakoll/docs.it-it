---
title: Interfaccia ICorDebugManagedCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback
helpviewer_keywords: ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: b47f1d61-c7dc-4196-b926-0b08c94f7041
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b72a2814ee2276363152052c7bf734104d4f395
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback-interface"></a>Interfaccia ICorDebugManagedCallback
Fornisce metodi per l'elaborazione dei callback del debugger.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Break (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Notifica al debugger quando un <xref:System.Reflection.Emit.OpCodes.Break> un'istruzione nel flusso del codice.|  
|[Breakpoint (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Notifica al debugger quando viene rilevato un punto di interruzione.|  
|[BreakpointSetError (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Notifica al debugger che common language runtime (CLR): Impossibile associare con precisione un punto di interruzione impostato prima della compilazione just-in-time (JIT) compilata di una funzione.|  
|[ControlCTrap (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Notifica al debugger che CTRL + C viene intercettato nel processo sottoposto a debug.|  
|[CreateAppDomain (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Notifica al debugger che è stato creato un dominio applicazione.|  
|[CreateProcess (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Notifica al debugger quando un processo è stato associato o avviato per la prima volta.|  
|[CreateThread (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Notifica al debugger che un thread ha avviato l'esecuzione di codice gestito.|  
|[DebuggerError (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento da CLR.|  
|[EditAndContinueRemap (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Deprecato. Notifica al debugger che è stato inviato un evento di modifica del mapping all'IDE.|  
|[EvalComplete (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Notifica al debugger che una versione di valutazione è stata completata.|  
|[EvalException (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Notifica al debugger che una versione di valutazione è stata terminata con un'eccezione non gestita.|  
|[Exception (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Notifica al debugger che è stata generata un'eccezione dal codice gestito.|  
|[ExitAppDomain (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Notifica al debugger che un dominio applicazione è stato terminato.|  
|[ExitProcess (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Notifica al debugger che un processo è terminato.|  
|[ExitThread (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Notifica al debugger che un thread che era in esecuzione il codice gestito è stato terminato.|  
|[LoadAssembly (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Notifica al debugger che un assembly CLR è stato caricato correttamente.|  
|[LoadClass (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Notifica al debugger che è stata caricata una classe.|  
|[LoadModule (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Notifica al debugger che un modulo CLR è stato caricato correttamente.|  
|[LogMessage (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Notifica al debugger che un thread gestito CLR ha chiamato un metodo <xref:System.Diagnostics.EventLog> classe per registrare un evento.|  
|[LogSwitch (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Notifica al debugger che un thread gestito CLR ha chiamato un metodo <xref:System.Diagnostics.Switch> classe per creare, modificare o eliminare un'opzione di debug/traccia.|  
|[NameChange (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Notifica al debugger che il nome di un thread o un dominio applicazione è stato modificato.|  
|[StepComplete (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Notifica al debugger che un passaggio è stato completato.|  
|[UnloadAssembly (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Notifica al debugger che un assembly CLR è stato scaricato.|  
|[UnloadClass (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Notifica al debugger che è in corso lo scaricamento di una classe.|  
|[UnloadModule (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Notifica al debugger che un modulo CLR (DLL) è stato scaricato.|  
|[UpdateModuleSymbols (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Notifica al debugger che i simboli per un modulo CLR sono stati modificati.|  
  
## <a name="remarks"></a>Note  
 Tutte le richiamate vengono serializzate, chiamate nello stesso thread e con il processo nello stato sincronizzato.  
  
 Ogni implementazione di callback deve chiamare [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per riprendere l'esecuzione. Se `ICorDebugController::Continue` non viene chiamato prima del completamento del callback, il processo continuerà a rimanere arrestato e finché non si verificherà alcun callback di evento più `ICorDebugController::Continue` viene chiamato.  
  
 Un debugger deve implementare [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) se sta eseguendo il debug di applicazioni .NET Framework versione 2.0. Un'istanza di `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` viene passato come oggetto di callback da [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [ICorDebugManagedCallback2 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
