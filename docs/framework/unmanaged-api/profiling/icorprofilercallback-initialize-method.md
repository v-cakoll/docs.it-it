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
ms.openlocfilehash: ea4fc8ab39d616415106150f56f4b7afd5f68237
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500104"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="10859-102">Metodo ICorProfilerCallback::Initialize</span><span class="sxs-lookup"><span data-stu-id="10859-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="10859-103">Chiamato per inizializzare la Code Profiler ogni volta che viene avviata una nuova applicazione di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="10859-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10859-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10859-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10859-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10859-105">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="10859-106">\[in] puntatore a un'interfaccia [IUnknown](/cpp/atl/iunknown) che il profiler deve eseguire una query per un puntatore di interfaccia [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="10859-106">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="10859-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="10859-107">Remarks</span></span>  
 <span data-ttu-id="10859-108">La `Initialize` chiamata è l'unica opportunità per abilitare (o disabilitare) i callback che non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="10859-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="10859-109">Quando un callback viene abilitato dalla `Initialize` chiamata, non può essere disabilitato in un secondo momento utilizzando [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="10859-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="10859-110">Il valore COR_PRF_MONITOR_IMMUTABLE dell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica gli eventi che non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="10859-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10859-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10859-111">Requirements</span></span>  
 <span data-ttu-id="10859-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10859-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10859-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10859-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10859-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10859-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10859-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10859-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10859-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10859-116">See also</span></span>

- [<span data-ttu-id="10859-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="10859-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="10859-118">Metodo Shutdown</span><span class="sxs-lookup"><span data-stu-id="10859-118">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
