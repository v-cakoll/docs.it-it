---
title: Interfaccia ICorProfilerAssemblyReferenceProvider
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerAssemblyReferenceProvider
api_location: mscorwks.dll
api_type: COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2120e400d4ecd23c86cdae7b12d8706b35e8ca08
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="b6cbb-102">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="b6cbb-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="b6cbb-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="b6cbb-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b6cbb-104">Consente al profiler di comunicare a common language runtime (CLR) di riferimenti ad assembly che verranno aggiunti nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="b6cbb-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6cbb-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b6cbb-105">Methods</span></span>  
  
|<span data-ttu-id="b6cbb-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b6cbb-106">Method</span></span>|<span data-ttu-id="b6cbb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6cbb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6cbb-108">Metodo AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="b6cbb-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="b6cbb-109">Informa il CLR di un riferimento all'assembly che il profiler prevede di aggiungere il [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="b6cbb-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6cbb-110">Note</span><span class="sxs-lookup"><span data-stu-id="b6cbb-110">Remarks</span></span>  
 <span data-ttu-id="b6cbb-111">CLR passa al profiler un `ICorProfilerAssemblyReferenceProvider` oggetto interfaccia di [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="b6cbb-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="b6cbb-112">Ciò consente al profiler di indicare a CLR di riferimenti ad assembly che verranno aggiunti successivamente nel [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="b6cbb-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="b6cbb-113">.</span><span class="sxs-lookup"><span data-stu-id="b6cbb-113">callback.</span></span> <span data-ttu-id="b6cbb-114">In questo modo viene migliorata la precisione del walker di chiusura dei riferimenti ad assembly di CLR e dei relativi algoritmi per determinare la possibilità di condivisione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="b6cbb-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="b6cbb-115">Questa interfaccia può essere utilizzata solo nella [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback che passa l'oggetto di interfaccia al profiler.</span><span class="sxs-lookup"><span data-stu-id="b6cbb-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6cbb-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6cbb-116">Requirements</span></span>  
 <span data-ttu-id="b6cbb-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6cbb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6cbb-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6cbb-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6cbb-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6cbb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cbb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6cbb-120">See Also</span></span>  
 [<span data-ttu-id="b6cbb-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b6cbb-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
