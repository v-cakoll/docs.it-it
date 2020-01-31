---
title: Metodo ICorProfilerCallback::ModuleUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: 7e43f58f619aaa63fa2294dd3e989026dcdfc604
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866130"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="0103b-102">Metodo ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="0103b-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="0103b-103">Notifica al profiler che un modulo è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="0103b-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0103b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0103b-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="0103b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0103b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="0103b-106">in ID del modulo da scaricare.</span><span class="sxs-lookup"><span data-stu-id="0103b-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0103b-107">Note</span><span class="sxs-lookup"><span data-stu-id="0103b-107">Remarks</span></span>  
 <span data-ttu-id="0103b-108">Il valore di `moduleId` non è valido per una richiesta di informazioni dopo la restituzione del metodo `ModuleUnloadStarted`, ovvero l'ultima possibilità del profiler di ottenere informazioni su questo modulo.</span><span class="sxs-lookup"><span data-stu-id="0103b-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0103b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0103b-109">Requirements</span></span>  
 <span data-ttu-id="0103b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0103b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0103b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0103b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0103b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0103b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0103b-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0103b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0103b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0103b-114">See also</span></span>

- [<span data-ttu-id="0103b-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0103b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0103b-116">Metodo ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="0103b-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
