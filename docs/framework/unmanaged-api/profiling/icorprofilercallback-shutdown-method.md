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
ms.openlocfilehash: f6873de1a864489d144a671b1a9e1349eaf77d15
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503182"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="7ee73-102">Metodo ICorProfilerCallback::Shutdown</span><span class="sxs-lookup"><span data-stu-id="7ee73-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="7ee73-103">Notifica al profiler che l'applicazione è in fase di chiusura.</span><span class="sxs-lookup"><span data-stu-id="7ee73-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ee73-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7ee73-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7ee73-105">Remarks</span></span>  
 <span data-ttu-id="7ee73-106">Il codice del profiler non può chiamare in modo sicuro i metodi dell'interfaccia [ICorProfilerInfo](icorprofilerinfo-interface.md) dopo la `Shutdown` chiamata del metodo.</span><span class="sxs-lookup"><span data-stu-id="7ee73-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="7ee73-107">Tutte le chiamate ai `ICorProfilerInfo` metodi generano un comportamento non definito dopo la `Shutdown` restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="7ee73-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="7ee73-108">Alcuni eventi non modificabili possono ancora verificarsi dopo l'arresto. il profiler deve prestare attenzione a restituire immediatamente quando si verifica questo problema.</span><span class="sxs-lookup"><span data-stu-id="7ee73-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="7ee73-109">Il `Shutdown` metodo verrà chiamato solo se l'applicazione gestita da profilare è stata avviata come codice gestito, ovvero il frame iniziale nello stack del processo è gestito.</span><span class="sxs-lookup"><span data-stu-id="7ee73-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="7ee73-110">Se l'applicazione è stata avviata come codice non gestito, ma in seguito viene passata al codice gestito, creando quindi un'istanza del Common Language Runtime (CLR), `Shutdown` non verrà chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ee73-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="7ee73-111">In questi casi, il profiler deve includere nella relativa libreria una `DllMain` routine che usa il valore DLL_PROCESS_DETACH per liberare le risorse ed eseguire l'elaborazione di pulitura dei dati, ad esempio lo scaricamento delle tracce sul disco e così via.</span><span class="sxs-lookup"><span data-stu-id="7ee73-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="7ee73-112">In generale, il profiler deve far fronte a arresti imprevisti.</span><span class="sxs-lookup"><span data-stu-id="7ee73-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="7ee73-113">È ad esempio possibile che un processo venga interrotto dal `TerminateProcess` metodo Win32 (dichiarato in winbase. h).</span><span class="sxs-lookup"><span data-stu-id="7ee73-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="7ee73-114">In altri casi, CLR interromperà alcuni thread gestiti (thread in background) senza dover recapitano i messaggi di distruzione ordinata.</span><span class="sxs-lookup"><span data-stu-id="7ee73-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ee73-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ee73-115">Requirements</span></span>  
 <span data-ttu-id="7ee73-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ee73-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee73-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ee73-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ee73-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ee73-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ee73-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ee73-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee73-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ee73-120">See also</span></span>

- [<span data-ttu-id="7ee73-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7ee73-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7ee73-122">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="7ee73-122">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
