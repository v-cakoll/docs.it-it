---
title: Metodo ICorProfilerCallback::RuntimeResumeStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70e687f0645fdb68d95effe6fdd52178b92c08e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452257"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="46637-102">Metodo ICorProfilerCallback::RuntimeResumeStarted</span><span class="sxs-lookup"><span data-stu-id="46637-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="46637-103">Notifica al profiler che il runtime viene ripresa di tutti i thread in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="46637-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46637-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46637-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="46637-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46637-105">Requirements</span></span>  
 <span data-ttu-id="46637-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46637-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46637-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46637-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46637-108">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="46637-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46637-109">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46637-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46637-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46637-110">See Also</span></span>  
 [<span data-ttu-id="46637-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="46637-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="46637-112">Metodo RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="46637-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
