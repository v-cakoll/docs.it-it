---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 170d0b20069724a4e1845be0250b2897daa10dee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501240"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="f2ce0-102">Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f2ce0-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="f2ce0-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="f2ce0-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="f2ce0-104">Notifica al profiler ogni volta che è stata avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ce0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2ce0-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2ce0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2ce0-106">Parameters</span></span>  
<span data-ttu-id="f2ce0-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="f2ce0-107">[in] `functionId`</span></span>  
<span data-ttu-id="f2ce0-108">L'identificatore della funzione in memoria per la quale JIT viene avviata la compilazione.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="f2ce0-109">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="f2ce0-109">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="f2ce0-110">`true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avrà effetto il funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-110">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="f2ce0-111">[in] `pILHeader`  </span><span class="sxs-lookup"><span data-stu-id="f2ce0-111">[in] `pILHeader`  </span></span>  
<span data-ttu-id="f2ce0-112">Puntatore al primo byte dell'intestazione di linguaggio intermedio del metodo.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="f2ce0-113">[in] `cbILHeader`  </span><span class="sxs-lookup"><span data-stu-id="f2ce0-113">[in] `cbILHeader`  </span></span>  
<span data-ttu-id="f2ce0-114">Il numero di byte nell'intestazione del linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="f2ce0-115">Note</span><span class="sxs-lookup"><span data-stu-id="f2ce0-115">Remarks</span></span>  

<span data-ttu-id="f2ce0-116">Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="f2ce0-117">Sono inclusi vari stub a livello di integrità e i metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="f2ce0-118">L'obiettivo consiste nel fornire gli autori di profiler con le informazioni necessarie per identificare il metodo compilato per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="f2ce0-119">`functionId` valori non possono essere usati per risolvere i relativi token di metadati, perché i metadati non dispongono di metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-119">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="f2ce0-120">Il `pILHeader` puntatore è valido solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="f2ce0-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="f2ce0-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2ce0-121">Requirements</span></span>  
 <span data-ttu-id="f2ce0-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ce0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ce0-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2ce0-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2ce0-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ce0-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ce0-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ce0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ce0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2ce0-126">See also</span></span>
- [<span data-ttu-id="f2ce0-127">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="f2ce0-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="f2ce0-128">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="f2ce0-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
