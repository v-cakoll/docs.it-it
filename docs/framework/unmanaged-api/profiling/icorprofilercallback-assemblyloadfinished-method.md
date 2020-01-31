---
title: Metodo ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: 15ce195af0c0e8f8777f6e5d02043e17e32308da
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866650"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="341e6-102">Metodo ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="341e6-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="341e6-103">Notifica al profiler che è stato completato il caricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="341e6-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="341e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="341e6-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="341e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="341e6-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="341e6-106">\[in] identifica l'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="341e6-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="341e6-107">\[in] valore HRESULT che indica se il caricamento dell'assembly è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="341e6-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="341e6-108">Note</span><span class="sxs-lookup"><span data-stu-id="341e6-108">Remarks</span></span>  
 <span data-ttu-id="341e6-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni fino a quando non viene chiamato il metodo di `AssemblyLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="341e6-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="341e6-110">Alcune parti del caricamento dell'assembly potrebbero continuare dopo il callback `AssemblyLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="341e6-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="341e6-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="341e6-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="341e6-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte del caricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="341e6-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="341e6-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="341e6-113">Requirements</span></span>  
 <span data-ttu-id="341e6-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="341e6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="341e6-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="341e6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="341e6-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="341e6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="341e6-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="341e6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341e6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="341e6-118">See also</span></span>

- [<span data-ttu-id="341e6-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="341e6-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
