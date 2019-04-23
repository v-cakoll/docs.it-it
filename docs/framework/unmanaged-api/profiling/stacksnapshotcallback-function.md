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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 891423661f45a1167d53385e6e0306fb09487278
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198322"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="cefe4-102">Funzione StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="cefe4-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="cefe4-103">Fornisce informazioni su ogni frame gestito e ogni esecuzione dei frame non gestiti nello stack durante un'analisi dello stack, che viene avviata dal profiler il [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="cefe4-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cefe4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cefe4-104">Syntax</span></span>  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cefe4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cefe4-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="cefe4-106">[in] Se questo valore è zero, il callback è per un'esecuzione dei frame non gestite; in caso contrario, è l'identificatore di una funzione gestita e questa richiamata viene eseguita per un frame gestito.</span><span class="sxs-lookup"><span data-stu-id="cefe4-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="cefe4-107">[in] Il valore del puntatore dell'istruzione di codice nativo nel frame.</span><span class="sxs-lookup"><span data-stu-id="cefe4-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="cefe4-108">[in] Oggetto `COR_PRF_FRAME_INFO` valore cui fa riferimento alle informazioni sullo stack frame.</span><span class="sxs-lookup"><span data-stu-id="cefe4-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="cefe4-109">Questo valore è valido per essere utilizzato solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="cefe4-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cefe4-110">[in] Le dimensioni dei `CONTEXT` struttura, a cui fa riferimento il `context` parametro.</span><span class="sxs-lookup"><span data-stu-id="cefe4-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="cefe4-111">[in] Un puntatore a un Win32 `CONTEXT` struttura che rappresenta lo stato della CPU per il frame.</span><span class="sxs-lookup"><span data-stu-id="cefe4-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="cefe4-112">Il `context` parametro è valido solo se è stato passato il flag COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="cefe4-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="cefe4-113">[in] Un puntatore ai dati client, che vengano passati direttamente da `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="cefe4-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cefe4-114">Note</span><span class="sxs-lookup"><span data-stu-id="cefe4-114">Remarks</span></span>  
 <span data-ttu-id="cefe4-115">Il `StackSnapshotCallback` (funzione) viene implementata dal writer del profiler.</span><span class="sxs-lookup"><span data-stu-id="cefe4-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="cefe4-116">È necessario limitare la complessità del lavoro svolto `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="cefe4-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="cefe4-117">Ad esempio, quando si usa `ICorProfilerInfo2::DoStackSnapshot` in modo asincrono, il thread di destinazione può contenere blocchi.</span><span class="sxs-lookup"><span data-stu-id="cefe4-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="cefe4-118">Se all'interno del codice `StackSnapshotCallback` richiede gli stessi blocchi, un deadlock.</span><span class="sxs-lookup"><span data-stu-id="cefe4-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="cefe4-119">Il `ICorProfilerInfo2::DoStackSnapshot` chiamate al metodo il `StackSnapshotCallback` funzione una volta ogni frame gestito o una sola volta per ogni esecuzione dei frame non gestiti.</span><span class="sxs-lookup"><span data-stu-id="cefe4-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="cefe4-120">Se `StackSnapshotCallback` viene chiamato per un'esecuzione dei frame non gestiti, il profiler può usare il contesto di registro (fa il `context` parametro) per eseguire la propria analisi dello stack non gestito.</span><span class="sxs-lookup"><span data-stu-id="cefe4-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="cefe4-121">In questo caso, Win32 `CONTEXT` struttura rappresenta lo stato della CPU per il frame recentemente inserito nell'esecuzione dei frame non gestiti.</span><span class="sxs-lookup"><span data-stu-id="cefe4-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="cefe4-122">Sebbene Win32 `CONTEXT` struttura include i valori per tutti i registri, è necessario basarsi solo sui valori del registro dei puntatori di stack frame registro dei puntatori, registro dei puntatori (istruzione) e non volatile (cioè, mantenuti) registri integer.</span><span class="sxs-lookup"><span data-stu-id="cefe4-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cefe4-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cefe4-123">Requirements</span></span>  
 <span data-ttu-id="cefe4-124">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cefe4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cefe4-125">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="cefe4-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cefe4-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cefe4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cefe4-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cefe4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefe4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cefe4-128">See also</span></span>

- [<span data-ttu-id="cefe4-129">Metodo DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="cefe4-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="cefe4-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="cefe4-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
