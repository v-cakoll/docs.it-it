---
title: Enumerazione COR_PRF_MONITOR
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbb39eb768069a737f3f89c771bf02fd6bc0c3b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102401"
---
# <a name="corprfmonitor-enumeration"></a>Enumerazione COR_PRF_MONITOR
Contiene i valori usati per specificare il comportamento, le funzionalità o gli eventi ai quali il profiler intende effettuare la sottoscrizione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a>Membri  
 Le sezioni seguenti `COR_PRF_MONITOR` membri dell'enumerazione in base alla categoria. Le categorie sono:  
  
-   [Nessun set di flag](#None)  
  
-   [Flag di callback](#Callback)  
  
-   [Flag di abilitazione delle funzionalità](#Feature)  
  
-   [Flag di configurazione](#Config)  
  
-   [Flag composti](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a>Nessun set di flag  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|Nessun flag impostato.|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a>Flag di callback  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Abilita tutti gli eventi di callback.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|I controlli di `AppDomainCreation*` e `AppDomainShutdown*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|I controlli di `AssemblyLoad*` e `AssemblyUnload*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|I controlli di `JITCachedFunctionSearch*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.<br /><br /> Il comportamento di questo flag è stato modificato in .NET Framework versione 2.0.|  
|`COR_PRF_MONITOR_CCW`|I controlli di `COMClassicVTable*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_CLASS_LOADS`|I controlli di `ClassLoad*` e `ClassUnload*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|I controlli di `ExceptionCLRCatcher*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|I controlli di [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) e [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia|  
|`COR_PRF_MONITOR_ENTERLEAVE`|I controlli di `FunctionEnter*`, `FunctionLeave*`, e `FunctionTailCall*` [funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md).|  
|`COR_PRF_MONITOR_EXCEPTIONS`|I controlli di [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) callback e il `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, e `ExceptionCatcher*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Controlli la [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) richiamata la [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_GC`|I controlli di [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md), [ SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md), [ RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md), e [FinalizeableObjectQueued ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) callback nel `ICorProfilerCallback*` interfacce.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|I controlli di `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md), e [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_MODULE_LOADS`|I controlli di `ModuleLoad*`, `ModuleUnload*`, e [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Controlli la [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) richiamata la [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_REMOTING`|I controlli di `Remoting*` callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Controlla se i callback di `Remoting*` monitoreranno gli eventi asincroni.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Controlla se un cookie viene passato ai callback di `Remoting*`.|  
|`COR_PRF_MONITOR_SUSPENDS`|I controlli di `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md), e [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaccia.|  
|`COR_PRF_MONITOR_THREADS`|I controlli di [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md), e [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) callback nel [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) e [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfacce.|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a>Flag di abilitazione delle funzionalità  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Abilita il recupero di un valore esatto `ClassID` per una funzione generica chiamando il [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) metodo con un `COR_PRF_FRAME_INFO` valore restituito dal [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Abilita traccia degli argomenti mediante il [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback o il [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) callback e il [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) (metodo).|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Abilita la tracciatura di valori restituiti mediante il [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback o il [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) callback e [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) (metodo).|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|Deprecato.<br /><br /> Il debug in-process non è supportato. Questo flag non ha alcun effetto.|  
|`COR_PRF_ENABLE_JIT_MAPS`|Deprecato.<br /><br /> Consente al profiler di ottenere mappe di linguaggio intermedio al codice nativo tramite [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md). A partire da .NET Framework versione 2.0, il runtime tiene sempre traccia dei mapping da codice IL a codice nativo, pertanto questo flag sarà considerato sempre impostato.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Indica al runtime di notificare al profiler le allocazioni degli oggetti. Questo flag deve essere impostato durante l'inizializzazione. Consente al profiler di usare successivamente il `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag per ricevere [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) i callback.|  
|`COR_PRF_ENABLE_REJIT`|Abilita le chiamate per il [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) e [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) metodi. Il profiler deve impostare questo flag all'avvio.  Se il profiler specifica questo flag, deve specificare anche `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Abilita le chiamate per il [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) (metodo).|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a>Flag di configurazione  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Impedisce il caricamento di tutte le immagini native, comprese le immagini ottimizzate per il profiler.  Se vengono specificati sia questo flag che il flag `COR_PRF_USE_PROFILE_IMAGES`, verrà usato il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_DISABLE_INLINING`|Disabilita tutte le funzionalità inline.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Disabilita tutte le ottimizzazioni del codice.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Disabilita i controlli per la trasparenza della sicurezza eseguiti generalmente durante la compilazione JIT e il caricamento delle classi per gli assembly con attendibilità totale. Ciò può rendere alcune strumentazioni più facili da eseguire.|  
|`COR_PRF_USE_PROFILE_IMAGES`|Fa sì che la ricerca delle immagini native venga avviata per le immagini ottimizzate per il profiler. Se non viene trovata alcuna immagine ottimizzata per il profiler relativa a un assembly specifico, Common Language Runtime esegue il fallback a JIT per tale assembly. Se vengono specificati sia questo flag che il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`, verrà usato il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a>Flag composti  
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_ALL`|Rappresenta tutti i valori del flag `COR_PRF_MONITOR`.|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|Rappresenta tutti i flag `COR_PRF_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione. La sezione sintassi indica i singoli flag presenti in questa maschera di bit.|  
|`COR_PRF_MONITOR_ALL`|Abilita tutti gli eventi di callback.|  
|`COR_PRF_MONITOR_IMMUTABLE`|Rappresenta tutti i flag `COR_PRF_MONITOR` che possono essere impostati solo durante l'inizializzazione. Se si prova a modificare uno di questi flag dopo l'inizializzazione, viene restituito un valore `HRESULT` che indica un errore.|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|Rappresenta tutti i flag `COR_PRF_MONITOR` che richiedono le immagini ottimizzate per il profiler.|  
  
## <a name="remarks"></a>Note  
 Oggetto `COR_PRF_MONITOR` valore viene usato con il [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodi per definire le notifiche degli eventi che common language runtime effettua a il profiler.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [Metodo GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)
- [Metodo SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)
