---
title: Metodo ICorProfilerCallback::Initialize
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: e4a003b30c495852a3a68d44d92bef35c3ed7812
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866297"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="874ea-102">Metodo ICorProfilerCallback::Initialize</span><span class="sxs-lookup"><span data-stu-id="874ea-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="874ea-103">Chiamato per inizializzare la Code Profiler ogni volta che viene avviata una nuova applicazione di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="874ea-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="874ea-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="874ea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="874ea-105">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="874ea-106">\[in] puntatore a un'interfaccia [IUnknown](/cpp/atl/iunknown) che il profiler deve eseguire una query per un puntatore a interfaccia [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="874ea-106">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="874ea-107">Note</span><span class="sxs-lookup"><span data-stu-id="874ea-107">Remarks</span></span>  
 <span data-ttu-id="874ea-108">La chiamata `Initialize` è l'unica opportunità per abilitare o disabilitare i callback che non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="874ea-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="874ea-109">Quando un callback viene abilitato dalla chiamata di `Initialize`, non può essere disabilitato in un secondo momento utilizzando [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="874ea-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="874ea-110">Il valore COR_PRF_MONITOR_IMMUTABLE dell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica gli eventi che non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="874ea-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="874ea-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="874ea-111">Requirements</span></span>  
 <span data-ttu-id="874ea-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="874ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="874ea-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="874ea-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="874ea-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="874ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="874ea-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="874ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874ea-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="874ea-116">See also</span></span>

- [<span data-ttu-id="874ea-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="874ea-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="874ea-118">Metodo Shutdown</span><span class="sxs-lookup"><span data-stu-id="874ea-118">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
