---
title: Metodo ICorProfilerCallback3::ProfilerDetachSucceeded
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
ms.openlocfilehash: b96a8930c24275546b0aac9fa650cf5447ef4ef2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865415"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="846d2-102">Metodo ICorProfilerCallback3::ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="846d2-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="846d2-103">Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="846d2-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="846d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="846d2-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="846d2-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="846d2-105">Return Value</span></span>  
 <span data-ttu-id="846d2-106">Il valore restituito da questo callback viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="846d2-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="846d2-107">Note</span><span class="sxs-lookup"><span data-stu-id="846d2-107">Remarks</span></span>  
 <span data-ttu-id="846d2-108">Il callback `ProfilerDetachSucceeded` viene generato dopo che tutti i thread sono usciti dal codice del profiler.</span><span class="sxs-lookup"><span data-stu-id="846d2-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="846d2-109">Quando viene chiamato questo metodo, il profiler deve eseguire un'attività dell'ultimo minuto non appropriata per il distruttore, ad esempio inviare una notifica all'interfaccia utente o registrare un componente.</span><span class="sxs-lookup"><span data-stu-id="846d2-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="846d2-110">Tuttavia, il profiler non deve chiamare funzioni sulle interfacce fornite da CLR durante questo callback (ad esempio, le interfacce [ICorProfilerInfo](icorprofilerinfo-interface.md) o `IMetaData*`).</span><span class="sxs-lookup"><span data-stu-id="846d2-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="846d2-111">CLR crea una voce nel registro eventi applicazioni Windows per indicare che l'operazione di rimozione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="846d2-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="846d2-112">Dopo che il profiler viene restituito da questo callback, CLR rilascia l'oggetto del profiler e scarica la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="846d2-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="846d2-113">Il profiler quindi non deve eseguire azioni che provocherebbero l'esecuzione nella DLL del profiler dopo essere stato restituito da questo callback.</span><span class="sxs-lookup"><span data-stu-id="846d2-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="846d2-114">Ad esempio, non deve creare thread o registrare callback del timer.</span><span class="sxs-lookup"><span data-stu-id="846d2-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="846d2-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="846d2-115">Requirements</span></span>  
 <span data-ttu-id="846d2-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="846d2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="846d2-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="846d2-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="846d2-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="846d2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="846d2-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="846d2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="846d2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="846d2-120">See also</span></span>

- [<span data-ttu-id="846d2-121">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="846d2-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="846d2-122">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="846d2-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="846d2-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="846d2-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="846d2-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="846d2-124">Profiling</span></span>](index.md)
