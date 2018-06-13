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
ms.openlocfilehash: df70041497f000bfd4f6dcac2713e8d5e4eb33f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450944"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="1fbe6-102">Metodo ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="1fbe6-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="1fbe6-103">Notifica al profiler che una classe venga caricata.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fbe6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fbe6-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fbe6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1fbe6-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1fbe6-106">[in] Identifica la classe che viene caricata.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fbe6-107">Note</span><span class="sxs-lookup"><span data-stu-id="1fbe6-107">Remarks</span></span>  
 <span data-ttu-id="1fbe6-108">Il valore di `classId` non è valido per una richiesta di informazioni fino a quando il [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="1fbe6-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fbe6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1fbe6-109">Requirements</span></span>  
 <span data-ttu-id="1fbe6-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fbe6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fbe6-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fbe6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1fbe6-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1fbe6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fbe6-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fbe6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbe6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fbe6-114">See Also</span></span>  
 [<span data-ttu-id="1fbe6-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1fbe6-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
