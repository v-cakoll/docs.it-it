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
ms.openlocfilehash: 38d9e83e9fa0e9cd0586fb10a6fd79c29bead4a6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866104"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="41359-102">Metodo ICorProfilerCallback::ObjectAllocated</span><span class="sxs-lookup"><span data-stu-id="41359-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="41359-103">Notifica al profiler che la memoria all'interno dell'heap è stata allocata per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="41359-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41359-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41359-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41359-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41359-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="41359-106">in ID dell'oggetto per cui è stata allocata la memoria.</span><span class="sxs-lookup"><span data-stu-id="41359-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="41359-107">in ID della classe di cui l'oggetto è un'istanza.</span><span class="sxs-lookup"><span data-stu-id="41359-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41359-108">Note</span><span class="sxs-lookup"><span data-stu-id="41359-108">Remarks</span></span>  
 <span data-ttu-id="41359-109">Il metodo `ObjectedAllocated` non viene chiamato per le allocazioni dallo stack o dalla memoria non gestita.</span><span class="sxs-lookup"><span data-stu-id="41359-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="41359-110">Il parametro `classId` può fare riferimento a una classe nel codice gestito che non è ancora stata caricata.</span><span class="sxs-lookup"><span data-stu-id="41359-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="41359-111">Il profiler riceverà un callback di caricamento della classe per la classe immediatamente successiva al callback `ObjectAllocated`.</span><span class="sxs-lookup"><span data-stu-id="41359-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41359-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="41359-112">Requirements</span></span>  
 <span data-ttu-id="41359-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41359-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41359-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41359-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41359-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41359-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41359-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41359-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41359-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41359-117">See also</span></span>

- [<span data-ttu-id="41359-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="41359-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="41359-119">Metodo ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="41359-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="41359-120">Metodo ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="41359-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
