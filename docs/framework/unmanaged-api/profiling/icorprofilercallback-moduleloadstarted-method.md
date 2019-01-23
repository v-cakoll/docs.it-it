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
ms.openlocfilehash: aa5ca8871ab284d2a46e6777b226f5a9b155e566
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502469"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="727f0-102">Metodo ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="727f0-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="727f0-103">Notifica al profiler che viene viene caricato un modulo.</span><span class="sxs-lookup"><span data-stu-id="727f0-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="727f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="727f0-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="727f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="727f0-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="727f0-106">[in] L'ID del modulo in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="727f0-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="727f0-107">Note</span><span class="sxs-lookup"><span data-stu-id="727f0-107">Remarks</span></span>  
 <span data-ttu-id="727f0-108">Il valore di `moduleId` non è valido per una richiesta di informazioni finché non la [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="727f0-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="727f0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="727f0-109">Requirements</span></span>  
 <span data-ttu-id="727f0-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="727f0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="727f0-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="727f0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="727f0-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="727f0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="727f0-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="727f0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727f0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="727f0-114">See also</span></span>
- [<span data-ttu-id="727f0-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="727f0-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
