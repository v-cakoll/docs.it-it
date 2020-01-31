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
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863946"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="9690b-102">Metodo ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="9690b-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="9690b-103">Ottiene l'ID del thread corrente, se è un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="9690b-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9690b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9690b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9690b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9690b-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="9690b-106">out Puntatore all'ID restituito del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="9690b-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9690b-107">Note</span><span class="sxs-lookup"><span data-stu-id="9690b-107">Remarks</span></span>  
 <span data-ttu-id="9690b-108">Se il thread corrente è un thread runtime interno o un altro thread non gestito, `GetCurrentThreadID` restituisce CORPROF_E_NOT_MANAGED_THREAD come HRESULT e il valore restituito del parametro `pThreadId` sarà null.</span><span class="sxs-lookup"><span data-stu-id="9690b-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9690b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9690b-109">Requirements</span></span>  
 <span data-ttu-id="9690b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9690b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9690b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9690b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9690b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9690b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9690b-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9690b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9690b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9690b-114">See also</span></span>

- [<span data-ttu-id="9690b-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9690b-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
