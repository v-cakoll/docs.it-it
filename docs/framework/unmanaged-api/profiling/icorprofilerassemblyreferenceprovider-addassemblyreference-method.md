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
ms.openlocfilehash: 2357e5348192db5d41adfe1176300359440aeee3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866728"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="732b6-102">Metodo ICorProfilerAssemblyReferenceProvider::AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="732b6-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="732b6-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="732b6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="732b6-104">Informa il Common Language Runtime (CLR) di un riferimento a un assembly che il Profiler prevede di aggiungere nel callback [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="732b6-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="732b6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="732b6-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="732b6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="732b6-106">Parameters</span></span>

- `pAssemblyRefInfo`

  <span data-ttu-id="732b6-107">Puntatore a una struttura [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) che fornisce a CLR informazioni su un riferimento a un assembly che deve considerare quando esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="732b6-107">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="732b6-108">Note</span><span class="sxs-lookup"><span data-stu-id="732b6-108">Remarks</span></span>  
 <span data-ttu-id="732b6-109">Il profiler chiama questo metodo per ogni assembly di destinazione a cui fa riferimento l'assembly specificato nell'argomento `wszAssemblyPath` del callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="732b6-109">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="732b6-110">L'oggetto interfaccia [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) viene passato al callback [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) del profiler, insieme al percorso e al nome dell'assembly nell'argomento `wszAssemblyPath`.</span><span class="sxs-lookup"><span data-stu-id="732b6-110">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="732b6-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="732b6-111">Requirements</span></span>  
 <span data-ttu-id="732b6-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="732b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="732b6-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="732b6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="732b6-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="732b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="732b6-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="732b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732b6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="732b6-116">See also</span></span>

- [<span data-ttu-id="732b6-117">Interfaccia ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="732b6-117">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="732b6-118">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="732b6-118">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="732b6-119">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="732b6-119">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
