---
title: Metodo ICorProfilerCallback::ExceptionOSHandlerLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0decfde08a9097c8fe5185c8b5a3fef4f7f68189
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213337"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="f7fe4-102">Metodo ICorProfilerCallback::ExceptionOSHandlerLeave</span><span class="sxs-lookup"><span data-stu-id="f7fe4-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="f7fe4-103">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="f7fe4-103">Not implemented.</span></span> <span data-ttu-id="f7fe4-104">Un profiler che richiede informazioni sull'eccezione non gestita è necessario ottenere queste informazioni tramite altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="f7fe4-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7fe4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7fe4-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f7fe4-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7fe4-106">Requirements</span></span>  
 <span data-ttu-id="f7fe4-107">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7fe4-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7fe4-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7fe4-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7fe4-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7fe4-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7fe4-110">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7fe4-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7fe4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7fe4-111">See also</span></span>

- [<span data-ttu-id="f7fe4-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f7fe4-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
