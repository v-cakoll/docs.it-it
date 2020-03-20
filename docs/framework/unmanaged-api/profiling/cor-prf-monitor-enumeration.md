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
ms.openlocfilehash: b6c3dc78b9c503747c7a2d404706eb797790b931
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175200"
---
# <a name="cor_prf_monitor-enumeration"></a>Enumerazione COR_PRF_MONITOR
Contiene i valori usati per specificare il comportamento, le funzionalità o gli eventi ai quali il profiler intende effettuare la sottoscrizione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="members"></a>Members  
 Nelle sezioni `COR_PRF_MONITOR` seguenti sono elencati i membri di enumerazione per categoria. Le categorie sono:  
  
- [Nessun flag impostato](#None)  
  
- [Flag di callback](#Callback)  
  
- [Flag di abilitazione delle funzionalità](#Feature)  
  
- [Flag di configurazione](#Config)  
  
- [Flag composti](#Composite)  
  
<a name="None"></a>
### <a name="no-flags-set"></a>Nessun flag impostato  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|Nessun flag impostato.|  
  
<a name="Callback"></a>
### <a name="callback-flags"></a>Flag di callback  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Abilita tutti gli eventi di callback.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|Controlla `AppDomainCreation*` i `AppDomainShutdown*` callback e nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|Controlla `AssemblyLoad*` i `AssemblyUnload*` callback e nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|Controlla `JITCachedFunctionSearch*` i callback nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)<br /><br /> Il comportamento di questo flag è stato modificato in .NET Framework versione 2.0.|  
|`COR_PRF_MONITOR_CCW`|Controlla `COMClassicVTable*` i callback nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CLASS_LOADS`|Controlla `ClassLoad*` i `ClassUnload*` callback e nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|Controlla `ExceptionCLRCatcher*` i callback nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|Controlla i callback [UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) e [ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_ENTERLEAVE`|Controlla `FunctionEnter*`le `FunctionLeave*`funzioni `FunctionTailCall*`statiche globali , e [profilano](profiling-global-static-functions.md).|  
|`COR_PRF_MONITOR_EXCEPTIONS`|Controlla il callback [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) e i `ExceptionSearch*`callback `ExceptionOSHandler*`, , `ExceptionUnwind*`e `ExceptionCatcher*` nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Controlla il callback [FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_GC`|Controlla i callback [di GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md), [RootReferences](icorprofilercallback-rootreferences-method.md), [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)e [FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) nelle interfacce. `ICorProfilerCallback*` Quando `COR_PRF_MONITOR_GC` viene allocato, l'operazione di Garbage Collection simultanea viene disattivata.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|Controlla `JITCompilation*`i callback , [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)e [JITInlining](icorprofilercallback-jitinlining-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .|  
|`COR_PRF_MONITOR_MODULE_LOADS`|Controlla `ModuleLoad*`i `ModuleUnload*`callback di , e [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Controlla il callback [ObjectAllocated](icorprofilercallback-objectallocated-method.md) nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_REMOTING`|Controlla `Remoting*` i callback nell'interfaccia [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Controlla se i callback di `Remoting*` monitoreranno gli eventi asincroni.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Controlla se un cookie viene passato ai callback di `Remoting*`.|  
|`COR_PRF_MONITOR_SUSPENDS`|Controlla `RuntimeSuspend*`i `RuntimeResume*`callback , , [, RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)e [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) nell'interfaccia [ICorProfilerCallback](icorprofilercallback-interface.md) .|  
|`COR_PRF_MONITOR_THREADS`|Controlla i callback [ThreadCreated](icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)e [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) nelle interfacce [ICorProfilerCallback](icorprofilercallback-interface.md) e [ICorProfilerCallback2](icorprofilercallback2-interface.md) .|  
  
<a name="Feature"></a>
### <a name="feature-enabling-flags"></a>Flag di abilitazione delle funzionalità  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Abilita il recupero di `ClassID` un'esatta funzione per una funzione generica chiamando il [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) metodo con un `COR_PRF_FRAME_INFO` valore restituito dal [FunctionEnter2](functionenter2-function.md) callback.|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Abilita la traccia degli argomenti utilizzando il callback [FunctionEnter2](functionenter2-function.md) o [FunctionEnter3WithInfo](functionenter3withinfo-function.md) e il metodo [GetFunctionEnter3Info.](icorprofilerinfo3-getfunctionenter3info-method.md)|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Abilita la traccia dei valori restituiti utilizzando il callback [FunctionLeave2](functionleave2-function.md) o il callback [FunctionLeave3WithInfo](functionleave3withinfo-function.md) e il metodo [GetFunctionLeave3Info.](icorprofilerinfo3-getfunctionleave3info-method.md)|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|Operazione deprecata.<br /><br /> Il debug in-process non è supportato. Questo flag non ha alcun effetto.|  
|`COR_PRF_ENABLE_JIT_MAPS`|Operazione deprecata.<br /><br /> Consente al profiler di ottenere mappe da IL a nativo utilizzando [GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md). A partire da .NET Framework versione 2.0, il runtime tiene sempre traccia dei mapping da codice IL a codice nativo, pertanto questo flag sarà considerato sempre impostato.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Indica al runtime di notificare al profiler le allocazioni degli oggetti. Questo flag deve essere impostato durante l'inizializzazione. Consente al profiler di `COR_PRF_MONITOR_OBJECT_ALLOCATED` utilizzare successivamente il flag per ricevere i callback [ObjectAllocated.](icorprofilercallback-objectallocated-method.md)|  
|`COR_PRF_ENABLE_REJIT`|Abilita le chiamate ai metodi [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) e [RequestRevert.](icorprofilerinfo4-requestrevert-method.md) Il profiler deve impostare questo flag all'avvio.  Se il profiler specifica questo flag, deve specificare anche `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Abilita le chiamate al metodo [DoStackSnapshot.](icorprofilerinfo2-dostacksnapshot-method.md)|  
  
<a name="Config"></a>
### <a name="configuration-flags"></a>Flag di configurazione  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Impedisce il caricamento di tutte le immagini native, comprese le immagini ottimizzate per il profiler.  Se vengono specificati sia questo flag che il flag `COR_PRF_USE_PROFILE_IMAGES`, verrà usato il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_DISABLE_INLINING`|Disabilita tutte le funzionalità inline.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Disabilita tutte le ottimizzazioni del codice.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Disabilita i controlli per la trasparenza della sicurezza eseguiti generalmente durante la compilazione JIT e il caricamento delle classi per gli assembly con attendibilità totale. Ciò può rendere alcune strumentazioni più facili da eseguire.|  
|`COR_PRF_USE_PROFILE_IMAGES`|Fa sì che la ricerca delle immagini native venga avviata per le immagini ottimizzate per il profiler. Se non viene trovata alcuna immagine ottimizzata per il profiler relativa a un assembly specifico, Common Language Runtime esegue il fallback a JIT per tale assembly. Se vengono specificati sia questo flag che il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`, verrà usato il flag `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
  
<a name="Composite"></a>
### <a name="composite-flags"></a>Flag composti  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_ALL`|Rappresenta tutti i valori del flag `COR_PRF_MONITOR`.|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|Rappresenta tutti i flag `COR_PRF_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione. La sezione sintassi indica i singoli flag presenti in questa maschera di bit.|  
|`COR_PRF_MONITOR_ALL`|Abilita tutti gli eventi di callback.|  
|`COR_PRF_MONITOR_IMMUTABLE`|Rappresenta tutti i flag `COR_PRF_MONITOR` che possono essere impostati solo durante l'inizializzazione. Se si prova a modificare uno di questi flag dopo l'inizializzazione, viene restituito un valore `HRESULT` che indica un errore.|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|Rappresenta tutti i flag `COR_PRF_MONITOR` che richiedono le immagini ottimizzate per il profiler.|  
  
## <a name="remarks"></a>Osservazioni  
 Un `COR_PRF_MONITOR` valore viene utilizzato con i metodi [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) per definire le notifiche degli eventi che Common Language Runtime apporta al profiler.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](profiling-enumerations.md)
- [Metodo GetEventMask](icorprofilerinfo-geteventmask-method.md)
- [Metodo SetEventMask](icorprofilerinfo-seteventmask-method.md)
