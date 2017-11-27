---
title: Metodo ICorProfilerInfo::GetThreadContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetThreadContext
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f2802c89a72b6c6c9e268d9d35767ca5b6dadce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="6f257-102">Metodo ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="6f257-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="6f257-103">Ottiene l'identità del contesto attualmente associato al thread specificato.</span><span class="sxs-lookup"><span data-stu-id="6f257-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f257-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f257-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f257-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f257-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="6f257-106">[in] L'ID del thread.</span><span class="sxs-lookup"><span data-stu-id="6f257-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="6f257-107">[out] Un puntatore all'ID di contesto attualmente associato al thread specificato.</span><span class="sxs-lookup"><span data-stu-id="6f257-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="6f257-108">Se il thread non è attualmente associato alcun contesto, questa funzione restituirà CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="6f257-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f257-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f257-109">Requirements</span></span>  
 <span data-ttu-id="6f257-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f257-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f257-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f257-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f257-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f257-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f257-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f257-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f257-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f257-114">See Also</span></span>  
 [<span data-ttu-id="6f257-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6f257-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
