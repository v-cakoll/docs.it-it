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
ms.openlocfilehash: 0a677e33950f178b916a5e9e9cbb7bd918c1349b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866611"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="6f6c0-102">Metodo ICorProfilerCallback::AssemblyUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="6f6c0-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="6f6c0-103">Notifica al profiler che è in corso lo scaricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="6f6c0-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f6c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f6c0-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f6c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f6c0-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="6f6c0-106">\[in] identifica l'assembly da scaricare.</span><span class="sxs-lookup"><span data-stu-id="6f6c0-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f6c0-107">Note</span><span class="sxs-lookup"><span data-stu-id="6f6c0-107">Remarks</span></span>  
 <span data-ttu-id="6f6c0-108">Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo la restituzione del metodo `AssemblyUnloadStarted`, ovvero l'ultima possibilità del profiler di ottenere informazioni su questo assembly.</span><span class="sxs-lookup"><span data-stu-id="6f6c0-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f6c0-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="6f6c0-109">Requirements</span></span>  
 <span data-ttu-id="6f6c0-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f6c0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f6c0-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f6c0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f6c0-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f6c0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f6c0-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f6c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f6c0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f6c0-114">See also</span></span>

- [<span data-ttu-id="6f6c0-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6f6c0-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6f6c0-116">Metodo AssemblyUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="6f6c0-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
