---
title: Metodo ICorProfilerCallback::ModuleLoadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleLoadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 360c14ccdd67cb7609ffe2f9c49914fdda163389
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="6a54e-102">Metodo ICorProfilerCallback::ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="6a54e-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="6a54e-103">Notifica al profiler che un modulo ha terminato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="6a54e-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a54e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a54e-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a54e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a54e-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="6a54e-106">[in] L'ID del modulo che ha terminato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="6a54e-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="6a54e-107">[in] Un valore HRESULT che indica se il modulo è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="6a54e-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a54e-108">Note</span><span class="sxs-lookup"><span data-stu-id="6a54e-108">Remarks</span></span>  
 <span data-ttu-id="6a54e-109">Il valore di `moduleId` non è valido per una richiesta di informazioni fino a quando il `ModuleLoadFinished` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="6a54e-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="6a54e-110">Alcune parti del caricamento del modulo potrebbero continuare dopo il `ModuleLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="6a54e-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="6a54e-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="6a54e-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6a54e-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte del caricamento del modulo ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6a54e-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a54e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a54e-113">Requirements</span></span>  
 <span data-ttu-id="6a54e-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a54e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a54e-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a54e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a54e-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a54e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a54e-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a54e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a54e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a54e-118">See Also</span></span>  
 [<span data-ttu-id="6a54e-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6a54e-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="6a54e-120">Metodo ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="6a54e-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
