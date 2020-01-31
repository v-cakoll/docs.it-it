---
title: Metodo ICorProfilerCallback::RemotingServerInvocationReturned
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
ms.openlocfilehash: 4b82a334d8c64dde824802fcf2a7d0ad17457af0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866000"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="9a1b2-102">Metodo ICorProfilerCallback::RemotingServerInvocationReturned</span><span class="sxs-lookup"><span data-stu-id="9a1b2-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="9a1b2-103">Notifica al profiler che il processo ha completato la chiamata a un metodo in risposta a una richiesta di chiamata al metodo remoto.</span><span class="sxs-lookup"><span data-stu-id="9a1b2-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a1b2-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="9a1b2-105">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9a1b2-105">Requirements</span></span>  
 <span data-ttu-id="9a1b2-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a1b2-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a1b2-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a1b2-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a1b2-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a1b2-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a1b2-109">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a1b2-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1b2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a1b2-110">See also</span></span>

- [<span data-ttu-id="9a1b2-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9a1b2-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
