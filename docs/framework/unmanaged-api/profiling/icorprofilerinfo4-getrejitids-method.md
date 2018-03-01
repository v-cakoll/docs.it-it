---
title: Metodo ICorProfilerInfo4::GetReJITIDs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fb1e507bea6f52e4959f241f1507807a76c0ec5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="edd68-102">Metodo ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="edd68-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="edd68-103">Restituisce una matrice di ID che identifica tutte ricompilata in JIT le versioni della funzione specificata che sono ancora allocate.</span><span class="sxs-lookup"><span data-stu-id="edd68-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="edd68-104">Sono incluse versioni ricompilata in JIT di funzioni che sono state ripristinate in seguito, ma non ancora liberate (ad esempio, quando il dominio applicazione che contiene la funzione ripristinata è ancora in uso).</span><span class="sxs-lookup"><span data-stu-id="edd68-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edd68-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edd68-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edd68-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="edd68-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="edd68-107">[in] Il `FunctionID` dell'istanza di funzione per cui si desidera ottenere le versioni.</span><span class="sxs-lookup"><span data-stu-id="edd68-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="edd68-108">[in] Il numero di ID ricompilata in JIT allocata nel `reJitIds` matrice.</span><span class="sxs-lookup"><span data-stu-id="edd68-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="edd68-109">[out] Il numero effettivo di ID ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="edd68-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="edd68-110">[out] Una matrice allocata dal chiamante che conterrà gli ID ricompilata in JIT per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="edd68-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edd68-111">Note</span><span class="sxs-lookup"><span data-stu-id="edd68-111">Remarks</span></span>  
 <span data-ttu-id="edd68-112">`GetReJITIDs`Enumera gli ID active ricompilata in JIT per un'istanza della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="edd68-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="edd68-113">Segue lo stesso modello di utilizzo delle altre `ICorProfilerInfo` funzioni che accettano i buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="edd68-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edd68-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="edd68-114">Requirements</span></span>  
 <span data-ttu-id="edd68-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edd68-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edd68-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="edd68-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="edd68-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edd68-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edd68-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edd68-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd68-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edd68-119">See Also</span></span>  
 [<span data-ttu-id="edd68-120">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="edd68-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="edd68-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="edd68-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="edd68-122">Profilatura</span><span class="sxs-lookup"><span data-stu-id="edd68-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
