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
ms.openlocfilehash: 86402abca5386f34256f1f44f674f1e1898ad5fd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500351"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="6035b-102">Metodo ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="6035b-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="6035b-103">Notifica al profiler che una classe viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="6035b-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6035b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6035b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6035b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6035b-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="6035b-106">\[in] identifica la classe che viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="6035b-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="6035b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6035b-107">Remarks</span></span>  
 <span data-ttu-id="6035b-108">Il valore di `classId` non è valido per una richiesta di informazioni dopo la `ClassUnloadStarted` restituzione del metodo: si tratta dell'ultima possibilità del profiler di ottenere informazioni su questa classe.</span><span class="sxs-lookup"><span data-stu-id="6035b-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6035b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6035b-109">Requirements</span></span>  
 <span data-ttu-id="6035b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6035b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6035b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6035b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6035b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6035b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6035b-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6035b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6035b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6035b-114">See also</span></span>

- [<span data-ttu-id="6035b-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6035b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6035b-116">Metodo ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="6035b-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
