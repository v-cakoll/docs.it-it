---
title: Interfaccia ICorProfilerCallback3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3
helpviewer_keywords: ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1419dfff7005b33fd1f8a545d168a410e7a88a76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="3ab65-102">Interfaccia ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="3ab65-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="3ab65-103">Fornisce metodi di callback usato da common language runtime (CLR) per comunicare collegamento e scollegamento di informazioni sullo stato per il profiler.</span><span class="sxs-lookup"><span data-stu-id="3ab65-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ab65-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3ab65-104">Methods</span></span>  
  
|<span data-ttu-id="3ab65-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3ab65-105">Method</span></span>|<span data-ttu-id="3ab65-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ab65-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ab65-107">Metodo InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="3ab65-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="3ab65-108">Chiamato da CLR per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di collegamento.</span><span class="sxs-lookup"><span data-stu-id="3ab65-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="3ab65-109">Metodo ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="3ab65-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="3ab65-110">Chiamato da CLR per indicare che il profiler può chiamare i metodi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3ab65-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="3ab65-111">Metodo ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="3ab65-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="3ab65-112">Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="3ab65-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ab65-113">Note</span><span class="sxs-lookup"><span data-stu-id="3ab65-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ab65-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ab65-114">Requirements</span></span>  
 <span data-ttu-id="3ab65-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ab65-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ab65-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ab65-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ab65-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ab65-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ab65-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ab65-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab65-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ab65-119">See Also</span></span>  
 [<span data-ttu-id="3ab65-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="3ab65-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="3ab65-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3ab65-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="3ab65-122">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="3ab65-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="3ab65-123">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="3ab65-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
