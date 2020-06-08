---
title: Metodo ICorProfilerCallback::ModuleLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
ms.openlocfilehash: a04f72fff9a88c8689821131b08b35500c23b3d9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503354"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="cc709-102">Metodo ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="cc709-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="cc709-103">Notifica al profiler che un modulo è in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="cc709-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc709-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc709-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc709-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc709-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="cc709-106">in ID del modulo che viene caricato.</span><span class="sxs-lookup"><span data-stu-id="cc709-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc709-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cc709-107">Remarks</span></span>  
 <span data-ttu-id="cc709-108">Il valore di `moduleId` non è valido per una richiesta di informazioni fino a quando non viene chiamato il metodo [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cc709-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc709-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc709-109">Requirements</span></span>  
 <span data-ttu-id="cc709-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc709-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc709-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc709-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc709-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc709-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc709-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc709-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc709-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc709-114">See also</span></span>

- [<span data-ttu-id="cc709-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cc709-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
