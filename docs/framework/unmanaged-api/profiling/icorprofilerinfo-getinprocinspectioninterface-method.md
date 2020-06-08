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
ms.openlocfilehash: 2fe0b314f761cf3c7a3a926d40c69302d0ece000
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498089"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="7076c-102">Metodo ICorProfilerInfo::GetInprocInspectionInterface</span><span class="sxs-lookup"><span data-stu-id="7076c-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="7076c-103">Ottiene un oggetto su cui è possibile eseguire una query per un'interfaccia "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="7076c-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="7076c-104">Questo metodo è obsoleto nella versione .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="7076c-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7076c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7076c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7076c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7076c-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="7076c-107">oggetto [out su](/cpp/atl/iunknown) cui è possibile eseguire una query per un' `ICorDebugProcess` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7076c-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7076c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7076c-108">Remarks</span></span>  
 <span data-ttu-id="7076c-109">L'API di debug di Common Language Runtime (CLR) supportava il debug in-process limitato nella versione .NET Framework 1,0.</span><span class="sxs-lookup"><span data-stu-id="7076c-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="7076c-110">Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="7076c-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="7076c-111">In seguito ai suggerimenti dei clienti, il debug in-process è stato rimosso dal .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.</span><span class="sxs-lookup"><span data-stu-id="7076c-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7076c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7076c-112">Requirements</span></span>  
 <span data-ttu-id="7076c-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7076c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7076c-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7076c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7076c-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7076c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7076c-116">**Versione .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="7076c-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7076c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7076c-117">See also</span></span>

- [<span data-ttu-id="7076c-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="7076c-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
