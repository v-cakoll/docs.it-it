---
title: Metodo ICorProfilerInfo3::GetFunctionTailcall3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: 5346792cb2a1309268cb4ba48625aa559777fbaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176994"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="0a52e-102">Metodo ICorProfilerInfo3::GetFunctionTailcall3Info</span><span class="sxs-lookup"><span data-stu-id="0a52e-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="0a52e-103">Fornisce lo stack frame della funzione segnalata al profiler dalla funzione [FunctionTailcall3WithInfo.](functiontailcall3withinfo-function.md)</span><span class="sxs-lookup"><span data-stu-id="0a52e-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="0a52e-104">Questo metodo può essere chiamato solo durante il callback `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="0a52e-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a52e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a52e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a52e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a52e-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0a52e-107">[in] Oggetto `FunctionID` della funzione restituita.</span><span class="sxs-lookup"><span data-stu-id="0a52e-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="0a52e-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="0a52e-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="0a52e-109">Il profiler deve `eltInfo` fornire lo stesso che `FunctionTailcall3WithInfo` è stato dato al profiler dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="0a52e-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="0a52e-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="0a52e-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="0a52e-111">Questo handle è valido solo durante il callback `FunctionTailcall3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="0a52e-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a52e-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0a52e-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a52e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a52e-113">Requirements</span></span>  
 <span data-ttu-id="0a52e-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a52e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a52e-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0a52e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0a52e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a52e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a52e-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a52e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a52e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a52e-118">See also</span></span>

- [<span data-ttu-id="0a52e-119">FunzioneEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0a52e-119">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="0a52e-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0a52e-120">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="0a52e-121">FunzioneTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0a52e-121">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="0a52e-122">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="0a52e-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="0a52e-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="0a52e-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0a52e-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="0a52e-124">Profiling</span></span>](index.md)
