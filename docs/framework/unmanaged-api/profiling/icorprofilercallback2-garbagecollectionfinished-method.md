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
ms.openlocfilehash: 47f25dbb1f88dbf580b096246016cd46f2d0d89c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499826"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="eefe0-102">Metodo ICorProfilerCallback2::GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="eefe0-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="eefe0-103">Notifica al profiler che Garbage Collection è stato completato e che sono stati rilasciati tutti i callback di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="eefe0-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eefe0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eefe0-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="eefe0-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eefe0-105">Remarks</span></span>  
 <span data-ttu-id="eefe0-106">Il profiler può ispezionare gli oggetti nelle posizioni finali quando `GarbageCollectionFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="eefe0-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eefe0-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eefe0-107">Requirements</span></span>  
 <span data-ttu-id="eefe0-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eefe0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eefe0-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eefe0-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eefe0-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eefe0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eefe0-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eefe0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefe0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eefe0-112">See also</span></span>

- [<span data-ttu-id="eefe0-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="eefe0-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="eefe0-114">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="eefe0-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
