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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d5ea547066663564d76008434884b6e34150efb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779329"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="7ffd9-102">Metodo ICorProfilerCallback2::HandleCreated</span><span class="sxs-lookup"><span data-stu-id="7ffd9-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="7ffd9-103">Notifica al profiler di codice che è stato creato l'handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7ffd9-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ffd9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ffd9-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ffd9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ffd9-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="7ffd9-106">[in] L'ID dell'handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7ffd9-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="7ffd9-107">[in] L'ID dell'oggetto per cui è stato creato l'handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7ffd9-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ffd9-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ffd9-108">Requirements</span></span>  
 <span data-ttu-id="7ffd9-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ffd9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ffd9-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ffd9-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ffd9-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ffd9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ffd9-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ffd9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ffd9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ffd9-113">See also</span></span>

- [<span data-ttu-id="7ffd9-114">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7ffd9-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7ffd9-115">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="7ffd9-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
