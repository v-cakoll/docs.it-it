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
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="1ea60-102">Metodo ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="1ea60-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="1ea60-103">Notifica al profiler che l'applicazione è in fase di chiusura.</span><span class="sxs-lookup"><span data-stu-id="1ea60-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ea60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ea60-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1ea60-105">Note</span><span class="sxs-lookup"><span data-stu-id="1ea60-105">Remarks</span></span>  
 <span data-ttu-id="1ea60-106">Il codice del profiler non può chiamare in modo sicuro i metodi dell'interfaccia [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) dopo la chiamata del metodo `Shutdown`.</span><span class="sxs-lookup"><span data-stu-id="1ea60-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="1ea60-107">Tutte le chiamate ai metodi `ICorProfilerInfo` hanno come risultato un comportamento non definito dopo la restituzione del metodo `Shutdown`.</span><span class="sxs-lookup"><span data-stu-id="1ea60-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="1ea60-108">Alcuni eventi non modificabili possono ancora verificarsi dopo l'arresto. il profiler deve prestare attenzione a restituire immediatamente quando si verifica questo problema.</span><span class="sxs-lookup"><span data-stu-id="1ea60-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="1ea60-109">Il metodo `Shutdown` verrà chiamato solo se l'applicazione gestita sottomessa a profilatura è stata avviata come codice gestito, ovvero il frame iniziale nello stack del processo è gestito.</span><span class="sxs-lookup"><span data-stu-id="1ea60-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="1ea60-110">Se l'applicazione è stata avviata come codice non gestito, ma in seguito viene passata al codice gestito, creando quindi un'istanza del Common Language Runtime (CLR), `Shutdown` non verrà chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ea60-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="1ea60-111">In questi casi, il profiler deve includere nella relativa libreria un `DllMain` routine che usa il valore DLL_PROCESS_DETACH per liberare le risorse ed eseguire l'elaborazione di pulitura dei dati, ad esempio lo scaricamento delle tracce sul disco e così via.</span><span class="sxs-lookup"><span data-stu-id="1ea60-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="1ea60-112">In generale, il profiler deve far fronte a arresti imprevisti.</span><span class="sxs-lookup"><span data-stu-id="1ea60-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="1ea60-113">È ad esempio possibile che un processo venga interrotto da Win32 `TerminateProcess` metodo (dichiarato in winbase. h).</span><span class="sxs-lookup"><span data-stu-id="1ea60-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="1ea60-114">In altri casi, CLR interromperà alcuni thread gestiti (thread in background) senza dover recapitano i messaggi di distruzione ordinata.</span><span class="sxs-lookup"><span data-stu-id="1ea60-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ea60-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ea60-115">Requirements</span></span>  
 <span data-ttu-id="1ea60-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ea60-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ea60-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ea60-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ea60-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ea60-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ea60-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ea60-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea60-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ea60-120">See also</span></span>

- [<span data-ttu-id="1ea60-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1ea60-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1ea60-122">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="1ea60-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
