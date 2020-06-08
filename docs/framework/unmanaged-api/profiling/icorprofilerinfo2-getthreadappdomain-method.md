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
ms.openlocfilehash: 70535f8bcee95c2596c43617eb5893e2d92a355b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496780"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="0fcad-102">Metodo ICorProfilerInfo2::GetThreadAppDomain</span><span class="sxs-lookup"><span data-stu-id="0fcad-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="0fcad-103">Ottiene l'ID del dominio dell'applicazione in cui il thread specificato esegue attualmente il codice.</span><span class="sxs-lookup"><span data-stu-id="0fcad-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fcad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fcad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fcad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fcad-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0fcad-106">in ID che specifica il thread.</span><span class="sxs-lookup"><span data-stu-id="0fcad-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="0fcad-107">out Puntatore all'ID del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0fcad-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fcad-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0fcad-108">Requirements</span></span>  
 <span data-ttu-id="0fcad-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fcad-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fcad-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fcad-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fcad-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fcad-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fcad-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fcad-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fcad-113">See also</span></span>

- [<span data-ttu-id="0fcad-114">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0fcad-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="0fcad-115">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="0fcad-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
