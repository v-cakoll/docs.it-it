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
ms.openlocfilehash: 9069498a4f62f4d9dbb50a7075323b14c3cc5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868447"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="7b2d2-102">Metodo ICorProfilerInfo4::GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="7b2d2-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="7b2d2-103">Restituisce una matrice di ID che identificano tutte le versioni ricompilate in JIT della funzione specificata ancora allocate.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="7b2d2-104">Sono incluse le versioni ricompilate tramite JIT di funzioni che sono state successivamente ripristinate ma non ancora liberate, ad esempio quando il dominio dell'applicazione che contiene la funzione ripristinata è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2d2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b2d2-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b2d2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b2d2-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7b2d2-107">in `FunctionID` dell'istanza della funzione per la quale enumerare le versioni.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="7b2d2-108">in Numero di ID ricompilati in modalità JIT allocati nella matrice `reJitIds`.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="7b2d2-109">out Numero effettivo di ID ricompilati in JIT.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="7b2d2-110">out Matrice allocata dal chiamante che conterrà gli ID ricompilati JIT per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b2d2-111">Note</span><span class="sxs-lookup"><span data-stu-id="7b2d2-111">Remarks</span></span>  
 <span data-ttu-id="7b2d2-112">`GetReJITIDs` enumera gli ID ricompilati JIT attivi per un'istanza di funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="7b2d2-113">Segue lo stesso modello di utilizzo di altre funzioni `ICorProfilerInfo` che accettano buffer allocati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b2d2-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7b2d2-114">Requirements</span></span>  
 <span data-ttu-id="7b2d2-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2d2-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b2d2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b2d2-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b2d2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b2d2-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b2d2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b2d2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b2d2-119">See also</span></span>

- [<span data-ttu-id="7b2d2-120">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="7b2d2-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="7b2d2-121">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="7b2d2-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7b2d2-122">Profilatura</span><span class="sxs-lookup"><span data-stu-id="7b2d2-122">Profiling</span></span>](index.md)
