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
ms.openlocfilehash: 0ab383f0968061667b3580a2058687eecda99dde
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870042"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="265dc-102">Metodo ICorProfilerInfo::GetInprocInspectionIThisThread</span><span class="sxs-lookup"><span data-stu-id="265dc-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="265dc-103">Ottiene un oggetto su cui è possibile eseguire query per l'interfaccia ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="265dc-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="265dc-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="265dc-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="265dc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="265dc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="265dc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="265dc-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="265dc-107">oggetto [out su](/cpp/atl/iunknown) cui è possibile eseguire query per l'interfaccia `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="265dc-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="265dc-108">Note</span><span class="sxs-lookup"><span data-stu-id="265dc-108">Remarks</span></span>  
 <span data-ttu-id="265dc-109">I servizi di debug di Common Language Runtime (CLR) supportano il debug in-process limitato nella versione .NET Framework 1,0.</span><span class="sxs-lookup"><span data-stu-id="265dc-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="265dc-110">Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="265dc-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="265dc-111">In seguito ai suggerimenti dei clienti, il debug in-process è stato rimosso dal .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="265dc-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="265dc-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="265dc-112">Requirements</span></span>  
 <span data-ttu-id="265dc-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="265dc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="265dc-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="265dc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="265dc-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="265dc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="265dc-116">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="265dc-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265dc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="265dc-117">See also</span></span>

- [<span data-ttu-id="265dc-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="265dc-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
