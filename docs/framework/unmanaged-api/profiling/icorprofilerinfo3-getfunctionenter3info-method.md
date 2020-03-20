---
title: Metodo ICorProfilerInfo3::GetFunctionEnter3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 50d16b8036144d6ede349149fa4ae37344064d8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177020"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="f2ea8-102">Metodo ICorProfilerInfo3::GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="f2ea8-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="f2ea8-103">Fornisce le informazioni sullo stack frame e sull'argomento della funzione segnalata al profiler dalla funzione [FunctionEnter3WithInfo.](functionenter3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="f2ea8-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="f2ea8-104">Questo metodo può essere chiamato solo durante il callback `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ea8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2ea8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2ea8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2ea8-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f2ea8-107">[in] `FunctionID` della funzione da immettere.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="f2ea8-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="f2ea8-109">Il profiler deve `eltInfo` fornire lo stesso che è stato dato dal [FunctionEnter3WithInfo](functionenter3withinfo-function.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="f2ea8-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="f2ea8-111">Questo handle è valido solo durante il callback `FunctionEnter3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionEnter3Info`.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="f2ea8-112">[in, out] Puntatore alla dimensione totale, in byte, della struttura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) (più eventuali strutture `pArgumentInfo` [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) aggiuntive per gli intervalli di argomenti a cui punta ).</span><span class="sxs-lookup"><span data-stu-id="f2ea8-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="f2ea8-113">Se la dimensione specificata non è sufficiente, viene restituito ERROR_INSUFFICIENT_BUFFER e la dimensione prevista viene archiviata in `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="f2ea8-114">Per chiamare `GetFunctionEnter3Info` per recuperare il valore previsto per `*pcbArgumentInfo`, impostare `*pcbArgumentInfo`=0 e `pArgumentInfo`=NULL.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="f2ea8-115">[fuori] Puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) che descrive le posizioni degli argomenti della funzione in memoria, in ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ea8-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f2ea8-116">Remarks</span></span>  
 <span data-ttu-id="f2ea8-117">Il profiler deve allocare spazio sufficiente per la struttura `COR_PRF_FUNCTION_ARGUMENT_INFO` della funzione che viene esaminata e deve indicare la dimensione nel parametro `pcbArgumentInfo`.</span><span class="sxs-lookup"><span data-stu-id="f2ea8-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ea8-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2ea8-118">Requirements</span></span>  
 <span data-ttu-id="f2ea8-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ea8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ea8-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2ea8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2ea8-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ea8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ea8-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ea8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ea8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2ea8-123">See also</span></span>

- [<span data-ttu-id="f2ea8-124">FunzioneEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f2ea8-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="f2ea8-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f2ea8-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="f2ea8-126">FunzioneTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f2ea8-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f2ea8-127">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="f2ea8-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f2ea8-128">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f2ea8-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f2ea8-129">Profilatura</span><span class="sxs-lookup"><span data-stu-id="f2ea8-129">Profiling</span></span>](index.md)
