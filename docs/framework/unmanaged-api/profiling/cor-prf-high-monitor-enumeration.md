---
title: Enumerazione COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: fc0251624738a06d1be7081ebd099e97f7278a15
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283136"
---
# <a name="cor_prf_high_monitor-enumeration"></a>Enumerazione COR_PRF_HIGH_MONITOR

[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
Fornisce flag aggiuntivi rispetto a quelli disponibili nell'enumerazione [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) che il profiler può specificare nel metodo [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) durante il caricamento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,
    COR_PRF_HIGH_DISABLE_TIERED_COMPILATION       = 0x00000008,
    COR_PRF_HIGH_BASIC_GC                         = 0x00000010,
    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS         = 0x00000020,
    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED    = 0x00000040,
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS |
                                                    COR_PRF_HIGH_BASIC_GC |
                                                    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS |
                                                    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = COR_PRF_HIGH_DISABLE_TIERED_COMPILATION  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|description|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Nessun flag impostato.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Controlla il callback di [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) per l'aggiunta di riferimenti ad assembly durante il walker di chiusura dei riferimenti ad assembly CLR.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Controlla il callback [ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) per gli aggiornamenti al flusso di simboli associato a un modulo in memoria.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Controlla il callback [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) per indicare quando un metodo dinamico è stato sottoposto a Garbage Collection e scaricato. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|Solo .NET Core 3,0 e versioni successive: Disabilita la [compilazione a livelli](../../../core/whats-new/dotnet-core-3-0.md) per i profiler.|
|`COR_PRF_HIGH_BASIC_GC`|Solo .NET Core 3,0 e versioni successive: fornisce un'opzione di profilatura GC semplice rispetto a [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md). Controlla solo i callback [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)e [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) . A differenza del flag di `COR_PRF_MONITOR_GC`, `COR_PRF_HIGH_BASIC_GC` non Disabilita Garbage Collection simultanee.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|Solo .NET Core 3,0 e versioni successive: Abilita i callback [MovedReferences](icorprofilercallback-movedreferences-method.md) e [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) solo per la compattazione di cataloghi globali.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|Solo .NET Core 3,0 e versioni successive: simile a [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), ma fornisce informazioni sulle allocazioni di oggetti solo per l'heap degli oggetti grandi (LOH).|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che richiedono le immagini ottimizzate per il profiler. Corrisponde al flag `COR_PRF_REQUIRE_PROFILE_IMAGE` nell'enumerazione [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md).|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati solo durante l'inizializzazione. Se si prova a modificare uno di questi flag altrove, viene restituito un valore `HRESULT` che indica un errore.|  
  
## <a name="remarks"></a>Osservazioni

I flag `COR_PRF_HIGH_MONITOR` sono usati con il parametro `pdwEventsHigh` dei metodi [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) e [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md).  
  
A partire da .NET Framework 4.6.1, il valore della `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` è stato modificato da 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002). A partire da .NET Framework 4.7.2, il relativo valore è stato modificato da `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` deve essere una maschera di maschera che rappresenta tutti i flag che possono essere impostati solo durante l'inizializzazione. Il tentativo di modificare uno di questi flag altrove comporta un `HRESULT`non riuscito.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
**Intestazione:** CorProf.idl, CorProf.h  
  
**Libreria:** CorGuids.lib  
  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [Enumerazione COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [Interfaccia ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
