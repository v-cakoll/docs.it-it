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
ms.openlocfilehash: 49e154ade91ea1a207645f924bd8aea1dbdb635c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868122"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="4fb8d-102">Funzione StackSnapshotCallback</span><span class="sxs-lookup"><span data-stu-id="4fb8d-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="4fb8d-103">Fornisce al profiler informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti nello stack durante un percorso stack, avviato dal metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4fb8d-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb8d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fb8d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4fb8d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4fb8d-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="4fb8d-106">in Se questo valore è zero, questo callback è per un'esecuzione di frame non gestiti; in caso contrario, è l'identificatore di una funzione gestita e questo callback è per un frame gestito.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="4fb8d-107">in Valore del puntatore all'istruzione del codice nativo nel frame.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="4fb8d-108">in Valore `COR_PRF_FRAME_INFO` che fa riferimento a informazioni relative al stack frame.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="4fb8d-109">Questo valore è valido per essere utilizzato solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="4fb8d-110">in Dimensioni della struttura di `CONTEXT`, a cui fa riferimento il parametro di `context`.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="4fb8d-111">in Puntatore a una struttura di `CONTEXT` Win32 che rappresenta lo stato della CPU per questo frame.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="4fb8d-112">Il parametro `context` è valido solo se il flag di COR_PRF_SNAPSHOT_CONTEXT è stato passato in `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="4fb8d-113">in Puntatore ai dati del client, che viene passato direttamente da `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fb8d-114">Note</span><span class="sxs-lookup"><span data-stu-id="4fb8d-114">Remarks</span></span>  
 <span data-ttu-id="4fb8d-115">La funzione `StackSnapshotCallback` viene implementata dal writer del profiler.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="4fb8d-116">È necessario limitare la complessità delle operazioni eseguite in `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="4fb8d-117">Ad esempio, quando si usa `ICorProfilerInfo2::DoStackSnapshot` in modo asincrono, è possibile che il thread di destinazione mantenga i blocchi.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="4fb8d-118">Se il codice all'interno `StackSnapshotCallback` richiede gli stessi blocchi, è possibile che si verifichi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="4fb8d-119">Il metodo `ICorProfilerInfo2::DoStackSnapshot` chiama la funzione `StackSnapshotCallback` una volta per ogni frame gestito o una volta per ogni esecuzione di frame non gestiti.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="4fb8d-120">Se `StackSnapshotCallback` viene chiamato per un'esecuzione di frame non gestiti, il profiler può usare il contesto di registro (a cui fa riferimento il parametro `context`) per eseguire il proprio percorso stack non gestito.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="4fb8d-121">In questo caso, la struttura di `CONTEXT` Win32 rappresenta lo stato della CPU per il frame inserito più di recente all'interno dell'esecuzione di frame non gestiti.</span><span class="sxs-lookup"><span data-stu-id="4fb8d-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="4fb8d-122">Sebbene la struttura di `CONTEXT` Win32 includa valori per tutti i registri, è necessario basarsi solo sui valori del registro del puntatore dello stack, il registro del puntatore ai frame, il registro del puntatore all'istruzione e i registri di interi non volatili (ovvero conservati).</span><span class="sxs-lookup"><span data-stu-id="4fb8d-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fb8d-123">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4fb8d-123">Requirements</span></span>  
 <span data-ttu-id="4fb8d-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fb8d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fb8d-125">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="4fb8d-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4fb8d-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fb8d-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fb8d-127">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fb8d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb8d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fb8d-128">See also</span></span>

- [<span data-ttu-id="4fb8d-129">Metodo DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="4fb8d-129">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="4fb8d-130">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="4fb8d-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
