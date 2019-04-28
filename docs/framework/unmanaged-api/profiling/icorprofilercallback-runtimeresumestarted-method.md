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
ms.openlocfilehash: 2b163d41280c8ea49554cecb845c4be757f55dfc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921979"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="20f06-102">Metodo ICorProfilerCallback::RuntimeResumeStarted</span><span class="sxs-lookup"><span data-stu-id="20f06-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="20f06-103">Notifica al profiler che il runtime viene ripresa di tutti i thread fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="20f06-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20f06-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="20f06-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20f06-105">Requirements</span></span>  
 <span data-ttu-id="20f06-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20f06-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20f06-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20f06-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20f06-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20f06-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20f06-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20f06-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f06-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20f06-110">See also</span></span>

- [<span data-ttu-id="20f06-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="20f06-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="20f06-112">Metodo RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="20f06-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
