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
ms.openlocfilehash: c4b8bffeb71497a7dd8e2ed25b833f9216d8017e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142246"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="f16b7-102">Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f16b7-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="f16b7-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="f16b7-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="f16b7-104">Notifica al profiler ogni volta che è stata avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="f16b7-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f16b7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f16b7-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f16b7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f16b7-106">Parameters</span></span>  
<span data-ttu-id="f16b7-107">[in]</span><span class="sxs-lookup"><span data-stu-id="f16b7-107">[in]</span></span> `functionId`  
<span data-ttu-id="f16b7-108">L'identificatore della funzione in memoria per la quale JIT viene avviata la compilazione.</span><span class="sxs-lookup"><span data-stu-id="f16b7-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="f16b7-109">[in]</span><span class="sxs-lookup"><span data-stu-id="f16b7-109">[in]</span></span> `fIsSafeToBlock`   
`true` <span data-ttu-id="f16b7-110">per indicare che il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avrà effetto il funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="f16b7-110">to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="f16b7-111">[in]</span><span class="sxs-lookup"><span data-stu-id="f16b7-111">[in]</span></span> `pILHeader`    
<span data-ttu-id="f16b7-112">Puntatore al primo byte dell'intestazione di linguaggio intermedio del metodo.</span><span class="sxs-lookup"><span data-stu-id="f16b7-112">A pointer to the first byte of the method's IL header.</span></span>   

<span data-ttu-id="f16b7-113">[in]</span><span class="sxs-lookup"><span data-stu-id="f16b7-113">[in]</span></span> `cbILHeader`    
<span data-ttu-id="f16b7-114">Il numero di byte nell'intestazione del linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="f16b7-114">The number of bytes in the IL header.</span></span> 

## <a name="remarks"></a><span data-ttu-id="f16b7-115">Note</span><span class="sxs-lookup"><span data-stu-id="f16b7-115">Remarks</span></span>  

<span data-ttu-id="f16b7-116">Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="f16b7-116">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="f16b7-117">Sono inclusi vari stub a livello di integrità e i metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="f16b7-117">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="f16b7-118">L'obiettivo consiste nel fornire gli autori di profiler con le informazioni necessarie per identificare il metodo compilato per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f16b7-118">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> `functionId` <span data-ttu-id="f16b7-119">valori non possono essere usati per risolvere i relativi token di metadati, perché i metadati non dispongono di metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="f16b7-119">values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="f16b7-120">Il `pILHeader` puntatore è valido solo durante il callback.</span><span class="sxs-lookup"><span data-stu-id="f16b7-120">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="f16b7-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f16b7-121">Requirements</span></span>  
 <span data-ttu-id="f16b7-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f16b7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f16b7-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f16b7-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f16b7-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f16b7-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f16b7-125">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f16b7-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f16b7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f16b7-126">See also</span></span>

- [<span data-ttu-id="f16b7-127">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="f16b7-127">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="f16b7-128">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="f16b7-128">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
