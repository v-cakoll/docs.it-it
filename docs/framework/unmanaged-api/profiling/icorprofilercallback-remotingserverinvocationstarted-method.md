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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 091851a5729d496fb030f5d09402f524ca712ae6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556548"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="47da2-102">Metodo ICorProfilerCallback::RemotingServerInvocationStarted</span><span class="sxs-lookup"><span data-stu-id="47da2-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="47da2-103">Notifica al profiler che il processo richiama un metodo in risposta a una richiesta di chiamata al metodo remoto.</span><span class="sxs-lookup"><span data-stu-id="47da2-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47da2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47da2-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="47da2-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47da2-105">Requirements</span></span>  
 <span data-ttu-id="47da2-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47da2-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47da2-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47da2-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47da2-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47da2-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47da2-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47da2-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47da2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47da2-110">See also</span></span>
- [<span data-ttu-id="47da2-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="47da2-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
