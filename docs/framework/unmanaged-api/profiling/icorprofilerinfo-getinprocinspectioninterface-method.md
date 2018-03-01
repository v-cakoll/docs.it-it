---
title: Metodo ICorProfilerInfo::GetInprocInspectionInterface
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9088389df33b079fe2275f5c7e642a055fa8ee51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="735fa-102">Metodo ICorProfilerInfo::GetInprocInspectionInterface</span><span class="sxs-lookup"><span data-stu-id="735fa-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="735fa-103">Ottiene un oggetto che è possibile eseguire query per un'interfaccia "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="735fa-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="735fa-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="735fa-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735fa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="735fa-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="735fa-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="735fa-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="735fa-107">[out](/cpp/atl/iunknown) oggetto che è possibile eseguire query per un `ICorDebugProcess` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="735fa-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="735fa-108">Note</span><span class="sxs-lookup"><span data-stu-id="735fa-108">Remarks</span></span>  
 <span data-ttu-id="735fa-109">L'API di debug di common language runtime (CLR) è supportato il debug in-process limitato in .NET Framework versione 1.0.</span><span class="sxs-lookup"><span data-stu-id="735fa-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="735fa-110">Debug in-process è abilitato un profiler di usare le parti di verifica dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="735fa-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="735fa-111">Come risultato di analisi utilizzo software, debug in-process è stato rimosso da .NET Framework versione 2.0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="735fa-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="735fa-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="735fa-112">Requirements</span></span>  
 <span data-ttu-id="735fa-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="735fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="735fa-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="735fa-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="735fa-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="735fa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="735fa-116">**Versione di .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="735fa-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735fa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="735fa-117">See Also</span></span>  
 [<span data-ttu-id="735fa-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="735fa-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
