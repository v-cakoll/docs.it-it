---
title: Metodo ICorProfilerCallback::RuntimeSuspendFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6127d0c5f3b193dad1586cdaf92beb8d8734376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="a311c-102">Metodo ICorProfilerCallback::RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="a311c-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="a311c-103">Notifica al profiler che il runtime è stata completata la sospensione di tutti i thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="a311c-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a311c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a311c-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a311c-105">Note</span><span class="sxs-lookup"><span data-stu-id="a311c-105">Remarks</span></span>  
 <span data-ttu-id="a311c-106">Per continuare l'esecuzione finché non si tenta di immettere nuovamente il runtime, sono consentiti tutti i thread di runtime nel codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="a311c-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="a311c-107">A questo punto si verrà inoltre sospeso fino a quando il runtime riprende.</span><span class="sxs-lookup"><span data-stu-id="a311c-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="a311c-108">Questo vale anche per i nuovi thread che accedono al runtime.</span><span class="sxs-lookup"><span data-stu-id="a311c-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="a311c-109">Tutti i thread nel runtime vengono che sospesi immediatamente se si trovano già nel codice che possono essere interrotte o gli viene chiesto di sospendere l'esecuzione quando raggiungono codice.</span><span class="sxs-lookup"><span data-stu-id="a311c-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="a311c-110">Il `RuntimeSuspendFinished` è garantito che si verifichi sullo stesso thread del callback di [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="a311c-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a311c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a311c-111">Requirements</span></span>  
 <span data-ttu-id="a311c-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a311c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a311c-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a311c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a311c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a311c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a311c-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a311c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a311c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a311c-116">See Also</span></span>  
 [<span data-ttu-id="a311c-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a311c-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a311c-118">Metodo RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="a311c-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
