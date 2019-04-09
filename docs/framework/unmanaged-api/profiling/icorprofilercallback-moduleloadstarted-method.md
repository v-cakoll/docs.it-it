---
title: Metodo ICorProfilerCallback::ModuleLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3503aa1eb86246365e31f52313893ad8713f5748
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153686"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="d2895-102">Metodo ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="d2895-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="d2895-103">Notifica al profiler che viene viene caricato un modulo.</span><span class="sxs-lookup"><span data-stu-id="d2895-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2895-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2895-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2895-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2895-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d2895-106">[in] L'ID del modulo in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="d2895-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2895-107">Note</span><span class="sxs-lookup"><span data-stu-id="d2895-107">Remarks</span></span>  
 <span data-ttu-id="d2895-108">Il valore di `moduleId` non è valido per una richiesta di informazioni finché non la [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="d2895-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2895-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2895-109">Requirements</span></span>  
 <span data-ttu-id="d2895-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2895-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2895-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2895-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2895-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2895-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d2895-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d2895-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2895-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2895-114">See also</span></span>

- [<span data-ttu-id="d2895-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d2895-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
