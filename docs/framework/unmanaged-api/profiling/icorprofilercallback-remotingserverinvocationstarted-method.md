---
title: Metodo ICorProfilerCallback::RemotingServerInvocationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationStarted
helpviewer_keywords:
- RemotingServerInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerInvocationStarted method [.NET Framework profiling]
ms.assetid: 86051a11-ad8e-4ace-9a11-ff0f982a5e11
topic_type:
- apiref
ms.openlocfilehash: 3725b73ab55f6e4dc789a1fde8d1224695a174d7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499935"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="c80c5-102">Metodo ICorProfilerCallback::RemotingServerInvocationStarted</span><span class="sxs-lookup"><span data-stu-id="c80c5-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="c80c5-103">Notifica al profiler che il processo sta richiamando un metodo in risposta a una richiesta di chiamata a un metodo remoto.</span><span class="sxs-lookup"><span data-stu-id="c80c5-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c80c5-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c80c5-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c80c5-105">Requirements</span></span>  
 <span data-ttu-id="c80c5-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c80c5-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c80c5-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c80c5-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c80c5-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c80c5-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c80c5-109">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80c5-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80c5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c80c5-110">See also</span></span>

- [<span data-ttu-id="c80c5-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c80c5-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
