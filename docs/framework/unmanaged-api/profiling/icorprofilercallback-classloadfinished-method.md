---
title: Metodo ICorProfilerCallback::ClassLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: 4be2a50664b001e865b5ecdd9aabe8ba727b8c26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500390"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="231b1-102">Metodo ICorProfilerCallback::ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="231b1-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="231b1-103">Notifica al profiler che una classe ha terminato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="231b1-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="231b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="231b1-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="231b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="231b1-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="231b1-106">\[in] identifica la classe che è stata caricata.</span><span class="sxs-lookup"><span data-stu-id="231b1-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="231b1-107">\[in] valore HRESULT che indica se la classe è stata caricata correttamente.</span><span class="sxs-lookup"><span data-stu-id="231b1-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="231b1-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="231b1-108">Remarks</span></span>  
 <span data-ttu-id="231b1-109">Il valore di `classId` non è valido per una richiesta di informazioni fino a quando non `ClassLoadFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="231b1-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="231b1-110">Alcune parti del caricamento della classe potrebbero continuare dopo il `ClassLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="231b1-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="231b1-111">Un errore HRESULT in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="231b1-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="231b1-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte del caricamento della classe ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="231b1-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="231b1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="231b1-113">Requirements</span></span>  
 <span data-ttu-id="231b1-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="231b1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="231b1-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="231b1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="231b1-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="231b1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="231b1-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="231b1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="231b1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="231b1-118">See also</span></span>

- [<span data-ttu-id="231b1-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="231b1-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="231b1-120">Metodo ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="231b1-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
