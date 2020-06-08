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
ms.openlocfilehash: 3ebf4a7706b3d3495e4a617b4f86a50281115436
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496555"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="4efe2-102">Metodo ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="4efe2-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="4efe2-103">Restituisce un enumeratore per tutte le funzioni precedentemente compilate tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="4efe2-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4efe2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4efe2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4efe2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4efe2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4efe2-106">out Puntatore all'enumeratore [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4efe2-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4efe2-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4efe2-107">Remarks</span></span>  
 <span data-ttu-id="4efe2-108">Questo metodo può sovrapporsi a `JITCompilation` callback come il metodo [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4efe2-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="4efe2-109">L'enumeratore restituito da questo metodo non include le funzioni caricate da immagini native generate con Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="4efe2-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4efe2-110">L'enumerazione restituita include solo "0" per il valore del `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="4efe2-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="4efe2-111">Se `COR_PRF_FUNCTION::reJitId` sono necessari valori validi, usare il metodo [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4efe2-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4efe2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4efe2-112">Requirements</span></span>  
 <span data-ttu-id="4efe2-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4efe2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4efe2-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4efe2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4efe2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4efe2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4efe2-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4efe2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efe2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4efe2-117">See also</span></span>

- [<span data-ttu-id="4efe2-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="4efe2-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4efe2-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="4efe2-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4efe2-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="4efe2-120">Profiling</span></span>](index.md)
