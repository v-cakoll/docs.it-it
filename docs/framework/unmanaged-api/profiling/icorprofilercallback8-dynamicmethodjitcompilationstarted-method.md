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
ms.openlocfilehash: a4c434c5d458602db8a4d582b239d6e57def6ace
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498999"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="5c8da-102">ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="5c8da-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="5c8da-103">[Supportato in .NET Framework 4,7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="5c8da-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="5c8da-104">Notifica al profiler ogni volta che viene avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="5c8da-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c8da-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c8da-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c8da-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c8da-106">Parameters</span></span>  
<span data-ttu-id="5c8da-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="5c8da-107">[in] `functionId`</span></span>  
<span data-ttu-id="5c8da-108">Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="5c8da-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="5c8da-109">[in] `fIsSafeToBlock` 
 `true` per indicare che il blocco può far sì che il runtime attenda il ritorno del thread chiamante da questo callback; `false`per indicare che il blocco non influisce sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="5c8da-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="5c8da-110">[in] `pILHeader` Puntatore al primo byte dell'intestazione IL del metodo.</span><span class="sxs-lookup"><span data-stu-id="5c8da-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="5c8da-111">[in] `cbILHeader` Numero di byte nell'intestazione IL.</span><span class="sxs-lookup"><span data-stu-id="5c8da-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c8da-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c8da-112">Remarks</span></span>  

<span data-ttu-id="5c8da-113">Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="5c8da-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="5c8da-114">Sono inclusi vari Stub IL e metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="5c8da-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="5c8da-115">Il suo obiettivo consiste nel fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="5c8da-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="5c8da-116">`functionId`non è possibile usare i valori per risolvere i token dei metadati, perché i metodi dinamici non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="5c8da-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="5c8da-117">Il `pILHeader` puntatore è valido solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="5c8da-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c8da-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c8da-118">Requirements</span></span>  
 <span data-ttu-id="5c8da-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c8da-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c8da-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c8da-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c8da-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c8da-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c8da-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5c8da-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c8da-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c8da-123">See also</span></span>

- [<span data-ttu-id="5c8da-124">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="5c8da-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="5c8da-125">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="5c8da-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
