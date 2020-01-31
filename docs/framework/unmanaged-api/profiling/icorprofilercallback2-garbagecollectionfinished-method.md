---
title: Metodo ICorProfilerCallback2::GarbageCollectionFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
ms.openlocfilehash: 30f2e675532848c2dbb1f055a0f1489cf3b2baa1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865792"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="0e59b-102">Metodo ICorProfilerCallback2::GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="0e59b-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="0e59b-103">Notifica al profiler che Garbage Collection è stato completato e che sono stati rilasciati tutti i callback di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0e59b-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e59b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e59b-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e59b-105">Note</span><span class="sxs-lookup"><span data-stu-id="0e59b-105">Remarks</span></span>  
 <span data-ttu-id="0e59b-106">Il profiler può ispezionare gli oggetti nelle posizioni finali quando viene chiamato il metodo `GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="0e59b-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e59b-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0e59b-107">Requirements</span></span>  
 <span data-ttu-id="0e59b-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e59b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e59b-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e59b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e59b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e59b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e59b-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e59b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e59b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e59b-112">See also</span></span>

- [<span data-ttu-id="0e59b-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0e59b-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0e59b-114">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="0e59b-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
