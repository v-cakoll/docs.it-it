---
title: Funzione FunctionEnter2
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: f4deec3e2b49b5cd6a924af8024e775c5c549f97
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440856"
---
# <a name="functionenter2-function"></a><span data-ttu-id="57074-102">Funzione FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="57074-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="57074-103">Notifica al profiler che il controllo viene passato a una funzione e fornisce informazioni sugli stack frame e sugli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="57074-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="57074-104">Questa funzione sostituisce la funzione [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="57074-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57074-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57074-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57074-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="57074-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="57074-107">in Identificatore della funzione a cui viene passato il controllo.</span><span class="sxs-lookup"><span data-stu-id="57074-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="57074-108">in Identificatore della funzione di cui è stato eseguito il mapping, specificato in precedenza dal profiler tramite la funzione [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="57074-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="57074-109">in Valore `COR_PRF_FRAME_INFO` che punta alle informazioni relative al stack frame.</span><span class="sxs-lookup"><span data-stu-id="57074-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="57074-110">Il profiler deve considerarlo come un handle opaco che può essere passato di nuovo al motore di esecuzione nel metodo [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="57074-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="57074-111">in Puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) che specifica le posizioni in memoria degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="57074-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="57074-112">Per accedere alle informazioni sugli argomenti, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_ARGS`.</span><span class="sxs-lookup"><span data-stu-id="57074-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="57074-113">Il profiler può usare il metodo [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento.</span><span class="sxs-lookup"><span data-stu-id="57074-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57074-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="57074-114">Remarks</span></span>  
 <span data-ttu-id="57074-115">I valori dei parametri `func` e `argumentInfo` non sono validi dopo che la funzione `FunctionEnter2` restituisce il risultato perché i valori possono essere modificati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="57074-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="57074-116">La funzione `FunctionEnter2` è un callback. è necessario implementarla.</span><span class="sxs-lookup"><span data-stu-id="57074-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="57074-117">L'implementazione deve usare l'attributo della classe di archiviazione `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="57074-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="57074-118">Il motore di esecuzione non salva i registri prima di chiamare questa funzione.</span><span class="sxs-lookup"><span data-stu-id="57074-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="57074-119">In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).</span><span class="sxs-lookup"><span data-stu-id="57074-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="57074-120">All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="57074-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="57074-121">L'implementazione di `FunctionEnter2` non deve bloccarsi perché ritarda Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="57074-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="57074-122">L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="57074-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="57074-123">Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionEnter2` non restituisce.</span><span class="sxs-lookup"><span data-stu-id="57074-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="57074-124">Inoltre, la funzione `FunctionEnter2` non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di managed memory.</span><span class="sxs-lookup"><span data-stu-id="57074-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57074-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57074-125">Requirements</span></span>  
 <span data-ttu-id="57074-126">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57074-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57074-127">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="57074-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="57074-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57074-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57074-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57074-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57074-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57074-130">See also</span></span>

- [<span data-ttu-id="57074-131">Funzione FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="57074-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="57074-132">Funzione FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="57074-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="57074-133">Metodo SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="57074-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="57074-134">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="57074-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
