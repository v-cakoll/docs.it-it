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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231097"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="2d00c-102">Metodo ICorProfilerCallback2::GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="2d00c-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="2d00c-103">Notifica al profiler che operazioni di garbage collection è stata completata e tutte le richiamate di garbage collection rilasciate appositamente.</span><span class="sxs-lookup"><span data-stu-id="2d00c-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d00c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d00c-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2d00c-105">Note</span><span class="sxs-lookup"><span data-stu-id="2d00c-105">Remarks</span></span>  
 <span data-ttu-id="2d00c-106">È sicuro per il profiler controllare gli oggetti nelle rispettive posizioni finali quando il `GarbageCollectionFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="2d00c-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d00c-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d00c-107">Requirements</span></span>  
 <span data-ttu-id="2d00c-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d00c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d00c-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d00c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d00c-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d00c-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2d00c-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2d00c-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d00c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d00c-112">See also</span></span>

- [<span data-ttu-id="2d00c-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2d00c-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2d00c-114">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="2d00c-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
