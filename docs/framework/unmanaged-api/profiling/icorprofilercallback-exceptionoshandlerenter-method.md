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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9167b35556fafb33e61e1dc050488aec2b7fa01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776021"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="547f7-102">Metodo ICorProfilerCallback::ExceptionOSHandlerEnter</span><span class="sxs-lookup"><span data-stu-id="547f7-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="547f7-103">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="547f7-103">Not implemented.</span></span> <span data-ttu-id="547f7-104">Un profiler che richiede informazioni sull'eccezione non gestita è necessario ottenere queste informazioni tramite altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="547f7-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="547f7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="547f7-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="547f7-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="547f7-106">Requirements</span></span>  
 <span data-ttu-id="547f7-107">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="547f7-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="547f7-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="547f7-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="547f7-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="547f7-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="547f7-110">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="547f7-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="547f7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="547f7-111">See also</span></span>

- [<span data-ttu-id="547f7-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="547f7-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
