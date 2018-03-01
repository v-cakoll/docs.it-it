---
title: Metodo ICorProfilerInfo2::DoStackSnapshot
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5548254eb160547643a874fd2e31a085ec6f3ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="a1bbc-102">Metodo ICorProfilerInfo2::DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="a1bbc-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="a1bbc-103">Verifica i frame gestiti nello stack per il thread specificato e invia informazioni al profiler tramite un callback.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bbc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1bbc-104">Syntax</span></span>  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1bbc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1bbc-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="a1bbc-106">[in] L'ID del thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="a1bbc-107">Il passaggio di null in `thread` viene generato uno snapshot del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="a1bbc-108">Se un `ThreadID` di viene passato un altro thread, sospende il thread di common language runtime (CLR), esegue lo snapshot e riprende.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="a1bbc-109">[in] Un puntatore all'implementazione del [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) metodo, che viene chiamato da Common Language Runtime per fornire al profiler con informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="a1bbc-110">Il `StackSnapshotCallback` metodo è implementato dal writer del profiler.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="a1bbc-111">[in] Il valore di [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumerazione che specifica la quantità di dati da passare per ciascun frame `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="a1bbc-112">[in] Un puntatore ai dati client, che vengano passati direttamente tramite il `StackSnapshotCallback` funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="a1bbc-113">[in] Un puntatore a un Win32 `CONTEXT` struttura, viene utilizzato per inizializzare il percorso dello stack.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="a1bbc-114">Win32 `CONTEXT` struttura contiene i valori dei registri della CPU e rappresenta lo stato della CPU in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="a1bbc-115">Il valore di inizializzazione consente a CLR di determinare il punto di inizio dell'analisi dello stack, se l'inizio dello stack è il codice di supporto non gestita. in caso contrario, il valore di inizializzazione viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="a1bbc-116">È necessario specificare un valore di inizializzazione per una verifica asincrona.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="a1bbc-117">Se si sta eseguendo una verifica sincrona, non è necessario alcun valore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="a1bbc-118">Il `context` parametro è valido solo se è stato passato il flag COR_PRF_SNAPSHOT_CONTEXT il `infoFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a1bbc-119">[in] Le dimensioni del `CONTEXT` struttura, a cui fa riferimento il `context` parametro.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1bbc-120">Note</span><span class="sxs-lookup"><span data-stu-id="a1bbc-120">Remarks</span></span>  
 <span data-ttu-id="a1bbc-121">Passare null per `thread` viene generato uno snapshot del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="a1bbc-122">Solo se il thread di destinazione è sospeso al momento, è possono eseguire gli snapshot di altri thread.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="a1bbc-123">Quando il profiler richiede analizzare lo stack, chiama `DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="a1bbc-124">Prima di CLR viene restituito dalla chiamata, chiama il `StackSnapshotCallback` più volte, una volta per ogni frame gestito (o esecuzione di frame non gestiti) nello stack.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="a1bbc-125">Quando vengono rilevati frame non gestiti, è necessario verificarli manualmente.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="a1bbc-126">L'ordine in cui viene esaminato lo stack è l'opposto di come i frame sono stati inseriti nello stack: foglia ultimo fotogramma (inserito per ultimo) in primo luogo, principale fotogramma (inserito per primo).</span><span class="sxs-lookup"><span data-stu-id="a1bbc-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="a1bbc-127">Per ulteriori informazioni su come programmare il profiler per spostarti chiamate negli stack gestiti, vedere [analisi dello Stack del Profiler in .NET Framework 2.0: nozioni di base e oltre](http://go.microsoft.com/fwlink/?LinkId=73638).</span><span class="sxs-lookup"><span data-stu-id="a1bbc-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](http://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="a1bbc-128">Un percorso stack può essere sincrona o asincrona, come illustrato nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="a1bbc-129">Sincrono dello stack</span><span class="sxs-lookup"><span data-stu-id="a1bbc-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="a1bbc-130">Un percorso stack sincrono implica percorsi nello stack del thread corrente in risposta a un callback.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="a1bbc-131">Non richiede il seeding o sospensione.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="a1bbc-132">Apportate sincrono, chiamare in risposta a una chiamata a uno del profiler CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)), chiamano `DoStackSnapshot` per analizzare lo stack del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="a1bbc-133">Ciò è utile quando si desidera visualizzare lo stack di aspetto analogo al seguente in una notifica, ad esempio [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1bbc-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="a1bbc-134">È sufficiente chiamare `DoStackSnapshot` dall'interno del `ICorProfilerCallback` , passando null nel `context` e `thread` parametri.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="a1bbc-135">Analisi dello Stack asincrona</span><span class="sxs-lookup"><span data-stu-id="a1bbc-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="a1bbc-136">Un'analisi dello stack asincrono comporta la verifica dello stack di un thread diverso o percorsi nello stack del thread corrente, non in risposta a un callback, ma assumendo puntatore all'istruzione del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="a1bbc-137">Una verifica asincrona richiede un valore di inizializzazione se l'inizio dello stack è il codice non gestito che non fa parte di una piattaforma invoke (PInvoke) o chiamata COM, ma il codice helper in CLR.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="a1bbc-138">Codice che esegue la compilazione o la garbage collection di (JIT) di just-in-time è ad esempio, codice di supporto.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="a1bbc-139">Si ottiene un valore di inizializzazione sospendendo direttamente il thread di destinazione e un esame relativo stack frame manualmente, fino a individuare il livello più alto gestito.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="a1bbc-140">Dopo che il thread di destinazione è sospeso, è possibile ottenere il contesto di registro corrente del thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="a1bbc-141">Successivamente, determinare se il contesto del registro punta a codice non gestito chiamando [ICorProfilerInfo::](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) , ovvero se viene restituito un `FunctionID` uguale a zero, il frame è codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="a1bbc-142">A questo punto, analizzare lo stack fino a raggiunga il primo frame gestito e quindi calcola il contesto del valore di inizializzazione in base al contesto di registro per quel frame.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="a1bbc-143">Chiamare `DoStackSnapshot` con il contesto del valore di inizializzazione per iniziare il percorso stack asincrona.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="a1bbc-144">Se non si specifica un valore di inizializzazione, `DoStackSnapshot` potrebbe ignorare i frame gestiti nella parte superiore dello stack e, di conseguenza, verrà visualizzato un percorso di stack incompleto.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="a1bbc-145">Se si specifica un valore di inizializzazione, deve puntare a compilato tramite JIT o Native Image Generator (Ngen.exe)-; codice generato in caso contrario, `DoStackSnapshot` restituisce il codice di errore CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="a1bbc-146">Analisi dello stack asincrona può facilmente causare deadlock o violazioni di accesso, a meno che non si seguono queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="a1bbc-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
-   <span data-ttu-id="a1bbc-147">Quando si sospendono direttamente i thread, tenere presente che solo un thread che non ha mai eseguito codice gestito è possibile sospendere un altro thread.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
-   <span data-ttu-id="a1bbc-148">Blocco sempre il [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback fino al termine dell'analisi dello stack del thread.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
-   <span data-ttu-id="a1bbc-149">Non mantenere un blocco mentre il profiler chiama una funzione CLR che può attivare una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="a1bbc-150">Ovvero, non mantenere un blocco se il thread proprietario può effettuare una chiamata che attiva un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="a1bbc-151">È inoltre disponibile un rischio di deadlock se si chiama `DoStackSnapshot` da un thread che ha creato il profiler in modo che è possibile analizzare lo stack di un thread di destinazione diversa.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="a1bbc-152">La prima volta che il thread è stato creato viene inserito determinate `ICorProfilerInfo*` metodi (inclusi `DoStackSnapshot`), CLR esegue per ogni thread, l'inizializzazione specifica del CLR su tale thread.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="a1bbc-153">Se il profiler ha sospeso il thread di destinazione i cui stack si sta tentando di analizzare e se si è verificato un thread di destinazione sia il proprietario di un blocco necessari per eseguire l'inizializzazione di singoli thread, si verificherà un deadlock.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="a1bbc-154">Per evitare il deadlock, effettuare una chiamata iniziale in `DoStackSnapshot` dal thread del creato profiler per verificare il thread di destinazione separato, ma non sospendere il thread di destinazione prima.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="a1bbc-155">Questa chiamata iniziale garantisce che l'inizializzazione di singoli thread può essere completato senza deadlock.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="a1bbc-156">Se `DoStackSnapshot` ha esito positivo e segnala almeno un frame, in seguito, sarà sicuro per tale thread creato profiler sospendere tutti i thread di destinazione e chiamare `DoStackSnapshot` per analizzare lo stack di thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a1bbc-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bbc-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1bbc-157">Requirements</span></span>  
 <span data-ttu-id="a1bbc-158">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1bbc-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bbc-159">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1bbc-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1bbc-160">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1bbc-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1bbc-161">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bbc-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bbc-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1bbc-162">See Also</span></span>  
 [<span data-ttu-id="a1bbc-163">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a1bbc-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="a1bbc-164">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="a1bbc-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
