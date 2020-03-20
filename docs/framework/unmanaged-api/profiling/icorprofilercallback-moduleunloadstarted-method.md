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
ms.openlocfilehash: fcfdddbd5316c098754ea7b0d4714b050c64fe55
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175148"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="a28da-102">Metodo ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="a28da-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="a28da-103">Notifica al profiler che è in corso lo scaricamento di un modulo.</span><span class="sxs-lookup"><span data-stu-id="a28da-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a28da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a28da-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="a28da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a28da-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a28da-106">[in] ID del modulo che viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="a28da-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a28da-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a28da-107">Remarks</span></span>  
 <span data-ttu-id="a28da-108">Il valore `moduleId` di non è valido `ModuleUnloadStarted` per una richiesta di informazioni dopo la restituzione del metodo, che è l'ultima possibilità del profiler di ottenere informazioni su questo modulo.</span><span class="sxs-lookup"><span data-stu-id="a28da-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a28da-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a28da-109">Requirements</span></span>  
 <span data-ttu-id="a28da-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a28da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a28da-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a28da-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a28da-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a28da-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a28da-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a28da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28da-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a28da-114">See also</span></span>

- [<span data-ttu-id="a28da-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a28da-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a28da-116">Metodo ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="a28da-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
