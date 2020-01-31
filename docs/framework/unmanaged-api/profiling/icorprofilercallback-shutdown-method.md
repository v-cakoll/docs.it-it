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
ms.openlocfilehash: 490f9dd5446a51bd07881cdb9825d737e380a63e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865857"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="e4b28-102">Metodo ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="e4b28-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="e4b28-103">Notifica al profiler che l'applicazione è in fase di chiusura.</span><span class="sxs-lookup"><span data-stu-id="e4b28-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4b28-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4b28-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e4b28-105">Note</span><span class="sxs-lookup"><span data-stu-id="e4b28-105">Remarks</span></span>  
 <span data-ttu-id="e4b28-106">Il codice del profiler non può chiamare in modo sicuro i metodi dell'interfaccia [ICorProfilerInfo](icorprofilerinfo-interface.md) dopo la chiamata del metodo `Shutdown`.</span><span class="sxs-lookup"><span data-stu-id="e4b28-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="e4b28-107">Tutte le chiamate ai metodi `ICorProfilerInfo` hanno come risultato un comportamento non definito dopo la restituzione del metodo `Shutdown`.</span><span class="sxs-lookup"><span data-stu-id="e4b28-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="e4b28-108">Alcuni eventi non modificabili possono ancora verificarsi dopo l'arresto. il profiler deve prestare attenzione a restituire immediatamente quando si verifica questo problema.</span><span class="sxs-lookup"><span data-stu-id="e4b28-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="e4b28-109">Il metodo `Shutdown` verrà chiamato solo se l'applicazione gestita sottomessa a profilatura è stata avviata come codice gestito, ovvero il frame iniziale nello stack del processo è gestito.</span><span class="sxs-lookup"><span data-stu-id="e4b28-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="e4b28-110">Se l'applicazione è stata avviata come codice non gestito, ma in seguito viene passata al codice gestito, creando quindi un'istanza del Common Language Runtime (CLR), `Shutdown` non verrà chiamata.</span><span class="sxs-lookup"><span data-stu-id="e4b28-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="e4b28-111">In questi casi, il profiler deve includere nella relativa libreria un `DllMain` routine che usa il valore DLL_PROCESS_DETACH per liberare le risorse ed eseguire l'elaborazione di pulitura dei dati, ad esempio lo scaricamento delle tracce sul disco e così via.</span><span class="sxs-lookup"><span data-stu-id="e4b28-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="e4b28-112">In generale, il profiler deve far fronte a arresti imprevisti.</span><span class="sxs-lookup"><span data-stu-id="e4b28-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="e4b28-113">È ad esempio possibile che un processo venga interrotto da Win32 `TerminateProcess` metodo (dichiarato in winbase. h).</span><span class="sxs-lookup"><span data-stu-id="e4b28-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="e4b28-114">In altri casi, CLR interromperà alcuni thread gestiti (thread in background) senza dover recapitano i messaggi di distruzione ordinata.</span><span class="sxs-lookup"><span data-stu-id="e4b28-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4b28-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e4b28-115">Requirements</span></span>  
 <span data-ttu-id="e4b28-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4b28-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4b28-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4b28-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4b28-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4b28-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4b28-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4b28-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b28-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4b28-120">See also</span></span>

- [<span data-ttu-id="e4b28-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e4b28-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e4b28-122">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="e4b28-122">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
