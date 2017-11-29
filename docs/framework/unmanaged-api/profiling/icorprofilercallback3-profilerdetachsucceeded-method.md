---
title: Metodo ICorProfilerCallback3::ProfilerDetachSucceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4413e5c475bce6d6f2eea1f7a968c946237f47a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="575dd-102">Metodo ICorProfilerCallback3::ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="575dd-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="575dd-103">Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="575dd-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="575dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="575dd-104">Syntax</span></span>  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="575dd-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="575dd-105">Return Value</span></span>  
 <span data-ttu-id="575dd-106">Il valore restituito da questo callback viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="575dd-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="575dd-107">Note</span><span class="sxs-lookup"><span data-stu-id="575dd-107">Remarks</span></span>  
 <span data-ttu-id="575dd-108">Il callback `ProfilerDetachSucceeded` viene generato dopo che tutti i thread sono usciti dal codice del profiler.</span><span class="sxs-lookup"><span data-stu-id="575dd-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="575dd-109">Quando viene chiamato questo metodo, il profiler deve eseguire un'attività dell'ultimo minuto non appropriata per il distruttore, ad esempio inviare una notifica all'interfaccia utente o registrare un componente.</span><span class="sxs-lookup"><span data-stu-id="575dd-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="575dd-110">Tuttavia, il profiler non deve chiamare funzioni sulle interfacce fornite da CLR durante questo callback (ad esempio il [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) o `IMetaData*` interfacce).</span><span class="sxs-lookup"><span data-stu-id="575dd-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="575dd-111">CLR crea una voce nel registro eventi applicazioni Windows per indicare che l'operazione di rimozione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="575dd-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="575dd-112">Dopo che il profiler viene restituito da questo callback, CLR rilascia l'oggetto del profiler e scarica la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="575dd-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="575dd-113">Il profiler quindi non deve eseguire azioni che provocherebbero l'esecuzione nella DLL del profiler dopo essere stato restituito da questo callback.</span><span class="sxs-lookup"><span data-stu-id="575dd-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="575dd-114">Ad esempio, non deve creare thread o registrare callback del timer.</span><span class="sxs-lookup"><span data-stu-id="575dd-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="575dd-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="575dd-115">Requirements</span></span>  
 <span data-ttu-id="575dd-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="575dd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="575dd-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="575dd-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="575dd-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="575dd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="575dd-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="575dd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575dd-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="575dd-120">See Also</span></span>  
 [<span data-ttu-id="575dd-121">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="575dd-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="575dd-122">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="575dd-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="575dd-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="575dd-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="575dd-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="575dd-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
