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
ms.openlocfilehash: d00e67d29921edc6b7487ceeb12aaa9e9f9bd0ac
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500416"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="f1ae2-102">Metodo ICorProfilerCallback::AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="f1ae2-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="f1ae2-103">Notifica al profiler che un assembly è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="f1ae2-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ae2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1ae2-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1ae2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1ae2-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="f1ae2-106">\[in] identifica l'assembly da scaricare.</span><span class="sxs-lookup"><span data-stu-id="f1ae2-106">\[in] Identifies the assembly that is being unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="f1ae2-107">\[in] valore HRESULT che indica se l'assembly è stato scaricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f1ae2-107">\[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1ae2-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f1ae2-108">Remarks</span></span>  
 <span data-ttu-id="f1ae2-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo che il metodo [ICorProfilerCallback:: AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) restituisce.</span><span class="sxs-lookup"><span data-stu-id="f1ae2-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="f1ae2-110">Alcune parti dello scaricamento dell'assembly potrebbero continuare dopo il `AssemblyUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="f1ae2-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="f1ae2-111">Un errore HRESULT in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="f1ae2-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="f1ae2-112">Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f1ae2-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ae2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1ae2-113">Requirements</span></span>  
 <span data-ttu-id="f1ae2-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ae2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ae2-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1ae2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1ae2-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1ae2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1ae2-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ae2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ae2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1ae2-118">See also</span></span>

- [<span data-ttu-id="f1ae2-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f1ae2-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
