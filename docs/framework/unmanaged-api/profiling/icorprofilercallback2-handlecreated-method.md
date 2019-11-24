---
title: Metodo ICorProfilerCallback2::HandleCreated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
ms.openlocfilehash: 594d970dbe0a176a5ec49015e105f89ff64bdfac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439769"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="c1248-102">Metodo ICorProfilerCallback2::HandleCreated</span><span class="sxs-lookup"><span data-stu-id="c1248-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="c1248-103">Notifies the code profiler that a garbage collection handle has been created.</span><span class="sxs-lookup"><span data-stu-id="c1248-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1248-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1248-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1248-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1248-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="c1248-106">[in] The ID of the handle for the garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c1248-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="c1248-107">[in] The ID of the object for which the garbage collection handle was created.</span><span class="sxs-lookup"><span data-stu-id="c1248-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1248-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1248-108">Requirements</span></span>  
 <span data-ttu-id="c1248-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1248-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1248-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1248-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1248-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1248-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1248-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1248-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1248-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1248-113">See also</span></span>

- [<span data-ttu-id="c1248-114">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c1248-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c1248-115">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="c1248-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
