---
title: Interfaccia ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34c358a3405262787ed495bf9d8d75462d97a71f
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380337"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="f3b43-102">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="f3b43-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="f3b43-103">Fornisce metodi che code profiler possono usare per comunicare con il common language runtime (CLR) per controllare il monitoraggio degli eventi e informazioni sulla richiesta.</span><span class="sxs-lookup"><span data-stu-id="f3b43-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="f3b43-104">.</span><span class="sxs-lookup"><span data-stu-id="f3b43-104">.</span></span> <span data-ttu-id="f3b43-105">Il `ICorProfilerInfo4` interfaccia è un'estensione di altro `ICorProfilerInfo` interfacce.</span><span class="sxs-lookup"><span data-stu-id="f3b43-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="f3b43-106">Fornisce nuovi metodi per supportare la ricompilazione just-in-time (JIT), aggiunta in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f3b43-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3b43-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="f3b43-107">Methods</span></span>  
  
|<span data-ttu-id="f3b43-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="f3b43-108">Method</span></span>|<span data-ttu-id="f3b43-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3b43-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3b43-110">Metodo EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="f3b43-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="f3b43-111">Restituisce un enumeratore per tutte le funzioni che erano in precedenza a compilazione JIT e ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="f3b43-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="f3b43-112">Metodo EnumThreads</span><span class="sxs-lookup"><span data-stu-id="f3b43-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="f3b43-113">Ottiene un enumeratore che fornisce i metodi per scorrere in sequenza la raccolta di tutti i thread gestiti nel processo profilato.</span><span class="sxs-lookup"><span data-stu-id="f3b43-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="f3b43-114">Metodo GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="f3b43-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="f3b43-115">Ottiene gli ambiti di codice nativo associati alla versione ricompilata in JIT della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="f3b43-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="f3b43-116">Metodo GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="f3b43-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="f3b43-117">Un puntatore all'istruzione di codice gestito viene eseguito il mapping alla versione ricompilata in JIT di una funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="f3b43-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="f3b43-118">Metodo GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="f3b43-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="f3b43-119">Ottiene una mappa da parte di Microsoft intermediate language (MSIL) agli offset nativi per il codice contenuto nella versione ricompilata in JIT della funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="f3b43-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="f3b43-120">Metodo GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="f3b43-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="f3b43-121">Restituisce le dimensioni di un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="f3b43-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="f3b43-122">Metodo GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="f3b43-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="f3b43-123">Restituisce una matrice di ID che identifica tutte ricompilata in JIT le versioni della funzione specificata che sono ancora allocate.</span><span class="sxs-lookup"><span data-stu-id="f3b43-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="f3b43-124">Metodo InitializeCurrentThread </span><span class="sxs-lookup"><span data-stu-id="f3b43-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="f3b43-125">Inizializza il thread corrente prima di profiler successive chiamate API sullo stesso thread, in modo tale deadlock può essere evitato.</span><span class="sxs-lookup"><span data-stu-id="f3b43-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="f3b43-126">Metodo RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="f3b43-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="f3b43-127">Richiede la ricompilazione JIT di tutte le istanze delle funzioni specificate.</span><span class="sxs-lookup"><span data-stu-id="f3b43-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="f3b43-128">Metodo RequestRevert</span><span class="sxs-lookup"><span data-stu-id="f3b43-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="f3b43-129">Ripristina tutte le istanze delle funzioni specificate alle versioni originali.</span><span class="sxs-lookup"><span data-stu-id="f3b43-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3b43-130">Note</span><span class="sxs-lookup"><span data-stu-id="f3b43-130">Remarks</span></span>  
 <span data-ttu-id="f3b43-131">CLR implementa i metodi dell'interfaccia `ICorProfilerInfo4` usando il modello a thread libero.</span><span class="sxs-lookup"><span data-stu-id="f3b43-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="f3b43-132">Ogni metodo restituisce un valore HRESULT per indicare esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="f3b43-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="f3b43-133">Per un elenco dei possibili codici restituiti, vedere il file CorError.h.</span><span class="sxs-lookup"><span data-stu-id="f3b43-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3b43-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3b43-134">Requirements</span></span>  
 <span data-ttu-id="f3b43-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3b43-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b43-136">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3b43-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3b43-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3b43-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3b43-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b43-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b43-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3b43-139">See also</span></span>

- [<span data-ttu-id="f3b43-140">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f3b43-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f3b43-141">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f3b43-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
