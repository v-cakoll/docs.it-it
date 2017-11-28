---
title: Metodo ICorProfilerCallback::ClassUnloadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 920fa36edcc49c12f8f73644cc4e6551a0e954ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="1f0c1-102">Metodo ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="1f0c1-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="1f0c1-103">Notifica al profiler che una classe è terminato lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="1f0c1-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f0c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f0c1-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f0c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1f0c1-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1f0c1-106">[in] Identifica la classe che è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="1f0c1-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="1f0c1-107">[in] Un valore HRESULT che indica se la classe è stata scaricata correttamente.</span><span class="sxs-lookup"><span data-stu-id="1f0c1-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f0c1-108">Note</span><span class="sxs-lookup"><span data-stu-id="1f0c1-108">Remarks</span></span>  
 <span data-ttu-id="1f0c1-109">Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ClassUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="1f0c1-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="1f0c1-110">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="1f0c1-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="1f0c1-111">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento della classe ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1f0c1-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f0c1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f0c1-112">Requirements</span></span>  
 <span data-ttu-id="1f0c1-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f0c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f0c1-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f0c1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1f0c1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f0c1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f0c1-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f0c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0c1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f0c1-117">See Also</span></span>  
 [<span data-ttu-id="1f0c1-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1f0c1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="1f0c1-119">ClassUnloadStarted (metodo)</span><span class="sxs-lookup"><span data-stu-id="1f0c1-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
