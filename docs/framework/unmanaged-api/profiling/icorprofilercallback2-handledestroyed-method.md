---
title: Metodo ICorProfilerCallback2::HandleDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57b814f01d7da8d5b3f9e5bda7d0cf517bb870ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592315"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="89e02-102">Metodo ICorProfilerCallback2::HandleDestroyed</span><span class="sxs-lookup"><span data-stu-id="89e02-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="89e02-103">Notifica al profiler di codice che è stato eliminato un handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="89e02-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89e02-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89e02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89e02-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="89e02-106">[in] L'ID dell'handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="89e02-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e02-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89e02-107">Requirements</span></span>  
 <span data-ttu-id="89e02-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e02-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e02-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89e02-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89e02-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89e02-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89e02-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e02-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e02-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89e02-112">See also</span></span>
- [<span data-ttu-id="89e02-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="89e02-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="89e02-114">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="89e02-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
