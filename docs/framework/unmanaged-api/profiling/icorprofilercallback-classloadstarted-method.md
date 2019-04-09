---
title: Metodo ICorProfilerCallback::ClassLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db7a033944272756a739dec39d4df11fde1d48b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178607"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="1b29f-102">Metodo ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="1b29f-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="1b29f-103">Notifica al profiler che venga caricata una classe.</span><span class="sxs-lookup"><span data-stu-id="1b29f-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b29f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b29f-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b29f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b29f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1b29f-106">[in] Identifica la classe in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="1b29f-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b29f-107">Note</span><span class="sxs-lookup"><span data-stu-id="1b29f-107">Remarks</span></span>  
 <span data-ttu-id="1b29f-108">Il valore di `classId` non è valido per una richiesta di informazioni finché non la [ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="1b29f-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b29f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b29f-109">Requirements</span></span>  
 <span data-ttu-id="1b29f-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b29f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b29f-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b29f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b29f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b29f-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1b29f-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1b29f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b29f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b29f-114">See also</span></span>

- [<span data-ttu-id="1b29f-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1b29f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
