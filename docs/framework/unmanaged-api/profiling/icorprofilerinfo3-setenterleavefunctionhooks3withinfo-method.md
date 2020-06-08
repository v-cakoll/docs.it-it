---
title: Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: d40cb424306535cc502d930dd61e6a1e254667da
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496178"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="b2bba-102">Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b2bba-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="b2bba-103">Specifica le funzioni implementate dal profiler che verranno chiamate sugli hook [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="b2bba-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2bba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2bba-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2bba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2bba-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="b2bba-106">in Puntatore all'implementazione da utilizzare come `FunctionEnter3WithInfo` callback.</span><span class="sxs-lookup"><span data-stu-id="b2bba-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="b2bba-107">in Puntatore all'implementazione da utilizzare come `FunctionLeave3WithInfo` callback.</span><span class="sxs-lookup"><span data-stu-id="b2bba-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="b2bba-108">in Puntatore all'implementazione da utilizzare come `FunctionTailcall3WithInfo` callback.</span><span class="sxs-lookup"><span data-stu-id="b2bba-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2bba-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b2bba-109">Remarks</span></span>  
 <span data-ttu-id="b2bba-110">Gli hook [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) forniscono stack frame e l'ispezione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b2bba-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="b2bba-111">Per accedere a tali informazioni, `COR_PRF_ENABLE_FUNCTION_ARGS` `COR_PRF_ENABLE_FUNCTION_RETVAL` è necessario impostare i flag, e/o `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="b2bba-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="b2bba-112">Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il `SetEnterLeaveFunctionHooks3WithInfo` metodo per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b2bba-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b2bba-113">Solo un set di callback può essere attivo alla volta e la versione più recente ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="b2bba-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="b2bba-114">Se pertanto un profiler chiama sia [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) che `SetEnterLeaveFunctionHooks3WithInfo` , `SetEnterLeaveFunctionHooks3WithInfo` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b2bba-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="b2bba-115">Il `SetEnterLeaveFunctionHooks3WithInfo` metodo può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="b2bba-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2bba-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2bba-116">Requirements</span></span>  
 <span data-ttu-id="b2bba-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2bba-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2bba-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2bba-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2bba-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2bba-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2bba-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2bba-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bba-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2bba-121">See also</span></span>

- [<span data-ttu-id="b2bba-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="b2bba-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="b2bba-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b2bba-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="b2bba-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b2bba-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="b2bba-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="b2bba-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="b2bba-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b2bba-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="b2bba-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b2bba-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="b2bba-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b2bba-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b2bba-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="b2bba-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="b2bba-130">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="b2bba-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b2bba-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b2bba-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b2bba-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="b2bba-132">Profiling</span></span>](index.md)
