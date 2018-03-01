---
title: Metodo ICorProfilerCallback5::ConditionalWeakTableElementReferences
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- CondiitonalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8cfe86ac7d0cd5b4a5c6adb9f12ffe9577b6e611
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a><span data-ttu-id="dca77-102">Metodo ICorProfilerCallback5::ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="dca77-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences Method</span></span>
<span data-ttu-id="dca77-103">Identifica la chiusura transitiva di oggetti a cui le radici fanno riferimento tramite i riferimenti di campo di membri diretti e tramite le dipendenze `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="dca77-103">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca77-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dca77-104">Syntax</span></span>  
  
```  
HRESULT ConditionalWeakTableElementReferences(     [in]                     ULONG    cRootRefs,     [in, size_is(cRootRefs)] ObjectID keyRefIds[],     [in, size_is(cRootRefs)] ObjectID valueRefIds[],     [in, size_is(cRootRefs)] GCHandleID rootIds[]);};  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dca77-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dca77-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="dca77-106">[in] Numero di elementi nelle matrici `keyRefIds`, `valueRefIds` e `rootIds`.</span><span class="sxs-lookup"><span data-stu-id="dca77-106">[in] The number of elements in the `keyRefIds`, `valueRefIds`, and `rootIds` arrays.</span></span>  
  
 `keyRefIds`  
 <span data-ttu-id="dca77-107">[in] Matrice di ID oggetto, ognuno dei quali include il valore `ObjectID` per l'elemento primario nella coppia di handle dipendente.</span><span class="sxs-lookup"><span data-stu-id="dca77-107">[in] An array of object IDs, each of which contains the `ObjectID` for the primary element in the dependent handle pair.</span></span>  
  
 `valueRefIds`  
 <span data-ttu-id="dca77-108">[in] Matrice di ID oggetto, ognuno dei quali include il valore `ObjectID` per l'elemento secondario nella coppia di handle dipendente.</span><span class="sxs-lookup"><span data-stu-id="dca77-108">[in] An array of object IDs, each of which contains the `ObjectID` for the secondary element in the dependent handle pair.</span></span> <span data-ttu-id="dca77-109">(`keyRefIds[i]` mantiene `valueRefIds[i]` alive.)</span><span class="sxs-lookup"><span data-stu-id="dca77-109">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span></span>  
  
 `rootIds`  
 <span data-ttu-id="dca77-110">[in] Matrice di valori `GCHandleID` che fanno riferimento a un valore Integer contenente informazioni aggiuntive sulla radice di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="dca77-110">[in] An array of `GCHandleID` values that point to an integer that contains additional information about the garbage collection root.</span></span>  
  
 <span data-ttu-id="dca77-111">Nessuno dei valori `ObjectID` restituito dal metodo `ConditionalWeakTableElementReferences` è valido durante il callback stesso, poiché è possibile che il Garbage Collector stia spostando oggetti da posizioni precedenti a nuove posizioni.</span><span class="sxs-lookup"><span data-stu-id="dca77-111">None of the `ObjectID` values returned by the `ConditionalWeakTableElementReferences` method are valid during the callback itself, because the garbage collector may be in the process of moving objects from old to new locations.</span></span> <span data-ttu-id="dca77-112">I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `ConditionalWeakTableElementReferences`.</span><span class="sxs-lookup"><span data-stu-id="dca77-112">Therefore, profilers should not attempt to inspect objects during a `ConditionalWeakTableElementReferences` call.</span></span> <span data-ttu-id="dca77-113">In corrispondenza di `GarbageCollectionFinished`, tutti gli oggetti saranno stati spostati nelle nuove posizioni e sarà possibile verificarli.</span><span class="sxs-lookup"><span data-stu-id="dca77-113">At `GarbageCollectionFinished`, all objects have been moved to their new locations, and inspection may be done.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dca77-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="dca77-114">Example</span></span>  
 <span data-ttu-id="dca77-115">Esempio di codice seguente viene illustrato come implementare [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) e utilizzare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="dca77-115">The following code example demonstrates how to implement [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) and use this method.</span></span>  
  
```  
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(  
    ULONG      cRootRefs,  
    ObjectID   keyRefIds[],  
    ObjectID   valueRefIds[],  
    GCHandleID rootIds[])  
{  
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");  
    for (unsigned int i = 0; i < cRootRefs; ++i)  
    {  
        // Save dependency to XML for later retrieval  
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or store dependency to an internal map  
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);  
        // or add arc to object graph  
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);  
    }  
    return S_OK;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="dca77-116">Note</span><span class="sxs-lookup"><span data-stu-id="dca77-116">Remarks</span></span>  
 <span data-ttu-id="dca77-117">Un profiler per il [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] o versioni successive implementa il [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) interfaccia e registra le dipendenze specificate per il `ConditionalWeakTableElementReferences` metodo.</span><span class="sxs-lookup"><span data-stu-id="dca77-117">A profiler for the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] or later versions implements the [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span></span> <span data-ttu-id="dca77-118">`ICorProfilerCallback5`fornisce il set completo di dipendenze tra oggetti attivi rappresentati da `ConditionalWeakTable` voci.</span><span class="sxs-lookup"><span data-stu-id="dca77-118">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span></span> <span data-ttu-id="dca77-119">Queste dipendenze e il membro del campo di riferimenti specificati dal [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) metodo abilitare un profiler gestito generare il grafico completo degli oggetti attivi.</span><span class="sxs-lookup"><span data-stu-id="dca77-119">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca77-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dca77-120">Requirements</span></span>  
 <span data-ttu-id="dca77-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dca77-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca77-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dca77-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dca77-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca77-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca77-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dca77-124">See Also</span></span>  
 [<span data-ttu-id="dca77-125">Interfaccia ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="dca77-125">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)
