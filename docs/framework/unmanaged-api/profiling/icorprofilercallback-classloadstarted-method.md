---
title: Metodo ICorProfilerCallback::ClassLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: 9a9fdc80c8f63dd5b004953266a5d7399655bc71
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500364"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="da76a-102">Metodo ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="da76a-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="da76a-103">Notifica al profiler che è in corso il caricamento di una classe.</span><span class="sxs-lookup"><span data-stu-id="da76a-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da76a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da76a-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da76a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da76a-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="da76a-106">\[in] identifica la classe da caricare.</span><span class="sxs-lookup"><span data-stu-id="da76a-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="da76a-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="da76a-107">Remarks</span></span>  
 <span data-ttu-id="da76a-108">Il valore di `classId` non è valido per una richiesta di informazioni fino a quando non viene chiamato il metodo [ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="da76a-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da76a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da76a-109">Requirements</span></span>  
 <span data-ttu-id="da76a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da76a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da76a-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da76a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da76a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da76a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da76a-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da76a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da76a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da76a-114">See also</span></span>

- [<span data-ttu-id="da76a-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="da76a-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
