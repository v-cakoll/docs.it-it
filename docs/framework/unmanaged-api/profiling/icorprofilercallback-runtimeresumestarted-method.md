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
ms.openlocfilehash: 08e76e295e30ede48733ab35870ec965eb157f60
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499870"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="26d4f-102">Metodo ICorProfilerCallback::RuntimeResumeStarted</span><span class="sxs-lookup"><span data-stu-id="26d4f-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="26d4f-103">Notifica al profiler che il Runtime sta riprendendo tutti i thread della fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="26d4f-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d4f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26d4f-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="26d4f-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26d4f-105">Requirements</span></span>  
 <span data-ttu-id="26d4f-106">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26d4f-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26d4f-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26d4f-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26d4f-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26d4f-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26d4f-109">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26d4f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d4f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26d4f-110">See also</span></span>

- [<span data-ttu-id="26d4f-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="26d4f-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="26d4f-112">Metodo RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="26d4f-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
