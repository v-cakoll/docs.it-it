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
ms.openlocfilehash: c7ad94bf766e0fcdbff95b0766cf68c2196a2c71
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503333"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="6e95b-102">Metodo ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="6e95b-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="6e95b-103">Notifica al profiler che un modulo è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="6e95b-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e95b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e95b-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="6e95b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e95b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="6e95b-106">in ID del modulo da scaricare.</span><span class="sxs-lookup"><span data-stu-id="6e95b-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e95b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6e95b-107">Remarks</span></span>  
 <span data-ttu-id="6e95b-108">Il valore di `moduleId` non è valido per una richiesta di informazioni dopo la `ModuleUnloadStarted` restituzione del metodo. si tratta dell'ultima possibilità del profiler di ottenere informazioni su questo modulo.</span><span class="sxs-lookup"><span data-stu-id="6e95b-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e95b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e95b-109">Requirements</span></span>  
 <span data-ttu-id="6e95b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e95b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e95b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6e95b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6e95b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e95b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e95b-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e95b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e95b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e95b-114">See also</span></span>

- [<span data-ttu-id="6e95b-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6e95b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6e95b-116">Metodo ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="6e95b-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
