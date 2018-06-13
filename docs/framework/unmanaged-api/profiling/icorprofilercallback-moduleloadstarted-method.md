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
ms.openlocfilehash: e9d6c322d82b34af908065106ef03ccf5ff846e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451730"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="c1ce4-102">Metodo ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="c1ce4-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="c1ce4-103">Notifica al profiler che un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="c1ce4-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ce4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1ce4-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1ce4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1ce4-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c1ce4-106">[in] L'ID del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="c1ce4-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1ce4-107">Note</span><span class="sxs-lookup"><span data-stu-id="c1ce4-107">Remarks</span></span>  
 <span data-ttu-id="c1ce4-108">Il valore di `moduleId` non è valido per una richiesta di informazioni fino a quando il [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="c1ce4-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ce4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1ce4-109">Requirements</span></span>  
 <span data-ttu-id="c1ce4-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ce4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ce4-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1ce4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1ce4-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c1ce4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1ce4-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ce4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ce4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1ce4-114">See Also</span></span>  
 [<span data-ttu-id="c1ce4-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c1ce4-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
