---
title: Interfaccia ICorProfilerCallback5
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: ce34d43091cdee0bca88f94711e49072fa4fd08c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430073"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="bbdd3-102">Interfaccia ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="bbdd3-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="bbdd3-103">Integra le informazioni per consentire a un profiler di identificare la chiusura completa di oggetti attivi, se usato con il metodo [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) insieme ai metodi [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) e [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bbdd3-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="bbdd3-104">`ICorProfilerCallback5` deve essere implementato da un profiler di managed memory per sottoscrivere le notifiche relative agli handle dipendenti.</span><span class="sxs-lookup"><span data-stu-id="bbdd3-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbdd3-105">Note</span><span class="sxs-lookup"><span data-stu-id="bbdd3-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bbdd3-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="bbdd3-106">Methods</span></span>  
  
|<span data-ttu-id="bbdd3-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="bbdd3-107">Method</span></span>|<span data-ttu-id="bbdd3-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbdd3-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bbdd3-109">Metodo ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="bbdd3-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="bbdd3-110">Identifica la chiusura transitiva di oggetti a cui le radici fanno riferimento tramite i riferimenti di campo di membri diretti e tramite le dipendenze `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="bbdd3-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bbdd3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bbdd3-111">Requirements</span></span>  
 <span data-ttu-id="bbdd3-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbdd3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbdd3-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbdd3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbdd3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbdd3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbdd3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbdd3-115">See also</span></span>

- [<span data-ttu-id="bbdd3-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="bbdd3-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="bbdd3-117">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="bbdd3-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
