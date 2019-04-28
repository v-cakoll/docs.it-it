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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f613842c12b50b8a58aac1b71bf2f3c53aaf961f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914485"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="e30e7-102">Metodo ICorProfilerCallback2::GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="e30e7-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="e30e7-103">Notifica al profiler che operazioni di garbage collection è stata completata e tutte le richiamate di garbage collection rilasciate appositamente.</span><span class="sxs-lookup"><span data-stu-id="e30e7-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e30e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e30e7-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e30e7-105">Note</span><span class="sxs-lookup"><span data-stu-id="e30e7-105">Remarks</span></span>  
 <span data-ttu-id="e30e7-106">È sicuro per il profiler controllare gli oggetti nelle rispettive posizioni finali quando il `GarbageCollectionFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="e30e7-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e30e7-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e30e7-107">Requirements</span></span>  
 <span data-ttu-id="e30e7-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e30e7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e30e7-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e30e7-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e30e7-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e30e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e30e7-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e30e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30e7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e30e7-112">See also</span></span>

- [<span data-ttu-id="e30e7-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e30e7-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e30e7-114">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="e30e7-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
