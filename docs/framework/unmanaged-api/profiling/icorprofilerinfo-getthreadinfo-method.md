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
ms.openlocfilehash: 0631afe149c7a179a6cda4b5e491ad28653ddee9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111917"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="b9810-102">Metodo ICorProfilerInfo::GetThreadInfo</span><span class="sxs-lookup"><span data-stu-id="b9810-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="b9810-103">Ottiene l'identità del thread Win32 corrente per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="b9810-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9810-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9810-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9810-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9810-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b9810-106">[in] L'ID del thread per cui ottenere l'ID Win32 corrente.</span><span class="sxs-lookup"><span data-stu-id="b9810-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="b9810-107">[out] Puntatore al thread Win32 corrente del thread specificato ID.</span><span class="sxs-lookup"><span data-stu-id="b9810-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9810-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9810-108">Requirements</span></span>  
 <span data-ttu-id="b9810-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9810-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9810-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9810-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9810-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9810-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b9810-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b9810-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b9810-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9810-113">See also</span></span>

- [<span data-ttu-id="b9810-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b9810-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
