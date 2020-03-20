---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinishedICorProfilerCallback8::DynamicMethodJITCompilationFinished Method
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175109"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="33765-102">Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinishedICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span><span class="sxs-lookup"><span data-stu-id="33765-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="33765-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="33765-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="33765-104">Notifica al profiler ogni volta che la compilazione JIT di un metodo dinamico è stata completata.</span><span class="sxs-lookup"><span data-stu-id="33765-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33765-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33765-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33765-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="33765-106">Parameters</span></span>  
<span data-ttu-id="33765-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="33765-107">[in] `functionId`</span></span>  
<span data-ttu-id="33765-108">Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="33765-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="33765-109">[in] `hrStatus` Valore che indica se la compilazione JIT ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="33765-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="33765-110">[in] `fIsSafeToBlock` per indicare che il blocco può causare il runtime di attendere che il thread chiamante venga restituito da questo 
 `true` callback; `false` per indicare che il blocco non influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="33765-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="33765-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="33765-111">Remarks</span></span>  

<span data-ttu-id="33765-112">Questo callback viene attivato ogni volta che la compilazione JIT di un metodo dinamico è terminata.</span><span class="sxs-lookup"><span data-stu-id="33765-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="33765-113">Sono inclusi vari stub IL e metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="33765-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="33765-114">Il suo scopo è quello di fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="33765-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="33765-115">`functionId`i valori non possono essere utilizzati per risolvere i relativi token di metadati, perché i metodi dinamici non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="33765-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="33765-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33765-116">Requirements</span></span>  
 <span data-ttu-id="33765-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33765-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33765-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33765-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33765-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33765-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33765-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33765-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33765-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33765-121">See also</span></span>

- [<span data-ttu-id="33765-122">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="33765-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="33765-123">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="33765-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
