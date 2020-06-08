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
ms.openlocfilehash: 554cc93de934061e87322c7557e05545e5e7bc62
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499077"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="0095c-102">ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="0095c-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="0095c-103">[Supportato in .NET Framework 4,7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="0095c-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="0095c-104">Notifica al profiler ogni volta che la compilazione JIT di un metodo dinamico è stata completata.</span><span class="sxs-lookup"><span data-stu-id="0095c-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0095c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0095c-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0095c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0095c-106">Parameters</span></span>  
<span data-ttu-id="0095c-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="0095c-107">[in] `functionId`</span></span>  
<span data-ttu-id="0095c-108">Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="0095c-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="0095c-109">[in] `hrStatus` Valore che indica se la compilazione JIT è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="0095c-109">[in] `hrStatus` A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="0095c-110">[in] `fIsSafeToBlock` 
 `true` per indicare che il blocco può far sì che il runtime attenda il ritorno del thread chiamante da questo callback; `false`per indicare che il blocco non influisce sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="0095c-110">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="0095c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0095c-111">Remarks</span></span>  

<span data-ttu-id="0095c-112">Questo callback viene attivato ogni volta che viene completata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="0095c-112">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="0095c-113">Sono inclusi vari Stub IL e metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="0095c-113">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="0095c-114">Il suo obiettivo consiste nel fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="0095c-114">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="0095c-115">`functionId`non è possibile usare i valori per risolvere i token dei metadati, perché i metodi dinamici non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="0095c-115">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="0095c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0095c-116">Requirements</span></span>  
 <span data-ttu-id="0095c-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0095c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0095c-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0095c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0095c-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0095c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0095c-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0095c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0095c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0095c-121">See also</span></span>

- [<span data-ttu-id="0095c-122">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="0095c-122">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="0095c-123">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="0095c-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
