---
title: Interfaccia ICorProfilerAssemblyReferenceProvider
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: f5ba72dca25889fb57c0ae1bb2429e54a8cf2228
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128721"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="a8105-102">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="a8105-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="a8105-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="a8105-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a8105-104">Consente al profiler di informare il Common Language Runtime (CLR) dei riferimenti ad assembly che il profiler aggiungerà nel callback [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a8105-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8105-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a8105-105">Methods</span></span>  
  
|<span data-ttu-id="a8105-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="a8105-106">Method</span></span>|<span data-ttu-id="a8105-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8105-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8105-108">Metodo AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="a8105-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="a8105-109">Informa il CLR di un riferimento a un assembly che il Profiler prevede di aggiungere nel callback [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a8105-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8105-110">Note</span><span class="sxs-lookup"><span data-stu-id="a8105-110">Remarks</span></span>  
 <span data-ttu-id="a8105-111">CLR passa al profiler un oggetto `ICorProfilerAssemblyReferenceProvider` interfaccia nel callback [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a8105-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="a8105-112">Ciò consente al profiler di informare il CLR dei riferimenti ad assembly che il Profiler prevede di aggiungere in un secondo momento nel metodo [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="a8105-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="a8105-113">.</span><span class="sxs-lookup"><span data-stu-id="a8105-113">callback.</span></span> <span data-ttu-id="a8105-114">In questo modo viene migliorata la precisione del walker di chiusura dei riferimenti ad assembly di CLR e dei relativi algoritmi per determinare la possibilità di condivisione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="a8105-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="a8105-115">Questa interfaccia può essere usata solo nel callback [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) che passa questo oggetto interfaccia al profiler.</span><span class="sxs-lookup"><span data-stu-id="a8105-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8105-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8105-116">Requirements</span></span>  
 <span data-ttu-id="a8105-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8105-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8105-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8105-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8105-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8105-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8105-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8105-120">See also</span></span>

- [<span data-ttu-id="a8105-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a8105-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
