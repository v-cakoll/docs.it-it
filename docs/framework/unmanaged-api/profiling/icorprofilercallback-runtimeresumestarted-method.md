---
title: Metodo ICorProfilerCallback::RuntimeResumeStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeResumeStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf63dd0882784750747a3fe5a68bb8dd432c4a78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="4eba1-102">Metodo ICorProfilerCallback::RuntimeResumeStarted</span><span class="sxs-lookup"><span data-stu-id="4eba1-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="4eba1-103">Notifica al profiler che il runtime viene ripresa di tutti i thread in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4eba1-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eba1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4eba1-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4eba1-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4eba1-105">Requirements</span></span>  
 <span data-ttu-id="4eba1-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eba1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eba1-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4eba1-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4eba1-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4eba1-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4eba1-109">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eba1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eba1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4eba1-110">See Also</span></span>  
 [<span data-ttu-id="4eba1-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4eba1-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4eba1-112">RuntimeResumeFinished (metodo)</span><span class="sxs-lookup"><span data-stu-id="4eba1-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
