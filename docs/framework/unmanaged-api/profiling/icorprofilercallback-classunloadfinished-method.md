---
title: Metodo ICorProfilerCallback::ClassUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d01f3d7485b19c076d9cd3e83aeccbcf5e728f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160706"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="cbd1a-102">Metodo ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="cbd1a-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="cbd1a-103">Notifica al profiler che ha terminato lo scaricamento di una classe.</span><span class="sxs-lookup"><span data-stu-id="cbd1a-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd1a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbd1a-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbd1a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbd1a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="cbd1a-106">[in] Identifica la classe che è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="cbd1a-106">[in] Identifies the class that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="cbd1a-107">[in] HRESULT che indica se la classe è stata scaricata correttamente.</span><span class="sxs-lookup"><span data-stu-id="cbd1a-107">[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbd1a-108">Note</span><span class="sxs-lookup"><span data-stu-id="cbd1a-108">Remarks</span></span>  
 <span data-ttu-id="cbd1a-109">Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ClassUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="cbd1a-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="cbd1a-110">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="cbd1a-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="cbd1a-111">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento della classe ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cbd1a-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbd1a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbd1a-112">Requirements</span></span>  
 <span data-ttu-id="cbd1a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbd1a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbd1a-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cbd1a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cbd1a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbd1a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbd1a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbd1a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd1a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbd1a-117">See also</span></span>

- [<span data-ttu-id="cbd1a-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cbd1a-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cbd1a-119">Metodo ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="cbd1a-119">ClassUnloadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
