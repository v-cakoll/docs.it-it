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
ms.openlocfilehash: 88da5a968bf224dc5b6f45ee5d1d2e75386086f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866156"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="60d13-102">Metodo ICorProfilerCallback::ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="60d13-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="60d13-103">Notifica al profiler che un modulo è in fase di caricamento.</span><span class="sxs-lookup"><span data-stu-id="60d13-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d13-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60d13-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60d13-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60d13-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="60d13-106">in ID del modulo che viene caricato.</span><span class="sxs-lookup"><span data-stu-id="60d13-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60d13-107">Note</span><span class="sxs-lookup"><span data-stu-id="60d13-107">Remarks</span></span>  
 <span data-ttu-id="60d13-108">Il valore di `moduleId` non è valido per una richiesta di informazioni fino a quando non viene chiamato il metodo [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="60d13-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60d13-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="60d13-109">Requirements</span></span>  
 <span data-ttu-id="60d13-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60d13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60d13-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60d13-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60d13-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60d13-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60d13-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60d13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d13-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60d13-114">See also</span></span>

- [<span data-ttu-id="60d13-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="60d13-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
