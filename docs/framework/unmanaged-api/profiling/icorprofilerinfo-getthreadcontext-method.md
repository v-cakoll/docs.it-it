---
title: Metodo ICorProfilerInfo::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b13402b6bccd825629b0110c948ed920c1fdf8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487967"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="14f8b-102">Metodo ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="14f8b-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="14f8b-103">Ottiene l'identità del contesto attualmente associato al thread specificato.</span><span class="sxs-lookup"><span data-stu-id="14f8b-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14f8b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14f8b-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14f8b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14f8b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="14f8b-106">[in] L'ID del thread.</span><span class="sxs-lookup"><span data-stu-id="14f8b-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="14f8b-107">[out] Un puntatore all'ID di contesto attualmente associato al thread specificato.</span><span class="sxs-lookup"><span data-stu-id="14f8b-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="14f8b-108">Se il thread non è attualmente associato alcun contesto, questa funzione restituirà CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="14f8b-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14f8b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14f8b-109">Requirements</span></span>  
 <span data-ttu-id="14f8b-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14f8b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14f8b-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14f8b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14f8b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14f8b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14f8b-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14f8b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f8b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14f8b-114">See also</span></span>
- [<span data-ttu-id="14f8b-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="14f8b-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
