---
title: Interfaccia ICorProfilerCallback
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback
helpviewer_keywords:
- ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3119818934df765a8bbd9c05caaee04f9476069f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963528"
---
# <a name="icorprofilercallback-interface"></a>Interfaccia ICorProfilerCallback
Fornisce i metodi utilizzati dal Common Language Runtime (CLR) per notificare a un Code Profiler quando si verificano gli eventi sottoscritti dal profiler.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|[Metodo AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al profiler che è stato creato un dominio dell'applicazione.|  
|[Metodo AppDomainCreationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al profiler che è in corso la creazione di un dominio applicazione.|  
|[Metodo AppDomainShutdownFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al profiler che un dominio applicazione è stato scaricato da un processo.|  
|[Metodo AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al profiler che un dominio applicazione viene scaricato da un processo.|  
|[Metodo AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Notifica al profiler che è stato completato il caricamento di un assembly.|  
|[Metodo AssemblyLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Notifica al profiler che è in corso il caricamento di un assembly.|  
|[Metodo AssemblyUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al profiler che un assembly è stato scaricato.|  
|[Metodo AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al profiler che è in corso lo scaricamento di un assembly.|  
|[Metodo ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Notifica al profiler che una classe ha terminato il caricamento.|  
|[Metodo ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Notifica al profiler che è in corso il caricamento di una classe.|  
|[Metodo ClassUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Notifica al profiler che una classe ha completato lo scaricamento.|  
|[Metodo ClassUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Notifica al profiler che una classe viene scaricata.|  
|[Metodo COMClassicVTableCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al profiler che è stato creato un Runtime Callable Wrapper (RCW) per l'IID e la classe specificati.|  
|[Metodo COMClassicVTableDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al profiler che un RCW viene eliminato definitivamente.|  
|[Metodo ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al profiler che il controllo viene passato al blocco `catch` appropriato.|  
|[Metodo ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al profiler che il controllo viene passato all'esterno del `catch` blocco appropriato.|  
|[Metodo ExceptionCLRCatcherExecute](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Obsoleto nella versione .NET Framework 2,0.|  
|[Metodo ExceptionCLRCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Obsoleto nella .NET Framework 2,0.|  
|[Metodo ExceptionOSHandlerEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Non implementato. Un profiler che necessita di informazioni sulle eccezioni non gestite deve ottenere tali informazioni tramite altri mezzi.|  
|[Metodo ExceptionOSHandlerLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Non implementato. Un profiler che necessita di informazioni sulle eccezioni non gestite deve ottenere tali informazioni tramite altri mezzi.|  
|[Metodo ExceptionSearchCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al profiler che la fase di ricerca della gestione delle eccezioni ha individuato un gestore per l'eccezione generata.|  
|[Metodo ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al profiler che è in corso l'esecuzione di un filtro utente.|  
|[Metodo ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al profiler che un filtro utente ha appena terminato l'esecuzione.|  
|[Metodo ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al profiler che la fase di ricerca della gestione delle eccezioni è stata immessa in una funzione.|  
|[Metodo ExceptionSearchFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al profiler che la fase di ricerca della gestione delle eccezioni ha terminato la ricerca di una funzione.|  
|[Metodo ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Notifica al profiler che è stata generata un'eccezione.|  
|[Metodo ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni sta `finally` immettendo una clausola contenuta nella funzione specificata.|  
|[Metodo ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha `finally` lasciato una clausola.|  
|[Metodo ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni è stata immessa in una funzione.|  
|[Metodo ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha terminato la rimozione di una funzione.|  
|[Metodo FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Notifica al profiler che il runtime ha iniziato a scaricare una funzione.|  
|[Metodo Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Chiamata eseguita per inizializzare il profiler ogni volta che viene avviata una nuova applicazione CLR.|  
|[Metodo JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al profiler che una ricerca è stata completata per una funzione compilata in precedenza utilizzando NGen. exe.|  
|[Metodo JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al profiler che è stata avviata una ricerca per una funzione compilata in precedenza utilizzando NGen. exe.|  
|[Metodo JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Notifica al profiler che il compilatore JIT ha terminato la compilazione di una funzione.|  
|[Metodo JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Notifica al profiler che il compilatore just-in-time (JIT) ha iniziato a compilare una funzione.|  
|[Metodo JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Notifica al profiler che una funzione che è stata compilata tramite JIT è stata rimossa dalla memoria.|  
|[Metodo JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Notifica al profiler che il compilatore JIT sta per inserire una funzione in linea con un'altra funzione.|  
|[Metodo ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al profiler che è stata eseguita una transizione dal codice gestito al codice non gestito.|  
|[Metodo ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al profiler che un modulo viene collegato al relativo assembly padre.|  
|[Metodo ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Notifica al profiler che un modulo ha terminato il caricamento.|  
|[Metodo ModuleLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Notifica al profiler che un modulo è in fase di caricamento.|  
|[Metodo ModuleUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Notifica al profiler che è stato completato lo scaricamento di un modulo.|  
|[Metodo ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Notifica al profiler che un modulo è stato scaricato.|  
|[Metodo MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Notifica al profiler i riferimenti agli oggetti spostati durante Garbage Collection.|  
|[Metodo ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Notifica al profiler che la memoria all'interno dell'heap è stata allocata per un oggetto.|  
|[Metodo ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Notifica al profiler gli oggetti in memoria a cui fa riferimento l'oggetto specificato.|  
|[Metodo ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al profiler il numero di istanze di ogni classe specificata create dopo la Garbage Collection precedente.|  
|[Metodo RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al profiler che una chiamata remota è stata eseguita fino al completamento nel client.|  
|[Metodo RemotingClientInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al profiler che è stata avviata una chiamata remota.|  
|[Metodo RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al profiler che la parte lato server di una chiamata remota è stata completata e che il client sta ricevendo e sta per elaborare la risposta.|  
|[Metodo RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al profiler che il client sta inviando una richiesta al server.|  
|[Metodo RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al profiler che il processo ha completato la chiamata a un metodo in risposta a una richiesta di chiamata al metodo remoto.|  
|[Metodo RemotingServerInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al profiler che il processo sta richiamando un metodo in risposta a una richiesta di chiamata a un metodo remoto.|  
|[Metodo RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al profiler che il processo riceve una chiamata a un metodo remoto o una richiesta di attivazione.|  
|[Metodo RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata al metodo remoto e sta per trasmettere la risposta tramite un canale.|  
|[Metodo RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Notifica al profiler informazioni sui riferimenti radice dopo Garbage Collection.|  
|[Metodo RuntimeResumeFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Notifica al profiler che il runtime ha ripreso tutti i thread di runtime e ha restituito un'operazione normale.|  
|[Metodo RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Notifica al profiler che il Runtime sta riprendendo tutti i thread della fase di esecuzione.|  
|[Metodo RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al profiler che il runtime ha interrotto la sospensione della fase di esecuzione in corso.|  
|[Metodo RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al profiler che il runtime ha completato la sospensione di tutti i thread della fase di esecuzione.|  
|[Metodo RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al profiler che il Runtime sta per sospendere tutti i thread della fase di esecuzione.|  
|[Metodo RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Notifica al profiler che il thread specificato è stato ripreso dopo essere stato sospeso.|  
|[Metodo RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al profiler che il thread specificato è stato o sta per essere sospeso.|  
|[Metodo Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Notifica al profiler che l'applicazione è in fase di chiusura.|  
|[Metodo ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al profiler che un thread gestito viene implementato utilizzando un particolare thread del sistema operativo.|  
|[Metodo ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Notifica al profiler che è stato creato un thread.|  
|[Metodo ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Notifica al profiler che un thread è stato eliminato definitivamente.|  
|[Metodo UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al profiler che è stata eseguita una transizione dal codice non gestito al codice gestito.|  
  
## <a name="remarks"></a>Note  
 CLR chiama un metodo nell' `ICorProfilerCallback` interfaccia (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) per notificare al profiler quando si verifica un evento in cui è stato sottoscritto il profiler. Si tratta dell'interfaccia di callback primaria tramite la quale CLR comunica con il Code Profiler.  
  
 Un code profiler deve implementare i metodi dell' `ICorProfilerCallback` interfaccia. Per il .NET Framework versione 2,0 o successiva, il profiler deve implementare `ICorProfilerCallback2` anche i metodi. Ogni implementazione del metodo deve restituire un valore HRESULT con valore S_OK in caso di esito positivo o E_FAIL in caso di errore. Attualmente CLR ignora il valore HRESULT restituito da ogni callback eccetto [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Nel registro di sistema di Microsoft Windows, un code profiler deve registrare l'oggetto Component Object Model (com) che `ICorProfilerCallback` implementa `ICorProfilerCallback2` le interfacce e. Un Code Profiler sottoscrive gli eventi per i quali vuole ricevere una notifica chiamando [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Questa operazione viene in genere eseguita nell'implementazione del profiler di [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Il profiler può quindi ricevere una notifica dal runtime quando un evento sta per verificarsi o si è appena verificato in un processo di runtime in esecuzione.  
  
> [!NOTE]
> Il profiler registra un singolo oggetto COM. Se il profiler è destinato alla .NET Framework versione 1,0 o 1,1, tale oggetto COM deve implementare solo i metodi di `ICorProfilerCallback`. Se la destinazione è .NET Framework versione 2,0 o successiva, l'oggetto COM deve implementare anche i metodi di `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl, CorProf. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Interfaccia ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [Interfaccia ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
