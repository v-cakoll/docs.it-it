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
ms.openlocfilehash: c121e403d116581ce3fa823d5d8cadbb2a58e296
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445778"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="5cf8a-102">Metodo ICorProfilerCallback::RemotingServerInvocationReturned</span><span class="sxs-lookup"><span data-stu-id="5cf8a-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="5cf8a-103">Notifica al profiler che il processo ha completato la chiamata a un metodo in risposta a una richiesta di chiamata al metodo remoto.</span><span class="sxs-lookup"><span data-stu-id="5cf8a-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cf8a-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="5cf8a-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cf8a-105">Requirements</span></span>  
 <span data-ttu-id="5cf8a-106">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cf8a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cf8a-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5cf8a-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5cf8a-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cf8a-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cf8a-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf8a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf8a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cf8a-110">See also</span></span>

- [<span data-ttu-id="5cf8a-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5cf8a-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
