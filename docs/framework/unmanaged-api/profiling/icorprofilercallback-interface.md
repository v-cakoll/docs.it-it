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
ms.openlocfilehash: 6a53b9b1b061c2ca07a469abc78c07ed9e710069
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500091"
---
# <a name="icorprofilercallback-interface"></a>Interfaccia ICorProfilerCallback
Fornisce i metodi utilizzati dal Common Language Runtime (CLR) per notificare a un Code Profiler quando si verificano gli eventi sottoscritti dal profiler.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al profiler che è stato creato un dominio dell'applicazione.|  
|[Metodo AppDomainCreationStarted](icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al profiler che è in corso la creazione di un dominio applicazione.|  
|[Metodo AppDomainShutdownFinished](icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al profiler che un dominio applicazione è stato scaricato da un processo.|  
|[Metodo AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al profiler che un dominio applicazione viene scaricato da un processo.|  
|[Metodo AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md)|Notifica al profiler che è stato completato il caricamento di un assembly.|  
|[Metodo AssemblyLoadStarted](icorprofilercallback-assemblyloadstarted-method.md)|Notifica al profiler che è in corso il caricamento di un assembly.|  
|[Metodo AssemblyUnloadFinished](icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al profiler che un assembly è stato scaricato.|  
|[Metodo AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al profiler che è in corso lo scaricamento di un assembly.|  
|[Metodo ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)|Notifica al profiler che una classe ha terminato il caricamento.|  
|[Metodo ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)|Notifica al profiler che è in corso il caricamento di una classe.|  
|[Metodo ClassUnloadFinished](icorprofilercallback-classunloadfinished-method.md)|Notifica al profiler che una classe ha completato lo scaricamento.|  
|[Metodo ClassUnloadStarted](icorprofilercallback-classunloadstarted-method.md)|Notifica al profiler che una classe viene scaricata.|  
|[Metodo COMClassicVTableCreated](icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al profiler che è stato creato un Runtime Callable Wrapper (RCW) per l'IID e la classe specificati.|  
|[Metodo COMClassicVTableDestroyed](icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al profiler che un RCW viene eliminato definitivamente.|  
|[Metodo ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al profiler che il controllo viene passato al `catch` blocco appropriato.|  
|[Metodo ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al profiler che il controllo viene passato all'esterno del `catch` blocco appropriato.|  
|[Metodo ExceptionCLRCatcherExecute](icorprofilercallback-exceptionclrcatcherexecute-method.md)|Obsoleto nella versione .NET Framework 2,0.|  
|[Metodo ExceptionCLRCatcherFound](icorprofilercallback-exceptionclrcatcherfound-method.md)|Obsoleto nella .NET Framework 2,0.|  
|[Metodo ExceptionOSHandlerEnter](icorprofilercallback-exceptionoshandlerenter-method.md)|Non implementato. Un profiler che necessita di informazioni sulle eccezioni non gestite deve ottenere tali informazioni tramite altri mezzi.|  
|[Metodo ExceptionOSHandlerLeave](icorprofilercallback-exceptionoshandlerleave-method.md)|Non implementato. Un profiler che necessita di informazioni sulle eccezioni non gestite deve ottenere tali informazioni tramite altri mezzi.|  
|[Metodo ExceptionSearchCatcherFound](icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al profiler che la fase di ricerca della gestione delle eccezioni ha individuato un gestore per l'eccezione generata.|  
|[Metodo ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al profiler che è in corso l'esecuzione di un filtro utente.|  
|[Metodo ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al profiler che un filtro utente ha appena terminato l'esecuzione.|  
|[Metodo ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al profiler che la fase di ricerca della gestione delle eccezioni è stata immessa in una funzione.|  
|[Metodo ExceptionSearchFunctionLeave](icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al profiler che la fase di ricerca della gestione delle eccezioni ha terminato la ricerca di una funzione.|  
|[Metodo ExceptionThrown](icorprofilercallback-exceptionthrown-method.md)|Notifica al profiler che è stata generata un'eccezione.|  
|[Metodo ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni sta immettendo una `finally` clausola contenuta nella funzione specificata.|  
|[Metodo ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha lasciato una `finally` clausola.|  
|[Metodo ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni è stata immessa in una funzione.|  
|[Metodo ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha terminato la rimozione di una funzione.|  
|[Metodo FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md)|Notifica al profiler che il runtime ha iniziato a scaricare una funzione.|  
|[Metodo Initialize](icorprofilercallback-initialize-method.md)|Chiamata eseguita per inizializzare il profiler ogni volta che viene avviata una nuova applicazione CLR.|  
|[Metodo JITCachedFunctionSearchFinished](icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al profiler che una ricerca è stata completata per una funzione compilata in precedenza utilizzando NGen. exe.|  
|[Metodo JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al profiler che è stata avviata una ricerca per una funzione compilata in precedenza utilizzando NGen. exe.|  
|[Metodo JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)|Notifica al profiler che il compilatore JIT ha terminato la compilazione di una funzione.|  
|[Metodo JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)|Notifica al profiler che il compilatore just-in-time (JIT) ha iniziato a compilare una funzione.|  
|[Metodo JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)|Notifica al profiler che una funzione che è stata compilata tramite JIT è stata rimossa dalla memoria.|  
|[Metodo JITInlining](icorprofilercallback-jitinlining-method.md)|Notifica al profiler che il compilatore JIT sta per inserire una funzione in linea con un'altra funzione.|  
|[Metodo ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al profiler che è stata eseguita una transizione dal codice gestito al codice non gestito.|  
|[Metodo ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al profiler che un modulo viene collegato al relativo assembly padre.|  
|[Metodo ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)|Notifica al profiler che un modulo ha terminato il caricamento.|  
|[Metodo ModuleLoadStarted](icorprofilercallback-moduleloadstarted-method.md)|Notifica al profiler che un modulo è in fase di caricamento.|  
|[Metodo ModuleUnloadFinished](icorprofilercallback-moduleunloadfinished-method.md)|Notifica al profiler che è stato completato lo scaricamento di un modulo.|  
|[Metodo ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md)|Notifica al profiler che un modulo è stato scaricato.|  
|[Metodo MovedReferences](icorprofilercallback-movedreferences-method.md)|Notifica al profiler i riferimenti agli oggetti spostati durante Garbage Collection.|  
|[Metodo ObjectAllocated](icorprofilercallback-objectallocated-method.md)|Notifica al profiler che la memoria all'interno dell'heap è stata allocata per un oggetto.|  
|[Metodo ObjectReferences](icorprofilercallback-objectreferences-method.md)|Notifica al profiler gli oggetti in memoria a cui fa riferimento l'oggetto specificato.|  
|[Metodo ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al profiler il numero di istanze di ogni classe specificata create dopo la Garbage Collection precedente.|  
|[Metodo RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al profiler che una chiamata remota è stata eseguita fino al completamento nel client.|  
|[Metodo RemotingClientInvocationStarted](icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al profiler che è stata avviata una chiamata remota.|  
|[Metodo RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al profiler che la parte lato server di una chiamata remota è stata completata e che il client sta ricevendo e sta per elaborare la risposta.|  
|[Metodo RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al profiler che il client sta inviando una richiesta al server.|  
|[Metodo RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al profiler che il processo ha completato la chiamata a un metodo in risposta a una richiesta di chiamata al metodo remoto.|  
|[Metodo RemotingServerInvocationStarted](icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al profiler che il processo sta richiamando un metodo in risposta a una richiesta di chiamata a un metodo remoto.|  
|[Metodo RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al profiler che il processo riceve una chiamata a un metodo remoto o una richiesta di attivazione.|  
|[Metodo RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)|Notifica al profiler che il processo ha terminato l'elaborazione di una richiesta di chiamata al metodo remoto e sta per trasmettere la risposta tramite un canale.|  
|[Metodo RootReferences](icorprofilercallback-rootreferences-method.md)|Notifica al profiler informazioni sui riferimenti radice dopo Garbage Collection.|  
|[Metodo RuntimeResumeFinished](icorprofilercallback-runtimeresumefinished-method.md)|Notifica al profiler che il runtime ha ripreso tutti i thread di runtime e ha restituito un'operazione normale.|  
|[Metodo RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)|Notifica al profiler che il Runtime sta riprendendo tutti i thread della fase di esecuzione.|  
|[Metodo RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al profiler che il runtime ha interrotto la sospensione della fase di esecuzione in corso.|  
|[Metodo RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al profiler che il runtime ha completato la sospensione di tutti i thread della fase di esecuzione.|  
|[Metodo RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al profiler che il Runtime sta per sospendere tutti i thread della fase di esecuzione.|  
|[Metodo RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)|Notifica al profiler che il thread specificato è stato ripreso dopo essere stato sospeso.|  
|[Metodo RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al profiler che il thread specificato è stato o sta per essere sospeso.|  
|[Metodo Shutdown](icorprofilercallback-shutdown-method.md)|Notifica al profiler che l'applicazione è in fase di chiusura.|  
|[Metodo ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al profiler che un thread gestito viene implementato utilizzando un particolare thread del sistema operativo.|  
|[Metodo ThreadCreated](icorprofilercallback-threadcreated-method.md)|Notifica al profiler che è stato creato un thread.|  
|[Metodo ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md)|Notifica al profiler che un thread è stato eliminato definitivamente.|  
|[Metodo UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al profiler che è stata eseguita una transizione dal codice non gestito al codice gestito.|  
  
## <a name="remarks"></a>Osservazioni  
 CLR chiama un metodo nell' `ICorProfilerCallback` interfaccia (o [ICorProfilerCallback2](icorprofilercallback2-interface.md)) per notificare al profiler quando si verifica un evento in cui è stato sottoscritto il profiler. Si tratta dell'interfaccia di callback primaria tramite la quale CLR comunica con il Code Profiler.  
  
 Un Code Profiler deve implementare i metodi dell' `ICorProfilerCallback` interfaccia. Per il .NET Framework versione 2,0 o successiva, il profiler deve implementare anche i `ICorProfilerCallback2` metodi. Ogni implementazione del metodo deve restituire un valore HRESULT che ha un valore di S_OK in caso di esito positivo o E_FAIL in caso di errore. Attualmente CLR ignora il valore HRESULT restituito da ogni callback eccetto [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
 Nel registro di sistema di Microsoft Windows, un Code Profiler deve registrare l'oggetto Component Object Model (COM) che implementa le `ICorProfilerCallback` `ICorProfilerCallback2` interfacce e. Un Code Profiler sottoscrive gli eventi per i quali vuole ricevere una notifica chiamando [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Questa operazione viene in genere eseguita nell'implementazione del profiler di [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md). Il profiler può quindi ricevere una notifica dal runtime quando un evento sta per verificarsi o si è appena verificato in un processo di runtime in esecuzione.  
  
> [!NOTE]
> Il profiler registra un singolo oggetto COM. Se il profiler è destinato alla .NET Framework versione 1,0 o 1,1, tale oggetto COM deve implementare solo i metodi di `ICorProfilerCallback` . Se la destinazione è .NET Framework versione 2,0 o successiva, l'oggetto COM deve implementare anche i metodi di `ICorProfilerCallback2` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Interfaccia ICorProfilerCallback3](icorprofilercallback3-interface.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
