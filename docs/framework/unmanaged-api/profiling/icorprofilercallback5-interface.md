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
ms.openlocfilehash: 02a690503d7b6323f19dcb66247d8a552b760b1c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499207"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="eca8e-102">Interfaccia ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="eca8e-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="eca8e-103">Integra le informazioni per consentire a un profiler di identificare la chiusura completa di oggetti attivi, se usato con il metodo [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) insieme ai metodi [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) e [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eca8e-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="eca8e-104">Per sottoscrivere le notifiche correlate agli handle dipendenti, l'interfaccia `ICorProfilerCallback5` deve essere implementata da un profiler della memoria gestito.</span><span class="sxs-lookup"><span data-stu-id="eca8e-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eca8e-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eca8e-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eca8e-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="eca8e-106">Methods</span></span>  
  
|<span data-ttu-id="eca8e-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="eca8e-107">Method</span></span>|<span data-ttu-id="eca8e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eca8e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eca8e-109">Metodo ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="eca8e-109">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="eca8e-110">Identifica la chiusura transitiva di oggetti a cui le radici fanno riferimento tramite i riferimenti di campo di membri diretti e tramite le dipendenze `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="eca8e-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eca8e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eca8e-111">Requirements</span></span>  
 <span data-ttu-id="eca8e-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eca8e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eca8e-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eca8e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eca8e-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eca8e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca8e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eca8e-115">See also</span></span>

- [<span data-ttu-id="eca8e-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="eca8e-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="eca8e-117">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="eca8e-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
