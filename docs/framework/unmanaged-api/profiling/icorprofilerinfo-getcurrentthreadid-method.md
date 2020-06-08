---
title: Metodo ICorProfilerInfo::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: fa0fe827300a86a906a254292434e2a56ebb4a47
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498401"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="35782-102">Metodo ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="35782-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="35782-103">Ottiene l'ID del thread corrente, se è un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="35782-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35782-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35782-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35782-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35782-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="35782-106">out Puntatore all'ID restituito del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="35782-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35782-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="35782-107">Remarks</span></span>  
 <span data-ttu-id="35782-108">Se il thread corrente è un thread runtime interno o un altro thread non gestito, `GetCurrentThreadID` restituisce CORPROF_E_NOT_MANAGED_THREAD come HRESULT e il valore restituito del `pThreadId` parametro sarà null.</span><span class="sxs-lookup"><span data-stu-id="35782-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35782-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35782-109">Requirements</span></span>  
 <span data-ttu-id="35782-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35782-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35782-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35782-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35782-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35782-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35782-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35782-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35782-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35782-114">See also</span></span>

- [<span data-ttu-id="35782-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="35782-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
