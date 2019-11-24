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
ms.openlocfilehash: 3abf944df3619256791882bf61dfc4072b642c54
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445132"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="ff500-102">Metodo ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="ff500-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="ff500-103">Notifies the profiler that an assembly is being unloaded.</span><span class="sxs-lookup"><span data-stu-id="ff500-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff500-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff500-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff500-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff500-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="ff500-106">[in] Identifies the assembly that is being unloaded.</span><span class="sxs-lookup"><span data-stu-id="ff500-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff500-107">Note</span><span class="sxs-lookup"><span data-stu-id="ff500-107">Remarks</span></span>  
 <span data-ttu-id="ff500-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span><span class="sxs-lookup"><span data-stu-id="ff500-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff500-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff500-109">Requirements</span></span>  
 <span data-ttu-id="ff500-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff500-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff500-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff500-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff500-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff500-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff500-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff500-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff500-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff500-114">See also</span></span>

- [<span data-ttu-id="ff500-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ff500-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ff500-116">Metodo AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="ff500-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
