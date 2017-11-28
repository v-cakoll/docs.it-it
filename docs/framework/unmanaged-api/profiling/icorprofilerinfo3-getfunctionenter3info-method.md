---
title: Metodo ICorProfilerInfo3::GetFunctionEnter3Info
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a75f76af924c3e75d280c36fb5f436498dc6c862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="8d0ef-102">Metodo ICorProfilerInfo3::GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="8d0ef-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="8d0ef-103">Fornisce le informazioni sullo stack frame e l'argomento della funzione da segnalare al profiler tramite la [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="8d0ef-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="8d0ef-104">Questo metodo può essere chiamato solo durante il callback `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d0ef-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d0ef-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d0ef-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d0ef-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8d0ef-107">[in] `FunctionID` della funzione da immettere.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="8d0ef-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="8d0ef-109">Il profiler deve fornire la stessa `eltInfo` che fornito il [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="8d0ef-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="8d0ef-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="8d0ef-111">Questo handle è valido solo durante il callback `FunctionEnter3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="8d0ef-112">[in, out] Un puntatore alla dimensione totale, espressa in byte, del [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) struttura (più eventuali altre [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) strutture per gli intervalli di argomenti a cui puntati `pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="8d0ef-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="8d0ef-113">Se la dimensione specificata non è sufficiente, viene restituito ERROR_INSUFFICIENT_BUFFER e la dimensione prevista viene archiviata in `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="8d0ef-114">Per chiamare `GetFunctionEnter3Info` per recuperare il valore previsto per `*pcbArgumentInfo`, impostare `*pcbArgumentInfo`=0 e `pArgumentInfo`=NULL.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="8d0ef-115">[out] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) struttura che descrive le posizioni degli argomenti della funzione in memoria, in ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d0ef-116">Note</span><span class="sxs-lookup"><span data-stu-id="8d0ef-116">Remarks</span></span>  
 <span data-ttu-id="8d0ef-117">Il profiler deve allocare spazio sufficiente per la struttura `COR_PRF_FUNCTION_ARGUMENT_INFO` della funzione che viene esaminata e deve indicare la dimensione nel parametro `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="8d0ef-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d0ef-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d0ef-118">Requirements</span></span>  
 <span data-ttu-id="8d0ef-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d0ef-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d0ef-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d0ef-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d0ef-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d0ef-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d0ef-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d0ef-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0ef-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d0ef-123">See Also</span></span>  
 [<span data-ttu-id="8d0ef-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8d0ef-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="8d0ef-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8d0ef-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="8d0ef-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8d0ef-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="8d0ef-127">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8d0ef-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="8d0ef-128">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="8d0ef-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8d0ef-129">Profilatura</span><span class="sxs-lookup"><span data-stu-id="8d0ef-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
