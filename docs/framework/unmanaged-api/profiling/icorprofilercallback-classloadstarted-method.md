---
title: Metodo ICorProfilerCallback::ClassLoadStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22b6d4ca72b0ee95af1c7baae63223cb09435971
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="fc512-102">Metodo ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="fc512-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="fc512-103">Notifica al profiler che una classe venga caricata.</span><span class="sxs-lookup"><span data-stu-id="fc512-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc512-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc512-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc512-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc512-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="fc512-106">[in] Identifica la classe che viene caricata.</span><span class="sxs-lookup"><span data-stu-id="fc512-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc512-107">Note</span><span class="sxs-lookup"><span data-stu-id="fc512-107">Remarks</span></span>  
 <span data-ttu-id="fc512-108">Il valore di `classId` non è valido per una richiesta di informazioni fino a quando il [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="fc512-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc512-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc512-109">Requirements</span></span>  
 <span data-ttu-id="fc512-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc512-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc512-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc512-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc512-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc512-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc512-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc512-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc512-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc512-114">See Also</span></span>  
 [<span data-ttu-id="fc512-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fc512-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
