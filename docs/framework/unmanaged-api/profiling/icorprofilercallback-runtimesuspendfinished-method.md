---
title: Metodo ICorProfilerCallback::RuntimeSuspendFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07e2ebe8afe6002dee6c45f56fa1f11a4083d6bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145600"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="43f88-102">Metodo ICorProfilerCallback::RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="43f88-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="43f88-103">Notifica al profiler che il runtime è stata completata la sospensione di tutti i thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="43f88-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43f88-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="43f88-105">Note</span><span class="sxs-lookup"><span data-stu-id="43f88-105">Remarks</span></span>  
 <span data-ttu-id="43f88-106">Sono consentiti tutti i thread di runtime in codice non gestito per continuare l'esecuzione fino a quando non tentano di immettere nuovamente la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="43f88-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="43f88-107">A questo punto si verranno inoltre sospese fino a quando il runtime riprende.</span><span class="sxs-lookup"><span data-stu-id="43f88-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="43f88-108">Questo vale anche per nuovi thread che accedono al runtime.</span><span class="sxs-lookup"><span data-stu-id="43f88-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="43f88-109">Tutti i thread nel runtime vengono che sospesi immediatamente se sono già nel codice che possono essere interrotte, o gli viene chiesto sospese quando raggiungono codice.</span><span class="sxs-lookup"><span data-stu-id="43f88-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="43f88-110">Il `RuntimeSuspendFinished` callback è garantito che si verifichi sullo stesso thread le [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="43f88-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43f88-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43f88-111">Requirements</span></span>  
 <span data-ttu-id="43f88-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43f88-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43f88-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43f88-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43f88-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43f88-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="43f88-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="43f88-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43f88-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43f88-116">See also</span></span>

- [<span data-ttu-id="43f88-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="43f88-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="43f88-118">Metodo RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="43f88-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
