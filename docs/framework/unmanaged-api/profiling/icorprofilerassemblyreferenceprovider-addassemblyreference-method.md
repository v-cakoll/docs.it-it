---
title: Metodo ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 762ebbe141473277dc064b36c6229f82d348f976
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582089"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="fc876-102">Metodo ICorProfilerAssemblyReferenceProvider::AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="fc876-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="fc876-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="fc876-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fc876-104">Indica a common language runtime (CLR) di un riferimento all'assembly che il profiler prevede di aggiungere il [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="fc876-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc876-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc876-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc876-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc876-106">Parameters</span></span>  
 <span data-ttu-id="fc876-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="fc876-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="fc876-108">Un puntatore a un [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) struttura che fornisce informazioni su un riferimento all'assembly che deve considerare quando si esegue un Walker di chiusura di riferimenti ad assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="fc876-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc876-109">Note</span><span class="sxs-lookup"><span data-stu-id="fc876-109">Remarks</span></span>  
 <span data-ttu-id="fc876-110">Il profiler chiama questo metodo per ogni assembly di destinazione a cui fare riferimento dall'assembly specificato nella `wszAssemblyPath` argomento del [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="fc876-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="fc876-111">Il [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) oggetto di interfaccia viene passata al profiler [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, con il percorso dell'assembly e il nome di `wszAssemblyPath` argomento.</span><span class="sxs-lookup"><span data-stu-id="fc876-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc876-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc876-112">Requirements</span></span>  
 <span data-ttu-id="fc876-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc876-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc876-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc876-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc876-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc876-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc876-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc876-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc876-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc876-117">See also</span></span>
- [<span data-ttu-id="fc876-118">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="fc876-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="fc876-119">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="fc876-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="fc876-120">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="fc876-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
