---
title: Metodo ICorProfilerCallback::ClassUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 14eb90c707618796d6d62ed2ec5710ceba31ba6c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500377"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="03f30-102">Metodo ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="03f30-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="03f30-103">Notifica al profiler che una classe ha completato lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="03f30-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f30-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03f30-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03f30-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03f30-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="03f30-106">\[in] identifica la classe che è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="03f30-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="03f30-107">\[in] valore HRESULT che indica se la classe è stata scaricata correttamente.</span><span class="sxs-lookup"><span data-stu-id="03f30-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="03f30-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="03f30-108">Remarks</span></span>  
 <span data-ttu-id="03f30-109">Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ClassUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="03f30-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="03f30-110">Un errore HRESULT in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="03f30-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="03f30-111">Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento della classe ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="03f30-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03f30-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03f30-112">Requirements</span></span>  
 <span data-ttu-id="03f30-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03f30-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03f30-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03f30-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03f30-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03f30-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03f30-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03f30-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f30-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03f30-117">See also</span></span>

- [<span data-ttu-id="03f30-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="03f30-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="03f30-119">Metodo ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="03f30-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
