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
ms.openlocfilehash: 75fb92be078c40f49ddcdc6662535b2a0be7a6ad
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866559"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="e8e2b-102">Metodo ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="e8e2b-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="e8e2b-103">Notifica al profiler che una classe viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="e8e2b-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e2b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8e2b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8e2b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8e2b-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="e8e2b-106">\[in] identifica la classe che viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="e8e2b-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8e2b-107">Note</span><span class="sxs-lookup"><span data-stu-id="e8e2b-107">Remarks</span></span>  
 <span data-ttu-id="e8e2b-108">Il valore di `classId` non è valido per una richiesta di informazioni dopo la restituzione del metodo `ClassUnloadStarted`, ovvero l'ultima possibilità del profiler di ottenere informazioni su questa classe.</span><span class="sxs-lookup"><span data-stu-id="e8e2b-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8e2b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e8e2b-109">Requirements</span></span>  
 <span data-ttu-id="e8e2b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8e2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8e2b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8e2b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8e2b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8e2b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8e2b-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8e2b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e2b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8e2b-114">See also</span></span>

- [<span data-ttu-id="e8e2b-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e8e2b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e8e2b-116">Metodo ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="e8e2b-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
