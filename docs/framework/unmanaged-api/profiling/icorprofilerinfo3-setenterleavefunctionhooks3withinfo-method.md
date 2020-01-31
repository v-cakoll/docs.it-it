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
ms.openlocfilehash: 4fe18b4f07e6f282571b13faff5ce51b66ce416b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868486"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="4a8db-102">Metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4a8db-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="4a8db-103">Specifica le funzioni implementate dal profiler che verranno chiamate sugli hook [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) delle funzioni gestite.</span><span class="sxs-lookup"><span data-stu-id="4a8db-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a8db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a8db-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a8db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a8db-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="4a8db-106">in Puntatore all'implementazione da utilizzare come callback `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="4a8db-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="4a8db-107">in Puntatore all'implementazione da utilizzare come callback `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="4a8db-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="4a8db-108">in Puntatore all'implementazione da utilizzare come callback `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="4a8db-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a8db-109">Note</span><span class="sxs-lookup"><span data-stu-id="4a8db-109">Remarks</span></span>  
 <span data-ttu-id="4a8db-110">Gli hook [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) forniscono stack frame e l'ispezione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4a8db-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="4a8db-111">Per accedere a tali informazioni, è necessario impostare i flag `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`e/o `COR_PRF_ENABLE_FRAME_INFO`.</span><span class="sxs-lookup"><span data-stu-id="4a8db-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="4a8db-112">Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il metodo `SetEnterLeaveFunctionHooks3WithInfo` per registrare l'implementazione di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4a8db-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="4a8db-113">Solo un set di callback può essere attivo alla volta e la versione più recente ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="4a8db-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="4a8db-114">Se pertanto un profiler chiama sia [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) che `SetEnterLeaveFunctionHooks3WithInfo`, viene utilizzato `SetEnterLeaveFunctionHooks3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="4a8db-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="4a8db-115">Il metodo `SetEnterLeaveFunctionHooks3WithInfo` può essere chiamato solo dal callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del profiler.</span><span class="sxs-lookup"><span data-stu-id="4a8db-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a8db-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4a8db-116">Requirements</span></span>  
 <span data-ttu-id="4a8db-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a8db-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a8db-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a8db-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a8db-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a8db-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a8db-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a8db-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8db-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a8db-121">See also</span></span>

- [<span data-ttu-id="4a8db-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="4a8db-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="4a8db-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="4a8db-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="4a8db-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="4a8db-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="4a8db-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="4a8db-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="4a8db-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4a8db-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="4a8db-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4a8db-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="4a8db-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4a8db-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="4a8db-129">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="4a8db-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="4a8db-130">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="4a8db-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4a8db-131">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="4a8db-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4a8db-132">Profilatura</span><span class="sxs-lookup"><span data-stu-id="4a8db-132">Profiling</span></span>](index.md)
