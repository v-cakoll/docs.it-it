---
title: Interfaccia ICorProfilerCallback3
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: db07e2afa64ea2bf80416e6ab8cba5a4dcdc8dcf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499675"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="6abb8-102">Interfaccia ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="6abb8-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="6abb8-103">Fornisce metodi di callback utilizzati dal Common Language Runtime (CLR) per comunicare le informazioni sullo stato di collegamento e scollegamento al profiler.</span><span class="sxs-lookup"><span data-stu-id="6abb8-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6abb8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6abb8-104">Methods</span></span>  
  
|<span data-ttu-id="6abb8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6abb8-105">Method</span></span>|<span data-ttu-id="6abb8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6abb8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6abb8-107">Metodo InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="6abb8-107">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="6abb8-108">Chiamato da CLR per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="6abb8-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="6abb8-109">Metodo ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="6abb8-109">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="6abb8-110">Chiamato da CLR per indicare che il profiler può ora chiamare i metodi di recupero.</span><span class="sxs-lookup"><span data-stu-id="6abb8-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="6abb8-111">Metodo ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="6abb8-111">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="6abb8-112">Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="6abb8-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6abb8-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6abb8-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6abb8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6abb8-114">Requirements</span></span>  
 <span data-ttu-id="6abb8-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6abb8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6abb8-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6abb8-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6abb8-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6abb8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6abb8-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6abb8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6abb8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6abb8-119">See also</span></span>

- [<span data-ttu-id="6abb8-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="6abb8-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6abb8-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6abb8-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6abb8-122">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="6abb8-122">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="6abb8-123">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="6abb8-123">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
