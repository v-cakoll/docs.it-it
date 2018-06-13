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
ms.openlocfilehash: 33430db8f83f446bab21b1fc86a5c165aecef2af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452364"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="3c841-102">Metodo ICorProfilerAssemblyReferenceProvider::AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="3c841-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="3c841-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="3c841-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3c841-104">Indica a common language runtime (CLR) di un riferimento all'assembly che il profiler prevede di aggiungere il [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="3c841-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c841-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c841-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c841-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c841-106">Parameters</span></span>  
 <span data-ttu-id="3c841-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="3c841-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="3c841-108">Un puntatore a un [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) struttura che fornisce informazioni su un riferimento all'assembly che deve considerare quando si esegue un percorso di chiusura del riferimento all'assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="3c841-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c841-109">Note</span><span class="sxs-lookup"><span data-stu-id="3c841-109">Remarks</span></span>  
 <span data-ttu-id="3c841-110">Il profiler chiama questo metodo per ogni assembly di destinazione al quale intende fare riferimento dall'assembly specificato nella `wszAssemblyPath` argomento del [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="3c841-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="3c841-111">Il [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interfaccia oggetto viene passato al profiler [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, insieme al nome in e il percorso dell'assembly di `wszAssemblyPath` argomento.</span><span class="sxs-lookup"><span data-stu-id="3c841-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c841-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c841-112">Requirements</span></span>  
 <span data-ttu-id="3c841-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c841-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c841-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c841-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c841-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3c841-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c841-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c841-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c841-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c841-117">See Also</span></span>  
 [<span data-ttu-id="3c841-118">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="3c841-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 [<span data-ttu-id="3c841-119">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="3c841-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [<span data-ttu-id="3c841-120">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="3c841-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
