---
title: Metodo ICorProfilerCallback::ExceptionOSHandlerEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: e27fd3147182e8c820fb1d30f172e0517ca4e77e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866476"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="cf2f0-102">Metodo ICorProfilerCallback::ExceptionOSHandlerEnter</span><span class="sxs-lookup"><span data-stu-id="cf2f0-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="cf2f0-103">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="cf2f0-103">Not implemented.</span></span> <span data-ttu-id="cf2f0-104">Un profiler che necessita di informazioni sulle eccezioni non gestite deve ottenere tali informazioni tramite altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="cf2f0-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf2f0-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cf2f0-106">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="cf2f0-106">Requirements</span></span>  
 <span data-ttu-id="cf2f0-107">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf2f0-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf2f0-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf2f0-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf2f0-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf2f0-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf2f0-110">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf2f0-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2f0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf2f0-111">See also</span></span>

- [<span data-ttu-id="cf2f0-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cf2f0-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
