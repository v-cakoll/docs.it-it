---
title: Metodo ICorProfilerInfo::GetInprocInspectionIThisThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: 0a4cb365ca8f7d52be505368a3d769a9728983bf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502964"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="f8aab-102">Metodo ICorProfilerInfo::GetInprocInspectionIThisThread</span><span class="sxs-lookup"><span data-stu-id="f8aab-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="f8aab-103">Ottiene un oggetto su cui è possibile eseguire query per l'interfaccia ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f8aab-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="f8aab-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f8aab-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8aab-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8aab-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8aab-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8aab-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="f8aab-107">oggetto [out su](/cpp/atl/iunknown) cui è possibile eseguire query per l' `ICorDebugThread` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f8aab-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8aab-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f8aab-108">Remarks</span></span>  
 <span data-ttu-id="f8aab-109">I servizi di debug di Common Language Runtime (CLR) supportano il debug in-process limitato nella versione .NET Framework 1,0.</span><span class="sxs-lookup"><span data-stu-id="f8aab-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="f8aab-110">Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="f8aab-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="f8aab-111">In seguito ai suggerimenti dei clienti, il debug in-process è stato rimosso dal .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="f8aab-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8aab-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8aab-112">Requirements</span></span>  
 <span data-ttu-id="f8aab-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8aab-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8aab-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8aab-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8aab-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8aab-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8aab-116">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="f8aab-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8aab-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8aab-117">See also</span></span>

- [<span data-ttu-id="f8aab-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f8aab-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
