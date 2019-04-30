---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbe8d4f7050b93ffb34280be6d63367ef294ae8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049713"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a><span data-ttu-id="44a7d-102">Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="44a7d-102">ICorProfilerCallback8::DynamicMethodJITCompilationFinished Method</span></span>
<span data-ttu-id="44a7d-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="44a7d-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="44a7d-104">Notifica al profiler ogni volta che è stata completata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="44a7d-104">Notifies the profiler whenever JIT compilation of a dynamic method has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44a7d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44a7d-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44a7d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="44a7d-106">Parameters</span></span>  
<span data-ttu-id="44a7d-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="44a7d-107">[in] `functionId`</span></span>  
<span data-ttu-id="44a7d-108">L'identificatore della funzione in memoria per la quale JIT viene avviata la compilazione.</span><span class="sxs-lookup"><span data-stu-id="44a7d-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>   

<span data-ttu-id="44a7d-109">[in] `hrStatus` </span><span class="sxs-lookup"><span data-stu-id="44a7d-109">[in] `hrStatus` </span></span>  
<span data-ttu-id="44a7d-110">Un valore che indica se la compilazione JIT è riuscita.</span><span class="sxs-lookup"><span data-stu-id="44a7d-110">A value that indicates whether the JIT compilation was successful.</span></span>

<span data-ttu-id="44a7d-111">[in] `fIsSafeToBlock` </span><span class="sxs-lookup"><span data-stu-id="44a7d-111">[in] `fIsSafeToBlock` </span></span>  
<span data-ttu-id="44a7d-112">`true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avrà effetto il funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="44a7d-112">`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

## <a name="remarks"></a><span data-ttu-id="44a7d-113">Note</span><span class="sxs-lookup"><span data-stu-id="44a7d-113">Remarks</span></span>  

<span data-ttu-id="44a7d-114">Questo callback viene attivato ogni volta che ha terminato la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="44a7d-114">This callback is triggered whenever JIT compilation of a dynamic method has finished.</span></span> <span data-ttu-id="44a7d-115">Sono inclusi vari stub a livello di integrità e i metodi LCG.</span><span class="sxs-lookup"><span data-stu-id="44a7d-115">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="44a7d-116">L'obiettivo consiste nel fornire gli autori di profiler con le informazioni necessarie per identificare il metodo compilato per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="44a7d-116">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="44a7d-117">`functionId` valori non possono essere usati per risolvere i relativi token di metadati, perché i metadati non dispongono di metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="44a7d-117">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="44a7d-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44a7d-118">Requirements</span></span>  
 <span data-ttu-id="44a7d-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44a7d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44a7d-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44a7d-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44a7d-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44a7d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44a7d-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="44a7d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a7d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44a7d-123">See also</span></span>

- [<span data-ttu-id="44a7d-124">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="44a7d-124">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="44a7d-125">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="44a7d-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
