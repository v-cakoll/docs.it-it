---
title: Metodo ICorProfilerCallback::ModuleUnloadStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 384d655254cc79283f93ff2e608b0429c4a84ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="7f0b9-102">Metodo ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="7f0b9-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="7f0b9-103">Notifica al profiler che sta per essere scaricato un modulo.</span><span class="sxs-lookup"><span data-stu-id="7f0b9-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f0b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f0b9-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f0b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f0b9-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="7f0b9-106">[in] L'ID del modulo che sta per essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="7f0b9-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f0b9-107">Note</span><span class="sxs-lookup"><span data-stu-id="7f0b9-107">Remarks</span></span>  
 <span data-ttu-id="7f0b9-108">Il valore di `moduleId` non è valido per una richiesta di informazioni dopo il `ModuleUnloadStarted` metodo restituisce, si tratta di completamento per ottenere informazioni su questo modulo.</span><span class="sxs-lookup"><span data-stu-id="7f0b9-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f0b9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f0b9-109">Requirements</span></span>  
 <span data-ttu-id="7f0b9-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f0b9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f0b9-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f0b9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f0b9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f0b9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f0b9-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f0b9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f0b9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f0b9-114">See Also</span></span>  
 [<span data-ttu-id="7f0b9-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7f0b9-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="7f0b9-116">Metodo ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="7f0b9-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
