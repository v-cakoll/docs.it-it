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
ms.openlocfilehash: 734ae1d14d02d47c7d3126f1b4cf55dcb4ad151b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866624"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="1eadd-102">Metodo ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="1eadd-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="1eadd-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="1eadd-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eadd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1eadd-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eadd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1eadd-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="1eadd-106">\[in] identifica l'assembly da scaricare.</span><span class="sxs-lookup"><span data-stu-id="1eadd-106">\[in] Identifies the assembly that is being unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="1eadd-107">\[in] valore HRESULT che indica se l'assembly è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1eadd-107">\[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="1eadd-108">Note</span><span class="sxs-lookup"><span data-stu-id="1eadd-108">Remarks</span></span>  
 <span data-ttu-id="1eadd-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo che il metodo [ICorProfilerCallback:: AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) restituisce.</span><span class="sxs-lookup"><span data-stu-id="1eadd-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="1eadd-110">Alcune parti dello scaricamento dell'assembly potrebbero continuare dopo il callback `AssemblyUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="1eadd-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="1eadd-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="1eadd-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="1eadd-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1eadd-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eadd-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1eadd-113">Requirements</span></span>  
 <span data-ttu-id="1eadd-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eadd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eadd-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1eadd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1eadd-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eadd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eadd-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eadd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eadd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1eadd-118">See also</span></span>

- [<span data-ttu-id="1eadd-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1eadd-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
