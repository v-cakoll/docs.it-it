---
title: Enumerazione COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cbc66ef1eb5048d2c708a615a99ea363d29540f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752168"
---
# <a name="corprfhighmonitor-enumeration"></a>Enumerazione COR_PRF_HIGH_MONITOR
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Flag oltre a quelle disponibili in offre il [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione che il profiler può specificare per il [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo durante il caricamento.  
  
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Nessun flag impostato.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|I controlli di [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback per l'aggiunta di riferimenti ad assembly durante il Walker di chiusura riferimenti ad assembly CLR.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|I controlli di [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback per gli aggiornamenti per il flusso di simboli associato a un modulo in memoria.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|I controlli di [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback per indicare quando un metodo dinamico è stato sottoposto a garbage collection e scaricata. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|.NET core 3.0 e versioni successive: Consente di disattivare [suddivisi in livelli compilazione](../../../core/whats-new/dotnet-core-3-0.md) per i profiler.|
|`COR_PRF_HIGH_BASIC_GC`|.NET core 3.0 e versioni successive: Fornisce un GC opzione di profilatura rispetto al tipo semplice [ `COR_PRF_MONITOR_GC` ](cor-prf-monitor-enumeration.md). Controlla solo il [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), e [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) i callback. A differenza di `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` non disabilitare la garbage collection simultanea.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|.NET core 3.0 e versioni successive: Abilita il [MovedReferences](icorprofilercallback-movedreferences-method.md) e [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) i callback per solo cataloghi globali con compattazione.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|.NET core 3.0 e versioni successive: Simile a [ `COR_PRF_MONITOR_OBJECT_ALLOCATED` ](cor-prf-monitor-enumeration.md), ma vengono fornite informazioni sulle allocazioni di oggetti per i grandi oggetti dell'Heap (LOH) solo.|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che richiedono le immagini ottimizzate per il profiler. Corrisponde alla `COR_PRF_REQUIRE_PROFILE_IMAGE` flag nel [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati solo durante l'inizializzazione. Se si prova a modificare uno di questi flag altrove, viene restituito un valore `HRESULT` che indica un errore.|  
  
## <a name="remarks"></a>Note  
 Il `COR_PRF_HIGH_MONITOR` flag vengono usati con il `pdwEventsHigh` parametro delle [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) e [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodi.  
  
A partire da .NET Framework 4.6.1, il valore della `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` modificato da 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002). A partire da .NET Framework 4.7.2, il valore modificato da `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` deve essere una maschera di bit che rappresenta tutti i flag che possono essere impostati solo durante l'inizializzazione. Tentativo di modificare uno di questi flag altrove, viene restituito un errore `HRESULT`.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [Enumerazione COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [Interfaccia ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
