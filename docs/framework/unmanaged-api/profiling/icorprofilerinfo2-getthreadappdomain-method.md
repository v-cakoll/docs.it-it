---
title: Metodo ICorProfilerInfo2::GetThreadAppDomain
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 690dbb5659ce991b7c4921fbd85c246da54eff0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453041"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="57394-102">Metodo ICorProfilerInfo2::GetThreadAppDomain</span><span class="sxs-lookup"><span data-stu-id="57394-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="57394-103">Ottiene l'ID del dominio dell'applicazione in cui il thread specificato è attualmente in esecuzione codice.</span><span class="sxs-lookup"><span data-stu-id="57394-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57394-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57394-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57394-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="57394-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="57394-106">[in] L'ID che specifica il thread.</span><span class="sxs-lookup"><span data-stu-id="57394-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="57394-107">[out] Un puntatore all'ID del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="57394-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57394-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57394-108">Requirements</span></span>  
 <span data-ttu-id="57394-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57394-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57394-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57394-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57394-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="57394-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57394-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57394-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57394-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57394-113">See Also</span></span>  
 [<span data-ttu-id="57394-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="57394-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="57394-115">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="57394-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
