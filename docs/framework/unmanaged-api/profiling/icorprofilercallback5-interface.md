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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 338bc10e02ceba5fb38c70088c4151271fca9b2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454411"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="cff20-102">Interfaccia ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="cff20-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="cff20-103">Integra le informazioni per consentire a un profiler di identificare la chiusura completa degli oggetti in tempo reale, quando utilizzato con il [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)(metodo) con il [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) e [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="cff20-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="cff20-104">Per sottoscrivere le notifiche correlate agli handle dipendenti, l'interfaccia `ICorProfilerCallback5` deve essere implementata da un profiler della memoria gestito.</span><span class="sxs-lookup"><span data-stu-id="cff20-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cff20-105">Note</span><span class="sxs-lookup"><span data-stu-id="cff20-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cff20-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="cff20-106">Methods</span></span>  
  
|<span data-ttu-id="cff20-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="cff20-107">Method</span></span>|<span data-ttu-id="cff20-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cff20-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cff20-109">Metodo ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="cff20-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="cff20-110">Identifica la chiusura transitiva di oggetti a cui le radici fanno riferimento tramite i riferimenti di campo di membri diretti e tramite le dipendenze `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="cff20-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cff20-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cff20-111">Requirements</span></span>  
 <span data-ttu-id="cff20-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cff20-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff20-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cff20-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cff20-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff20-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff20-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cff20-115">See Also</span></span>  
 [<span data-ttu-id="cff20-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="cff20-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="cff20-117">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="cff20-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
