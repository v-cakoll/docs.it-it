---
title: ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136458"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="cd249-102">ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="cd249-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="cd249-103">[Supportato in .NET Framework 4,7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="cd249-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="cd249-104">Notifica al profiler ogni volta che viene avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="cd249-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd249-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd249-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd249-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd249-106">Parameters</span></span>  
<span data-ttu-id="cd249-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="cd249-107">[in] `functionId`</span></span>  
<span data-ttu-id="cd249-108">Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="cd249-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="cd249-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="cd249-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="cd249-110">`true` per indicare che il blocco può causare la restituzione del thread chiamante da parte del runtime. `false` per indicare che il blocco non influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="cd249-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="cd249-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="cd249-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="cd249-112">Puntatore al primo byte dell'intestazione IL del metodo.</span><span class="sxs-lookup"><span data-stu-id="cd249-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="cd249-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="cd249-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="cd249-114">Numero di byte nell'intestazione IL.</span><span class="sxs-lookup"><span data-stu-id="cd249-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="cd249-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cd249-115">Remarks</span></span>  

<span data-ttu-id="cd249-116">Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="cd249-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="cd249-117">Sono inclusi vari Stub IL e metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="cd249-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="cd249-118">Il suo obiettivo consiste nel fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="cd249-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="cd249-119">non è possibile usare i valori `functionId` per risolvere i token dei metadati, perché i metodi dinamici non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="cd249-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="cd249-120">Il puntatore `pILHeader` è valido solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="cd249-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd249-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd249-121">Requirements</span></span>  
 <span data-ttu-id="cd249-122">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd249-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd249-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd249-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd249-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd249-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd249-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd249-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd249-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd249-126">See also</span></span>

- [<span data-ttu-id="cd249-127">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="cd249-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="cd249-128">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="cd249-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
