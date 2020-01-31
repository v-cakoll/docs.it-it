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
ms.openlocfilehash: ad9c5445cbef0be7919570db64b027556d923752
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865571"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="56788-102">Interfaccia ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="56788-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="56788-103">Fornisce metodi di callback utilizzati dal Common Language Runtime (CLR) per comunicare le informazioni sullo stato di collegamento e scollegamento al profiler.</span><span class="sxs-lookup"><span data-stu-id="56788-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56788-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="56788-104">Methods</span></span>  
  
|<span data-ttu-id="56788-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="56788-105">Method</span></span>|<span data-ttu-id="56788-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56788-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56788-107">Metodo InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="56788-107">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="56788-108">Chiamato da CLR per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="56788-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="56788-109">Metodo ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="56788-109">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="56788-110">Chiamato da CLR per indicare che il profiler può ora chiamare i metodi di recupero.</span><span class="sxs-lookup"><span data-stu-id="56788-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="56788-111">Metodo ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="56788-111">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="56788-112">Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="56788-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56788-113">Note</span><span class="sxs-lookup"><span data-stu-id="56788-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56788-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="56788-114">Requirements</span></span>  
 <span data-ttu-id="56788-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56788-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56788-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56788-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56788-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56788-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56788-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56788-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56788-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56788-119">See also</span></span>

- [<span data-ttu-id="56788-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="56788-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="56788-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="56788-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="56788-122">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="56788-122">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="56788-123">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="56788-123">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
