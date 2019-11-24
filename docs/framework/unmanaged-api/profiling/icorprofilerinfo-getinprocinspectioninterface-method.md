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
ms.openlocfilehash: d3fcd859fb11f6a0c660751f16fa175e19e9d03b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439002"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="b87ac-102">Metodo ICorProfilerInfo::GetInprocInspectionInterface</span><span class="sxs-lookup"><span data-stu-id="b87ac-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="b87ac-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span><span class="sxs-lookup"><span data-stu-id="b87ac-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="b87ac-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="b87ac-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b87ac-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b87ac-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b87ac-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b87ac-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="b87ac-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span><span class="sxs-lookup"><span data-stu-id="b87ac-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b87ac-108">Note</span><span class="sxs-lookup"><span data-stu-id="b87ac-108">Remarks</span></span>  
 <span data-ttu-id="b87ac-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span><span class="sxs-lookup"><span data-stu-id="b87ac-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="b87ac-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span><span class="sxs-lookup"><span data-stu-id="b87ac-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b87ac-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span><span class="sxs-lookup"><span data-stu-id="b87ac-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b87ac-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b87ac-112">Requirements</span></span>  
 <span data-ttu-id="b87ac-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b87ac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b87ac-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b87ac-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b87ac-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b87ac-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b87ac-116">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="b87ac-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b87ac-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b87ac-117">See also</span></span>

- [<span data-ttu-id="b87ac-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b87ac-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
