---
title: Metodo ICorProfilerInfo::GetCurrentThreadID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetCurrentThreadID
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 055a5f56f076cc29ca7ce5d45ecedd650e8f2f44
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="120d4-102">Metodo ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="120d4-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="120d4-103">Ottiene l'ID del thread corrente, se un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="120d4-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="120d4-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="120d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="120d4-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="120d4-106">[out] Un puntatore all'ID restituito del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="120d4-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="120d4-107">Note</span><span class="sxs-lookup"><span data-stu-id="120d4-107">Remarks</span></span>  
 <span data-ttu-id="120d4-108">Se il thread corrente è un thread di runtime interno o un altro thread non gestito, `GetCurrentThreadID` restituirà CORPROF_E_NOT_MANAGED_THREAD come HRESULT e il valore restituito di `pThreadId` parametro sarà null.</span><span class="sxs-lookup"><span data-stu-id="120d4-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="120d4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="120d4-109">Requirements</span></span>  
 <span data-ttu-id="120d4-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120d4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120d4-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="120d4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="120d4-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="120d4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="120d4-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="120d4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120d4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="120d4-114">See Also</span></span>  
 [<span data-ttu-id="120d4-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="120d4-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
