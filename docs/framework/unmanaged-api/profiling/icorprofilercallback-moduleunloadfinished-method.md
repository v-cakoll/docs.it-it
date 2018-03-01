---
title: Metodo ICorProfilerCallback::ModuleUnloadFinished
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
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6f9f048d60d2d463e3d846fadda91932a9a2a091
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="929d7-102">Metodo ICorProfilerCallback::ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="929d7-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="929d7-103">Notifica al profiler che un modulo è terminato lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="929d7-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="929d7-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="929d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="929d7-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="929d7-106">[in] L'ID del modulo che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="929d7-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="929d7-107">[in] Un valore HRESULT che indica se il modulo è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="929d7-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="929d7-108">Note</span><span class="sxs-lookup"><span data-stu-id="929d7-108">Remarks</span></span>  
 <span data-ttu-id="929d7-109">Il valore di `moduleId` non è valido per una richiesta di informazioni dopo il [ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) metodo restituisce.</span><span class="sxs-lookup"><span data-stu-id="929d7-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="929d7-110">Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ModuleUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="929d7-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="929d7-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="929d7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="929d7-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento del modulo ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="929d7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929d7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="929d7-113">Requirements</span></span>  
 <span data-ttu-id="929d7-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="929d7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929d7-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="929d7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="929d7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="929d7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="929d7-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="929d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929d7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="929d7-118">See Also</span></span>  
 [<span data-ttu-id="929d7-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="929d7-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
