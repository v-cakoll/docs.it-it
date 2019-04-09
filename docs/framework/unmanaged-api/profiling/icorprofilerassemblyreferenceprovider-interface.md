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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bad1cc71b9a27896141837a6d342f2cfe068fc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089732"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="afd4c-102">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="afd4c-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="afd4c-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="afd4c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="afd4c-104">Consente al profiler di comunicare a common language runtime (CLR) dei riferimenti all'assembly che il profiler aggiungerà nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="afd4c-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afd4c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="afd4c-105">Methods</span></span>  
  
|<span data-ttu-id="afd4c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="afd4c-106">Method</span></span>|<span data-ttu-id="afd4c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afd4c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afd4c-108">Metodo AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="afd4c-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="afd4c-109">Indica a CLR il riferimento a un assembly che il profiler prevede di aggiungere il [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="afd4c-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afd4c-110">Note</span><span class="sxs-lookup"><span data-stu-id="afd4c-110">Remarks</span></span>  
 <span data-ttu-id="afd4c-111">CLR passa al profiler un `ICorProfilerAssemblyReferenceProvider` nell'oggetto di interfaccia di [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="afd4c-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="afd4c-112">Ciò consente al profiler di indicare a CLR di riferimenti ad assembly che il profiler prevede di aggiungere successivamente nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="afd4c-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="afd4c-113">.</span><span class="sxs-lookup"><span data-stu-id="afd4c-113">callback.</span></span> <span data-ttu-id="afd4c-114">In questo modo viene migliorata la precisione del walker di chiusura dei riferimenti ad assembly di CLR e dei relativi algoritmi per determinare la possibilità di condivisione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="afd4c-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="afd4c-115">Questa interfaccia può essere utilizzata solo nel [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback che passa l'oggetto di interfaccia al profiler.</span><span class="sxs-lookup"><span data-stu-id="afd4c-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afd4c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="afd4c-116">Requirements</span></span>  
 <span data-ttu-id="afd4c-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afd4c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afd4c-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="afd4c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="afd4c-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="afd4c-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="afd4c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afd4c-120">See also</span></span>

- [<span data-ttu-id="afd4c-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="afd4c-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
