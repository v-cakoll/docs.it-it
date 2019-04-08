---
title: Enumerazione COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 572fcee528098a4f2929e07dfae63efc56e93dfd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081645"
---
# <a name="corprfhighmonitor-enumeration"></a><span data-ttu-id="d2e16-102">Enumerazione COR_PRF_HIGH_MONITOR</span><span class="sxs-lookup"><span data-stu-id="d2e16-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>
<span data-ttu-id="d2e16-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="d2e16-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d2e16-104">Flag oltre a quelle disponibili in offre il [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione che il profiler può specificare per il [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo durante il caricamento.</span><span class="sxs-lookup"><span data-stu-id="d2e16-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e16-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2e16-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,     
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,    
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="d2e16-106">Membri</span><span class="sxs-lookup"><span data-stu-id="d2e16-106">Members</span></span>  
  
|<span data-ttu-id="d2e16-107">Member</span><span class="sxs-lookup"><span data-stu-id="d2e16-107">Member</span></span>|<span data-ttu-id="d2e16-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2e16-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="d2e16-109">Nessun flag impostato.</span><span class="sxs-lookup"><span data-stu-id="d2e16-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="d2e16-110">I controlli di [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback per l'aggiunta di riferimenti ad assembly durante il Walker di chiusura riferimenti ad assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="d2e16-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="d2e16-111">I controlli di [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback per gli aggiornamenti per il flusso di simboli associato a un modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="d2e16-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="d2e16-112">I controlli di [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback per indicare quando un metodo dinamico è stato sottoposto a garbage collection e scaricata.</span><span class="sxs-lookup"><span data-stu-id="d2e16-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|   
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="d2e16-113">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che richiedono le immagini ottimizzate per il profiler.</span><span class="sxs-lookup"><span data-stu-id="d2e16-113">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="d2e16-114">Corrisponde alla `COR_PRF_REQUIRE_PROFILE_IMAGE` flag nel [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d2e16-114">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="d2e16-115">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati dopo la connessione del profiler a un'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d2e16-115">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="d2e16-116">Rappresenta tutti i flag `COR_PRF_HIGH_MONITOR` che possono essere impostati solo durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="d2e16-116">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="d2e16-117">Se si prova a modificare uno di questi flag altrove, viene restituito un valore `HRESULT` che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="d2e16-117">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2e16-118">Note</span><span class="sxs-lookup"><span data-stu-id="d2e16-118">Remarks</span></span>  
 <span data-ttu-id="d2e16-119">Il `COR_PRF_HIGH_MONITOR` flag vengono usati con il `pdwEventsHigh` parametro delle [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) e [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="d2e16-119">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="d2e16-120">Inizia con la [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], il valore della `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` modificato da 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="d2e16-120">Starting with the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="d2e16-121">A partire da .NET Framework 4.7.2, il valore modificato da `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span><span class="sxs-lookup"><span data-stu-id="d2e16-121">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` <span data-ttu-id="d2e16-122">deve essere una maschera di bit che rappresenta tutti i flag che possono essere impostati solo durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="d2e16-122">is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="d2e16-123">Tentativo di modificare uno di questi flag altrove, viene restituito un errore `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d2e16-123">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d2e16-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2e16-124">Requirements</span></span>  
 <span data-ttu-id="d2e16-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2e16-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2e16-126">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2e16-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2e16-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2e16-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d2e16-128">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d2e16-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2e16-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2e16-129">See also</span></span>

- [<span data-ttu-id="d2e16-130">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="d2e16-130">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [<span data-ttu-id="d2e16-131">Enumerazione COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="d2e16-131">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="d2e16-132">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="d2e16-132">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
