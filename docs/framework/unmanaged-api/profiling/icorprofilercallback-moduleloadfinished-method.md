---
title: Metodo ICorProfilerCallback::ModuleLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 481fc2c40331e31f6a018d012fb2b2543d4fd9b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503367"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="9cbf2-102">Metodo ICorProfilerCallback::ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="9cbf2-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="9cbf2-103">Notifica al profiler che un modulo ha terminato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="9cbf2-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cbf2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9cbf2-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cbf2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9cbf2-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="9cbf2-106">in ID del modulo che ha terminato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="9cbf2-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="9cbf2-107">in HRESULT che indica se il modulo è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9cbf2-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cbf2-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9cbf2-108">Remarks</span></span>  
 <span data-ttu-id="9cbf2-109">Il valore di `moduleId` non è valido per una richiesta di informazioni fino a quando non `ModuleLoadFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="9cbf2-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="9cbf2-110">Alcune parti del caricamento del modulo possono continuare dopo il `ModuleLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="9cbf2-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="9cbf2-111">Un errore HRESULT in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="9cbf2-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="9cbf2-112">Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte del caricamento del modulo è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9cbf2-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cbf2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9cbf2-113">Requirements</span></span>  
 <span data-ttu-id="9cbf2-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cbf2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cbf2-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9cbf2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9cbf2-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cbf2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cbf2-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cbf2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbf2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cbf2-118">See also</span></span>

- [<span data-ttu-id="9cbf2-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9cbf2-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9cbf2-120">Metodo ModuleLoadStarted</span><span class="sxs-lookup"><span data-stu-id="9cbf2-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
