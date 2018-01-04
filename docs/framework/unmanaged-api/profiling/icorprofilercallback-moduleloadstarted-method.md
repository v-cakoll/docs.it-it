---
title: Metodo ICorProfilerCallback::ModuleLoadStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09f88b2a287eef0bf3fe8edeba4b76a3b3a1ce4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="74bcf-102">Metodo ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="74bcf-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="74bcf-103">Notifica al profiler che un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="74bcf-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74bcf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74bcf-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74bcf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74bcf-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="74bcf-106">[in] L'ID del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="74bcf-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74bcf-107">Note</span><span class="sxs-lookup"><span data-stu-id="74bcf-107">Remarks</span></span>  
 <span data-ttu-id="74bcf-108">Il valore di `moduleId` non è valido per una richiesta di informazioni fino a quando il [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="74bcf-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74bcf-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74bcf-109">Requirements</span></span>  
 <span data-ttu-id="74bcf-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74bcf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74bcf-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74bcf-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74bcf-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74bcf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74bcf-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74bcf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74bcf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74bcf-114">See Also</span></span>  
 [<span data-ttu-id="74bcf-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="74bcf-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
