---
title: Funzione StackSnapshotCallback
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: a0f5316900dedc6c8983f9e670f60767ed783a40
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493994"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="55c95-102">Funzione StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="55c95-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="55c95-103">Fornisce al profiler informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti nello stack durante un percorso stack, avviato dal metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="55c95-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c95-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55c95-104">Syntax</span></span>  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c95-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55c95-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="55c95-106">in Se questo valore è zero, questo callback è per un'esecuzione di frame non gestiti; in caso contrario, è l'identificatore di una funzione gestita e questo callback è per un frame gestito.</span><span class="sxs-lookup"><span data-stu-id="55c95-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="55c95-107">in Valore del puntatore all'istruzione del codice nativo nel frame.</span><span class="sxs-lookup"><span data-stu-id="55c95-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="55c95-108">in `COR_PRF_FRAME_INFO`Valore che fa riferimento a informazioni sul stack frame.</span><span class="sxs-lookup"><span data-stu-id="55c95-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="55c95-109">Questo valore è valido per essere utilizzato solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="55c95-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="55c95-110">in Dimensione della `CONTEXT` struttura, a cui fa riferimento il `context` parametro.</span><span class="sxs-lookup"><span data-stu-id="55c95-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="55c95-111">in Puntatore a una struttura Win32 `CONTEXT` che rappresenta lo stato della CPU per questo frame.</span><span class="sxs-lookup"><span data-stu-id="55c95-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="55c95-112">Il `context` parametro è valido solo se il flag di COR_PRF_SNAPSHOT_CONTEXT è stato passato `ICorProfilerInfo2::DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="55c95-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="55c95-113">in Puntatore ai dati del client, che viene passato direttamente da `ICorProfilerInfo2::DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="55c95-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55c95-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="55c95-114">Remarks</span></span>  
 <span data-ttu-id="55c95-115">La `StackSnapshotCallback` funzione viene implementata dal writer del profiler.</span><span class="sxs-lookup"><span data-stu-id="55c95-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="55c95-116">È necessario limitare la complessità delle operazioni eseguite in `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="55c95-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="55c95-117">Ad esempio, quando `ICorProfilerInfo2::DoStackSnapshot` si usa in modo asincrono, è possibile che il thread di destinazione mantenga i blocchi.</span><span class="sxs-lookup"><span data-stu-id="55c95-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="55c95-118">Se il codice all'interno di `StackSnapshotCallback` richiede gli stessi blocchi, è possibile che si verifichi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="55c95-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="55c95-119">Il `ICorProfilerInfo2::DoStackSnapshot` metodo chiama la `StackSnapshotCallback` funzione una volta per ogni frame gestito o una volta per ogni esecuzione di frame non gestiti.</span><span class="sxs-lookup"><span data-stu-id="55c95-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="55c95-120">Se `StackSnapshotCallback` viene chiamato per un'esecuzione di frame non gestiti, il profiler può usare il contesto del registro (a cui fa riferimento il `context` parametro) per eseguire il proprio percorso stack non gestito.</span><span class="sxs-lookup"><span data-stu-id="55c95-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="55c95-121">In questo caso, la `CONTEXT` struttura Win32 rappresenta lo stato della CPU per il frame inserito più di recente all'interno dell'esecuzione di frame non gestiti.</span><span class="sxs-lookup"><span data-stu-id="55c95-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="55c95-122">Sebbene la `CONTEXT` struttura Win32 includa valori per tutti i registri, è consigliabile fare affidamento solo sui valori del registro del puntatore dello stack, del registro dei puntatori ai frame, del registro del puntatore all'istruzione e dei registri integer non volatili (ovvero conservati).</span><span class="sxs-lookup"><span data-stu-id="55c95-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c95-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55c95-123">Requirements</span></span>  
 <span data-ttu-id="55c95-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c95-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c95-125">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="55c95-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="55c95-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55c95-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55c95-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c95-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c95-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55c95-128">See also</span></span>

- [<span data-ttu-id="55c95-129">Metodo DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="55c95-129">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="55c95-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="55c95-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
