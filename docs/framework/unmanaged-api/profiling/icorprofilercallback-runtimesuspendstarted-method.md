---
title: Metodo ICorProfilerCallback::RuntimeSuspendStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 358536aa51dfef2d079813b34eddbd1b01294bcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="f6569-102">Metodo ICorProfilerCallback::RuntimeSuspendStarted</span><span class="sxs-lookup"><span data-stu-id="f6569-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="f6569-103">Notifica al profiler che il runtime sta per sospendere tutti i thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="f6569-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6569-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6569-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6569-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6569-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="f6569-106">[in] Il valore di [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumerazione che indica il motivo della sospensione.</span><span class="sxs-lookup"><span data-stu-id="f6569-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6569-107">Note</span><span class="sxs-lookup"><span data-stu-id="f6569-107">Remarks</span></span>  
 <span data-ttu-id="f6569-108">Per continuare l'esecuzione finché non si tenta di immettere nuovamente il runtime, sono consentiti tutti i thread di runtime nel codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="f6569-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="f6569-109">A questo punto si verrà inoltre sospeso fino a quando il runtime riprende.</span><span class="sxs-lookup"><span data-stu-id="f6569-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="f6569-110">Questo vale anche per i nuovi thread che accedono al runtime.</span><span class="sxs-lookup"><span data-stu-id="f6569-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="f6569-111">Tutti i thread nel runtime vengono che sospesi immediatamente se si trovano già nel codice che possono essere interrotte o gli viene chiesto di sospendere l'esecuzione quando raggiungono codice.</span><span class="sxs-lookup"><span data-stu-id="f6569-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6569-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6569-112">Requirements</span></span>  
 <span data-ttu-id="f6569-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6569-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6569-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6569-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6569-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6569-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6569-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6569-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6569-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6569-117">See Also</span></span>  
 [<span data-ttu-id="f6569-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f6569-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f6569-119">RuntimeSuspendAborted (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6569-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [<span data-ttu-id="f6569-120">RuntimeSuspendFinished (metodo)</span><span class="sxs-lookup"><span data-stu-id="f6569-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
