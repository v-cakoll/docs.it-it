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
ms.openlocfilehash: 7c8339142ef382ca029e9dd32c0270bd794ffcc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546689"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="1f8cd-102">Metodo ICorProfilerCallback::ExceptionOSHandlerLeave</span><span class="sxs-lookup"><span data-stu-id="1f8cd-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="1f8cd-103">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="1f8cd-103">Not implemented.</span></span> <span data-ttu-id="1f8cd-104">Un profiler che richiede informazioni sull'eccezione non gestita è necessario ottenere queste informazioni tramite altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="1f8cd-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8cd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f8cd-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1f8cd-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f8cd-106">Requirements</span></span>  
 <span data-ttu-id="1f8cd-107">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f8cd-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f8cd-108">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f8cd-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1f8cd-109">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f8cd-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f8cd-110">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f8cd-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8cd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f8cd-111">See also</span></span>
- [<span data-ttu-id="1f8cd-112">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1f8cd-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
