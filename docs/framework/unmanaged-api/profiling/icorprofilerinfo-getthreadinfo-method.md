---
title: Metodo ICorProfilerInfo::GetThreadInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03b6f2fe0cc98b469b9b82bfdc4151adafb99c38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665552"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="265c1-102">Metodo ICorProfilerInfo::GetThreadInfo</span><span class="sxs-lookup"><span data-stu-id="265c1-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="265c1-103">Ottiene l'identità del thread Win32 corrente per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="265c1-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="265c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="265c1-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="265c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="265c1-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="265c1-106">[in] L'ID del thread per cui ottenere l'ID Win32 corrente.</span><span class="sxs-lookup"><span data-stu-id="265c1-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="265c1-107">[out] Puntatore al thread Win32 corrente del thread specificato ID.</span><span class="sxs-lookup"><span data-stu-id="265c1-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="265c1-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="265c1-108">Requirements</span></span>  
 <span data-ttu-id="265c1-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="265c1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="265c1-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="265c1-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="265c1-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="265c1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="265c1-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="265c1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265c1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="265c1-113">See also</span></span>
- [<span data-ttu-id="265c1-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="265c1-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
