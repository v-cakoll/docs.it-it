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
ms.openlocfilehash: f68565977551a54244f3caf6a0250f67005a6ecf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452882"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="b8f43-102">Metodo ICorProfilerInfo::GetThreadInfo</span><span class="sxs-lookup"><span data-stu-id="b8f43-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="b8f43-103">Ottiene l'identità corrente del thread Win32 per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="b8f43-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f43-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8f43-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8f43-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8f43-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b8f43-106">[in] L'ID del thread per il quale ottenere l'ID Win32 corrente.</span><span class="sxs-lookup"><span data-stu-id="b8f43-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="b8f43-107">[out] ID di un puntatore a thread Win32 corrente del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="b8f43-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8f43-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8f43-108">Requirements</span></span>  
 <span data-ttu-id="b8f43-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8f43-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8f43-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8f43-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8f43-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b8f43-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8f43-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8f43-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f43-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8f43-113">See Also</span></span>  
 [<span data-ttu-id="b8f43-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b8f43-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
