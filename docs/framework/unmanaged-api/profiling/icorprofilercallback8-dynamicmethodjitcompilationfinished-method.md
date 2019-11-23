---
title: ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e04459614ca697908fb9b71ecc3931ac305a838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136576"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="533ea-102">ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="533ea-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="533ea-103">[Supportato in .NET Framework 4,7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="533ea-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="533ea-104">Notifica al profiler ogni volta che la compilazione JIT di un metodo dinamico è stata completata.</span><span class="sxs-lookup"><span data-stu-id="533ea-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="533ea-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="533ea-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="533ea-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="533ea-106">Parameters</span></span>  
<span data-ttu-id="533ea-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="533ea-107">[in] `functionId`</span></span>  
<span data-ttu-id="533ea-108">Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="533ea-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="533ea-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="533ea-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="533ea-110">Valore che indica se la compilazione JIT è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="533ea-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="533ea-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="533ea-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="533ea-112">`true` per indicare che il blocco può causare la restituzione del thread chiamante da parte del runtime. `false` per indicare che il blocco non influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="533ea-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="533ea-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="533ea-113">Remarks</span></span>  

<span data-ttu-id="533ea-114">Questo callback viene attivato ogni volta che viene completata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="533ea-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="533ea-115">Sono inclusi vari Stub IL e metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="533ea-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="533ea-116">Il suo obiettivo consiste nel fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="533ea-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="533ea-117">non è possibile usare i valori `functionId` per risolvere i token dei metadati, perché i metodi dinamici non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="533ea-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="533ea-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="533ea-118">Requirements</span></span>  
 <span data-ttu-id="533ea-119">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="533ea-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="533ea-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="533ea-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="533ea-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="533ea-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="533ea-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="533ea-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533ea-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="533ea-123">See also</span></span>

- [<span data-ttu-id="533ea-124">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="533ea-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="533ea-125">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="533ea-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
