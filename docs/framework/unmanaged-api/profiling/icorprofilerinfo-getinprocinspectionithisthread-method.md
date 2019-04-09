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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 24b7af4b44d51da06e9d65104f1b469ef1d83b8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219434"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="b93d2-102">Metodo ICorProfilerInfo::GetInprocInspectionIThisThread</span><span class="sxs-lookup"><span data-stu-id="b93d2-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="b93d2-103">Ottiene un oggetto che è possibile eseguire query per l'interfaccia ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="b93d2-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="b93d2-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="b93d2-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b93d2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b93d2-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b93d2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b93d2-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="b93d2-107">[out](/cpp/atl/iunknown) oggetto che è possibile cercare il `ICorDebugThread` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b93d2-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b93d2-108">Note</span><span class="sxs-lookup"><span data-stu-id="b93d2-108">Remarks</span></span>  
 <span data-ttu-id="b93d2-109">Debug dei servizi di common language runtime (CLR) supportata limitato in-process debugging in .NET Framework versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="b93d2-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="b93d2-110">Per attivare un profiler di usare le parti di verifica dell'API di debug, il debug in-process.</span><span class="sxs-lookup"><span data-stu-id="b93d2-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b93d2-111">In seguito a commenti e suggerimenti dei clienti, debug in-process è stati rimossi da .NET Framework versione 2.0 e sostituito con un set di funzionalità che è più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="b93d2-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b93d2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b93d2-112">Requirements</span></span>  
 <span data-ttu-id="b93d2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b93d2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b93d2-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b93d2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b93d2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b93d2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b93d2-116">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="b93d2-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b93d2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b93d2-117">See also</span></span>

- [<span data-ttu-id="b93d2-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b93d2-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
