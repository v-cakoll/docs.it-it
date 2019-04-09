---
title: Metodo ICorProfilerInfo4::GetReJITIDs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121615"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="04803-102">Metodo ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="04803-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="04803-103">Restituisce una matrice di ID che identifica tutte ricompilata in JIT le versioni della funzione specificata che sono ancora allocate.</span><span class="sxs-lookup"><span data-stu-id="04803-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="04803-104">Sono incluse versioni ricompilata in JIT di funzioni che sono state ripristinate successivamente ma non ancora liberate (ad esempio, quando il dominio applicazione che contiene la funzione ripristinata è ancora in uso).</span><span class="sxs-lookup"><span data-stu-id="04803-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04803-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04803-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04803-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="04803-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="04803-107">[in] Il `FunctionID` dell'istanza di funzione per cui si desidera ottenere le versioni.</span><span class="sxs-lookup"><span data-stu-id="04803-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="04803-108">[in] Il numero di ID ricompilata in JIT allocati nel `reJitIds` matrice.</span><span class="sxs-lookup"><span data-stu-id="04803-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="04803-109">[out] Il numero effettivo di ID ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="04803-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="04803-110">[out] Una matrice allocata dal chiamante che conterrà gli ID ricompilata in JIT della funzione specificato.</span><span class="sxs-lookup"><span data-stu-id="04803-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04803-111">Note</span><span class="sxs-lookup"><span data-stu-id="04803-111">Remarks</span></span>  
 `GetReJITIDs` <span data-ttu-id="04803-112">Enumera gli ID active ricompilata in JIT per un'istanza della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="04803-112">enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="04803-113">Segue lo stesso modello di utilizzo delle altre `ICorProfilerInfo` funzioni che accettano i buffer allocato dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="04803-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04803-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04803-114">Requirements</span></span>  
 <span data-ttu-id="04803-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04803-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04803-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04803-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04803-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04803-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="04803-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="04803-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04803-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04803-119">See also</span></span>

- [<span data-ttu-id="04803-120">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="04803-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="04803-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="04803-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="04803-122">Profilatura</span><span class="sxs-lookup"><span data-stu-id="04803-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
