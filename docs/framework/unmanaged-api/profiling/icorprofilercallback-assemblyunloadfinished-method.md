---
title: Metodo ICorProfilerCallback::AssemblyUnloadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ead41718e0253de599019112178d64c0ab706924
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="bbed2-102">Metodo ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="bbed2-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="bbed2-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="bbed2-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbed2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbed2-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbed2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bbed2-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="bbed2-106">[in] Identifica l'assembly in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="bbed2-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bbed2-107">[in] Un valore HRESULT che indica se l'assembly è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="bbed2-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbed2-108">Note</span><span class="sxs-lookup"><span data-stu-id="bbed2-108">Remarks</span></span>  
 <span data-ttu-id="bbed2-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo il [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) metodo restituisce.</span><span class="sxs-lookup"><span data-stu-id="bbed2-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="bbed2-110">Alcune parti di scaricamento dell'assembly potrebbero continuare dopo il `AssemblyUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="bbed2-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="bbed2-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="bbed2-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bbed2-112">Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bbed2-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbed2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bbed2-113">Requirements</span></span>  
 <span data-ttu-id="bbed2-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbed2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbed2-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbed2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbed2-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbed2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbed2-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbed2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbed2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbed2-118">See Also</span></span>  
 [<span data-ttu-id="bbed2-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bbed2-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
