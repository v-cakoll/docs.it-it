---
title: Metodo ICorProfilerCallback::Shutdown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 63e41df8af85d94df068526ef69708687b341e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446939"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="33a8a-102">Metodo ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="33a8a-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="33a8a-103">Notifies the profiler that the application is shutting down.</span><span class="sxs-lookup"><span data-stu-id="33a8a-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33a8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33a8a-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="33a8a-105">Note</span><span class="sxs-lookup"><span data-stu-id="33a8a-105">Remarks</span></span>  
 <span data-ttu-id="33a8a-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span><span class="sxs-lookup"><span data-stu-id="33a8a-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="33a8a-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span><span class="sxs-lookup"><span data-stu-id="33a8a-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="33a8a-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span><span class="sxs-lookup"><span data-stu-id="33a8a-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="33a8a-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span><span class="sxs-lookup"><span data-stu-id="33a8a-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="33a8a-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span><span class="sxs-lookup"><span data-stu-id="33a8a-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="33a8a-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span><span class="sxs-lookup"><span data-stu-id="33a8a-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="33a8a-112">In general, the profiler must cope with unexpected shutdowns.</span><span class="sxs-lookup"><span data-stu-id="33a8a-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="33a8a-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span><span class="sxs-lookup"><span data-stu-id="33a8a-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="33a8a-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span><span class="sxs-lookup"><span data-stu-id="33a8a-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33a8a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33a8a-115">Requirements</span></span>  
 <span data-ttu-id="33a8a-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33a8a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33a8a-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33a8a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33a8a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33a8a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33a8a-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33a8a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a8a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33a8a-120">See also</span></span>

- [<span data-ttu-id="33a8a-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="33a8a-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="33a8a-122">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="33a8a-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
