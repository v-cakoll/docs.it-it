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
ms.openlocfilehash: 13a298451c3e8e1c5809cc1cb222acb5ab85714b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866689"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="d7d93-102">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="d7d93-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="d7d93-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="d7d93-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d7d93-104">Consente al profiler di informare il Common Language Runtime (CLR) dei riferimenti ad assembly che il profiler aggiungerà nel callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d7d93-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7d93-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d7d93-105">Methods</span></span>  
  
|<span data-ttu-id="d7d93-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d7d93-106">Method</span></span>|<span data-ttu-id="d7d93-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7d93-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7d93-108">Metodo AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="d7d93-108">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="d7d93-109">Informa il CLR di un riferimento a un assembly che il Profiler prevede di aggiungere nel callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d7d93-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7d93-110">Note</span><span class="sxs-lookup"><span data-stu-id="d7d93-110">Remarks</span></span>  
 <span data-ttu-id="d7d93-111">CLR passa al profiler un oggetto `ICorProfilerAssemblyReferenceProvider` interfaccia nel callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d7d93-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="d7d93-112">Ciò consente al profiler di informare il CLR dei riferimenti ad assembly che il Profiler prevede di aggiungere in un secondo momento nel metodo [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="d7d93-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="d7d93-113">.</span><span class="sxs-lookup"><span data-stu-id="d7d93-113">callback.</span></span> <span data-ttu-id="d7d93-114">In questo modo viene migliorata la precisione del walker di chiusura dei riferimenti ad assembly di CLR e dei relativi algoritmi per determinare la possibilità di condivisione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="d7d93-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="d7d93-115">Questa interfaccia può essere usata solo nel callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) che passa questo oggetto interfaccia al profiler.</span><span class="sxs-lookup"><span data-stu-id="d7d93-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7d93-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d7d93-116">Requirements</span></span>  
 <span data-ttu-id="d7d93-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7d93-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7d93-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7d93-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7d93-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7d93-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d93-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d93-120">See also</span></span>

- [<span data-ttu-id="d7d93-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="d7d93-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
