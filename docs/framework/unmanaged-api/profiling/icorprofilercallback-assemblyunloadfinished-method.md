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
ms.openlocfilehash: b9ee87c926d2377ff8eef53f930fe75251b28ceb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137774"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="c2974-102">Metodo ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="c2974-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="c2974-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="c2974-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2974-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2974-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2974-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2974-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="c2974-106">[in] Identifica l'assembly che sta per essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="c2974-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c2974-107">[in] HRESULT che indica se l'assembly è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c2974-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2974-108">Note</span><span class="sxs-lookup"><span data-stu-id="c2974-108">Remarks</span></span>  
 <span data-ttu-id="c2974-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo che il [AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) restituzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="c2974-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="c2974-110">Alcune parti dello scaricamento dell'assembly potrebbero continuare dopo il `AssemblyUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="c2974-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="c2974-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="c2974-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c2974-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte di scaricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c2974-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2974-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2974-113">Requirements</span></span>  
 <span data-ttu-id="c2974-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2974-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2974-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2974-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2974-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2974-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2974-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2974-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2974-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2974-118">See also</span></span>

- [<span data-ttu-id="c2974-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c2974-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
