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
ms.openlocfilehash: bc4643f1c90b3ea4d3b561249a4e76ff304737bd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438767"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="d8070-102">Metodo ICorProfilerInfo::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="d8070-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="d8070-103">Gets the context identity currently associated with the specified thread.</span><span class="sxs-lookup"><span data-stu-id="d8070-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8070-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8070-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8070-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8070-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="d8070-106">[in] The ID of the thread.</span><span class="sxs-lookup"><span data-stu-id="d8070-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="d8070-107">[out] A pointer to the context ID currently associated with the specified thread.</span><span class="sxs-lookup"><span data-stu-id="d8070-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="d8070-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="d8070-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8070-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8070-109">Requirements</span></span>  
 <span data-ttu-id="d8070-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8070-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8070-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8070-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8070-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8070-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8070-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8070-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8070-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8070-114">See also</span></span>

- [<span data-ttu-id="d8070-115">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d8070-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
