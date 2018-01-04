---
title: Metodo ICorProfilerCallback::AssemblyUnloadStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9984cff1d3c4013d66bc9eb7dbe5dbe7b61d2ba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="a79d6-102">Metodo ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="a79d6-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="a79d6-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="a79d6-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a79d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a79d6-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a79d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a79d6-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="a79d6-106">[in] Identifica l'assembly in fase di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="a79d6-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a79d6-107">Note</span><span class="sxs-lookup"><span data-stu-id="a79d6-107">Remarks</span></span>  
 <span data-ttu-id="a79d6-108">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo il `AssemblyUnloadStarted` metodo restituisce, si tratta di completamento per ottenere informazioni su questo assembly.</span><span class="sxs-lookup"><span data-stu-id="a79d6-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a79d6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a79d6-109">Requirements</span></span>  
 <span data-ttu-id="a79d6-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a79d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a79d6-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a79d6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a79d6-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a79d6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a79d6-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a79d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a79d6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a79d6-114">See Also</span></span>  
 [<span data-ttu-id="a79d6-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a79d6-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a79d6-116">Metodo AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="a79d6-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
