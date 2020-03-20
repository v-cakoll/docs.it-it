---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStartedICorProfilerCallback8::DynamicMethodJITCompilationStarted Method
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177046"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="7cb6e-102">Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStartedICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span><span class="sxs-lookup"><span data-stu-id="7cb6e-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="7cb6e-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="7cb6e-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="7cb6e-104">Notifica al profiler ogni volta che è stata avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cb6e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cb6e-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cb6e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7cb6e-106">Parameters</span></span>  
<span data-ttu-id="7cb6e-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="7cb6e-107">[in] `functionId`</span></span>  
<span data-ttu-id="7cb6e-108">Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="7cb6e-109">[in] `fIsSafeToBlock` per indicare che il blocco può causare il runtime di attendere che il thread chiamante venga restituito da questo 
 `true` callback; `false` per indicare che il blocco non influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="7cb6e-110">[in] `pILHeader` Puntatore al primo byte dell'intestazione IL del metodo.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="7cb6e-111">[in] `cbILHeader` Numero di byte nell'intestazione IL.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="7cb6e-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7cb6e-112">Remarks</span></span>  

<span data-ttu-id="7cb6e-113">Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="7cb6e-114">Sono inclusi vari stub IL e metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="7cb6e-115">Il suo scopo è quello di fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="7cb6e-116">`functionId`i valori non possono essere utilizzati per risolvere i relativi token di metadati, perché i metodi dinamici non hanno metadati.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="7cb6e-117">Il `pILHeader` puntatore è valido solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="7cb6e-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="7cb6e-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7cb6e-118">Requirements</span></span>  
 <span data-ttu-id="7cb6e-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cb6e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cb6e-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7cb6e-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7cb6e-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cb6e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cb6e-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7cb6e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb6e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cb6e-123">See also</span></span>

- [<span data-ttu-id="7cb6e-124">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7cb6e-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="7cb6e-125">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="7cb6e-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
