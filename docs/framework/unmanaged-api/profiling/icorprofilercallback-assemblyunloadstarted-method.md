---
title: Metodo ICorProfilerCallback::AssemblyUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c95bed520e0a4687541f127c8b39ef7916ef104
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122928"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="d6180-102">Metodo ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="d6180-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="d6180-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="d6180-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6180-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6180-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6180-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6180-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="d6180-106">[in] Identifica l'assembly che sta per essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="d6180-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6180-107">Note</span><span class="sxs-lookup"><span data-stu-id="d6180-107">Remarks</span></span>  
 <span data-ttu-id="d6180-108">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo il `AssemblyUnloadStarted` restituzione del metodo, ovvero si tratta di completamento per ottenere informazioni relative a questo assembly.</span><span class="sxs-lookup"><span data-stu-id="d6180-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6180-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6180-109">Requirements</span></span>  
 <span data-ttu-id="d6180-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6180-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6180-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6180-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6180-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6180-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6180-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6180-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6180-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6180-114">See also</span></span>

- [<span data-ttu-id="d6180-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d6180-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d6180-116">Metodo AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="d6180-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
