---
title: Metodo ICorProfilerCallback::ObjectAllocated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 9a402b7dfc3ece9d38994ed897162fe0d81ff0b9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503302"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="ace93-102">Metodo ICorProfilerCallback::ObjectAllocated</span><span class="sxs-lookup"><span data-stu-id="ace93-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="ace93-103">Notifica al profiler che la memoria all'interno dell'heap è stata allocata per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ace93-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace93-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ace93-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ace93-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ace93-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="ace93-106">in ID dell'oggetto per cui è stata allocata la memoria.</span><span class="sxs-lookup"><span data-stu-id="ace93-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="ace93-107">in ID della classe di cui l'oggetto è un'istanza.</span><span class="sxs-lookup"><span data-stu-id="ace93-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ace93-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ace93-108">Remarks</span></span>  
 <span data-ttu-id="ace93-109">Il `ObjectedAllocated` metodo non viene chiamato per le allocazioni dallo stack o dalla memoria non gestita.</span><span class="sxs-lookup"><span data-stu-id="ace93-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="ace93-110">Il `classId` parametro può fare riferimento a una classe nel codice gestito che non è ancora stata caricata.</span><span class="sxs-lookup"><span data-stu-id="ace93-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="ace93-111">Il profiler riceverà un callback di caricamento della classe per la classe immediatamente successiva al `ObjectAllocated` callback.</span><span class="sxs-lookup"><span data-stu-id="ace93-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ace93-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ace93-112">Requirements</span></span>  
 <span data-ttu-id="ace93-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ace93-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ace93-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ace93-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ace93-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ace93-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ace93-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ace93-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace93-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ace93-117">See also</span></span>

- [<span data-ttu-id="ace93-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ace93-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ace93-119">Metodo ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="ace93-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="ace93-120">Metodo ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="ace93-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
