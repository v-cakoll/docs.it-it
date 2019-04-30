---
title: Metodo ICorProfilerInfo::GetHandleFromThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fc26ad9b25ad243bf868d6ef3155360509e6483
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049583"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="fee59-102">Metodo ICorProfilerInfo::GetHandleFromThread</span><span class="sxs-lookup"><span data-stu-id="fee59-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="fee59-103">L'ID di un thread viene eseguito il mapping a un handle del thread Win32.</span><span class="sxs-lookup"><span data-stu-id="fee59-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fee59-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fee59-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fee59-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fee59-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="fee59-106">[in] ID del thread per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="fee59-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="fee59-107">[out] Puntatore a un handle del thread Win32.</span><span class="sxs-lookup"><span data-stu-id="fee59-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fee59-108">Note</span><span class="sxs-lookup"><span data-stu-id="fee59-108">Remarks</span></span>  
 <span data-ttu-id="fee59-109">Il profiler deve chiamare Win32 `DuplicateHandle` funzione l'handle prima di poterla usare.</span><span class="sxs-lookup"><span data-stu-id="fee59-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fee59-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fee59-110">Requirements</span></span>  
 <span data-ttu-id="fee59-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fee59-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fee59-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fee59-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fee59-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fee59-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fee59-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fee59-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee59-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fee59-115">See also</span></span>

- [<span data-ttu-id="fee59-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fee59-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
