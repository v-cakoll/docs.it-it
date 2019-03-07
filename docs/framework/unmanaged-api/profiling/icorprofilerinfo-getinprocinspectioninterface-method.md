---
title: Metodo ICorProfilerInfo::GetInprocInspectionInterface
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fbb4aa43757df86037d9c883e76ee38cef5eeb86
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494428"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="34c05-102">Metodo ICorProfilerInfo::GetInprocInspectionInterface</span><span class="sxs-lookup"><span data-stu-id="34c05-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="34c05-103">Ottiene un oggetto che è possibile eseguire query per un'interfaccia "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="34c05-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="34c05-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="34c05-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c05-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34c05-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34c05-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="34c05-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="34c05-107">[out](/cpp/atl/iunknown) oggetto che è possibile cercare un `ICorDebugProcess` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="34c05-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34c05-108">Note</span><span class="sxs-lookup"><span data-stu-id="34c05-108">Remarks</span></span>  
 <span data-ttu-id="34c05-109">API di debug di common language runtime (CLR) supportata limitato in-process debugging in .NET Framework versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="34c05-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="34c05-110">Per attivare un profiler di usare le parti di verifica dell'API di debug, il debug in-process.</span><span class="sxs-lookup"><span data-stu-id="34c05-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="34c05-111">In seguito a commenti e suggerimenti dei clienti, debug in-process è stati rimossi da .NET Framework versione 2.0 e sostituito con un set di funzionalità che è più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="34c05-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34c05-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34c05-112">Requirements</span></span>  
 <span data-ttu-id="34c05-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34c05-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34c05-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="34c05-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="34c05-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34c05-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34c05-116">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="34c05-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c05-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34c05-117">See also</span></span>
- [<span data-ttu-id="34c05-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="34c05-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
