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
ms.openlocfilehash: 5d9474f78dd8b999a37f60e0698cfd04240b897a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866572"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="1069b-102">Metodo ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="1069b-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="1069b-103">Notifica al profiler che una classe ha completato lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="1069b-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1069b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1069b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1069b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1069b-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="1069b-106">\[in] identifica la classe che è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="1069b-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="1069b-107">\[in] valore HRESULT che indica se la classe è stata scaricata correttamente.</span><span class="sxs-lookup"><span data-stu-id="1069b-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1069b-108">Note</span><span class="sxs-lookup"><span data-stu-id="1069b-108">Remarks</span></span>  
 <span data-ttu-id="1069b-109">Alcune parti dello scaricamento della classe potrebbero continuare dopo il callback `ClassUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="1069b-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="1069b-110">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="1069b-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="1069b-111">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento della classe ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1069b-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1069b-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1069b-112">Requirements</span></span>  
 <span data-ttu-id="1069b-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1069b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1069b-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1069b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1069b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1069b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1069b-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1069b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1069b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1069b-117">See also</span></span>

- [<span data-ttu-id="1069b-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1069b-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1069b-119">Metodo ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="1069b-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
