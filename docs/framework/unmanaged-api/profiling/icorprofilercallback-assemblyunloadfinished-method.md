---
title: Metodo ICorProfilerCallback::AssemblyUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a75d31f0a2c844895363bb4693dbcb5aba4cce1f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775503"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="e79a9-102">Metodo ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="e79a9-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="e79a9-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="e79a9-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e79a9-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e79a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e79a9-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="e79a9-106">[in] Identifica l'assembly che sta per essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="e79a9-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e79a9-107">[in] HRESULT che indica se l'assembly è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e79a9-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e79a9-108">Note</span><span class="sxs-lookup"><span data-stu-id="e79a9-108">Remarks</span></span>  
 <span data-ttu-id="e79a9-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo che il [AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="e79a9-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="e79a9-110">Alcune parti dello scaricamento dell'assembly potrebbero continuare dopo il `AssemblyUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="e79a9-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="e79a9-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="e79a9-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e79a9-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte di scaricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e79a9-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e79a9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e79a9-113">Requirements</span></span>  
 <span data-ttu-id="e79a9-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e79a9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e79a9-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e79a9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e79a9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e79a9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e79a9-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e79a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79a9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e79a9-118">See also</span></span>

- [<span data-ttu-id="e79a9-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e79a9-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
