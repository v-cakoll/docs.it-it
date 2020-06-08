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
ms.openlocfilehash: c2c9ed848984d36ddf10d32d120deda76a4d47cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500286"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="3cf5c-102">Metodo ICorProfilerCallback::ExceptionOSHandlerEnter</span><span class="sxs-lookup"><span data-stu-id="3cf5c-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="3cf5c-103">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="3cf5c-103">Not implemented.</span></span> <span data-ttu-id="3cf5c-104">Un profiler che necessita di informazioni sulle eccezioni non gestite deve ottenere tali informazioni tramite altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="3cf5c-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf5c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cf5c-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3cf5c-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3cf5c-106">Requirements</span></span>  
 <span data-ttu-id="3cf5c-107">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cf5c-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cf5c-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3cf5c-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3cf5c-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cf5c-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cf5c-110">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cf5c-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf5c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cf5c-111">See also</span></span>

- [<span data-ttu-id="3cf5c-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3cf5c-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
