---
title: Metodo ICorProfilerInfo3::EnumJITedFunctions
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ceb1d22500f73a29ffdfa6f16907478628358c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969398"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="f1b94-102">Metodo ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="f1b94-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="f1b94-103">Restituisce un enumeratore per tutte le funzioni precedentemente compilate tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="f1b94-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1b94-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1b94-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1b94-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1b94-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f1b94-106">out Puntatore all'enumeratore [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f1b94-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1b94-107">Note</span><span class="sxs-lookup"><span data-stu-id="f1b94-107">Remarks</span></span>  
 <span data-ttu-id="f1b94-108">Questo metodo può sovrapporsi `JITCompilation` a callback come il metodo [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f1b94-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="f1b94-109">L'enumeratore restituito da questo metodo non include le funzioni caricate da immagini native generate con Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="f1b94-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1b94-110">L'enumerazione restituita include solo "0" per il valore del `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="f1b94-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="f1b94-111">Se sono necessari valori `COR_PRF_FUNCTION::reJitId` validi, usare il metodo [ICorProfilerInfo4:: EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f1b94-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1b94-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1b94-112">Requirements</span></span>  
 <span data-ttu-id="f1b94-113">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1b94-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1b94-114">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="f1b94-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1b94-115">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1b94-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1b94-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1b94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b94-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1b94-117">See also</span></span>

- [<span data-ttu-id="f1b94-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="f1b94-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f1b94-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f1b94-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f1b94-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="f1b94-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
