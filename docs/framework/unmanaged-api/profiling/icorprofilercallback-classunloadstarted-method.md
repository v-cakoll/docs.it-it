---
title: Metodo ICorProfilerCallback::ClassUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 3b729d3be84571a48cc9a770d7f06b99723c0d1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445075"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="fcabe-102">Metodo ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="fcabe-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="fcabe-103">Notifica al profiler che una classe viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="fcabe-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcabe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcabe-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcabe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fcabe-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="fcabe-106">in Identifica la classe che viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="fcabe-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcabe-107">Note</span><span class="sxs-lookup"><span data-stu-id="fcabe-107">Remarks</span></span>  
 <span data-ttu-id="fcabe-108">Il valore di `classId` non è valido per una richiesta di informazioni dopo la restituzione del metodo `ClassUnloadStarted`, ovvero l'ultima possibilità del profiler di ottenere informazioni su questa classe.</span><span class="sxs-lookup"><span data-stu-id="fcabe-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcabe-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fcabe-109">Requirements</span></span>  
 <span data-ttu-id="fcabe-110">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcabe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcabe-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fcabe-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fcabe-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcabe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcabe-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcabe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcabe-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcabe-114">See also</span></span>

- [<span data-ttu-id="fcabe-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fcabe-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fcabe-116">Metodo ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="fcabe-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
