---
title: Metodo ICorProfilerCallback::ModuleUnloadStarted
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c99ddc66cca0a0d0083cfa19cfca34a1e557d4e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769154"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="964d2-102">Metodo ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="964d2-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="964d2-103">Notifica al profiler che un modulo verrà scaricato.</span><span class="sxs-lookup"><span data-stu-id="964d2-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="964d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="964d2-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="964d2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="964d2-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="964d2-106">[in] L'ID del modulo che sta per essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="964d2-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="964d2-107">Note</span><span class="sxs-lookup"><span data-stu-id="964d2-107">Remarks</span></span>  
 <span data-ttu-id="964d2-108">Il valore di `moduleId` non è valido per una richiesta di informazioni dopo il `ModuleUnloadStarted` restituzione del metodo, ovvero si tratta di completamento per ottenere informazioni su questo modulo.</span><span class="sxs-lookup"><span data-stu-id="964d2-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="964d2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="964d2-109">Requirements</span></span>  
 <span data-ttu-id="964d2-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="964d2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="964d2-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="964d2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="964d2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="964d2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="964d2-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="964d2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="964d2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="964d2-114">See also</span></span>

- [<span data-ttu-id="964d2-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="964d2-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="964d2-116">Metodo ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="964d2-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
