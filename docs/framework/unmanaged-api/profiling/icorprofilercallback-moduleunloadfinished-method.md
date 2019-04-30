---
title: Metodo ICorProfilerCallback::ModuleUnloadFinished
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f096c1f3898348141e13da44f39f2768417acd1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042082"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="ffeb6-102">Metodo ICorProfilerCallback::ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="ffeb6-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="ffeb6-103">Notifica al profiler che un modulo è terminato lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffeb6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffeb6-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffeb6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ffeb6-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ffeb6-106">[in] L'ID del modulo che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ffeb6-107">[in] HRESULT che indica se il modulo è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffeb6-108">Note</span><span class="sxs-lookup"><span data-stu-id="ffeb6-108">Remarks</span></span>  
 <span data-ttu-id="ffeb6-109">Il valore di `moduleId` non è valido per una richiesta di informazioni dopo che il [ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="ffeb6-110">Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ModuleUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="ffeb6-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ffeb6-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento del modulo ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ffeb6-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffeb6-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffeb6-113">Requirements</span></span>  
 <span data-ttu-id="ffeb6-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffeb6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffeb6-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ffeb6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ffeb6-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffeb6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffeb6-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffeb6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffeb6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffeb6-118">See also</span></span>

- [<span data-ttu-id="ffeb6-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ffeb6-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
