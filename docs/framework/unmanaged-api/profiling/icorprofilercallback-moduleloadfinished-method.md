---
title: Metodo ICorProfilerCallback::ModuleLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 354d2f278bcb0618b823b7300079278fc4c3315c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758483"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="a84fb-102">Metodo ICorProfilerCallback::ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="a84fb-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="a84fb-103">Notifica al profiler che un modulo ha terminato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="a84fb-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a84fb-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a84fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a84fb-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a84fb-106">[in] L'ID del modulo che ha completato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="a84fb-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a84fb-107">[in] HRESULT che indica se il modulo è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a84fb-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a84fb-108">Note</span><span class="sxs-lookup"><span data-stu-id="a84fb-108">Remarks</span></span>  
 <span data-ttu-id="a84fb-109">Il valore di `moduleId` non è valido per una richiesta di informazioni finché non la `ModuleLoadFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="a84fb-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="a84fb-110">Alcune parti del caricamento del modulo potrebbero continuare dopo il `ModuleLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="a84fb-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="a84fb-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="a84fb-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a84fb-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte del caricamento del modulo ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a84fb-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a84fb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a84fb-113">Requirements</span></span>  
 <span data-ttu-id="a84fb-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a84fb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a84fb-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a84fb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a84fb-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a84fb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a84fb-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a84fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84fb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a84fb-118">See also</span></span>

- [<span data-ttu-id="a84fb-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a84fb-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a84fb-120">Metodo ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="a84fb-120">ModuleLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
