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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8be698d27ce69f955e5c1f17f5258602880c4021
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618698"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="b5562-102">Metodo ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="b5562-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="b5562-103">Ottiene l'ID del thread corrente, se si tratta di un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="b5562-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5562-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5562-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5562-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5562-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="b5562-106">[out] Un puntatore all'ID restituito del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="b5562-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5562-107">Note</span><span class="sxs-lookup"><span data-stu-id="b5562-107">Remarks</span></span>  
 <span data-ttu-id="b5562-108">Se il thread corrente è un thread di runtime interno o un altro thread non gestito, `GetCurrentThreadID` restituisce CORPROF_E_NOT_MANAGED_THREAD come il valore HRESULT e il valore restituito del `pThreadId` parametro sarà null.</span><span class="sxs-lookup"><span data-stu-id="b5562-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5562-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5562-109">Requirements</span></span>  
 <span data-ttu-id="b5562-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5562-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5562-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5562-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5562-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5562-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5562-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5562-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5562-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5562-114">See also</span></span>
- [<span data-ttu-id="b5562-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b5562-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
