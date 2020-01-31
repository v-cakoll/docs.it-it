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
ms.openlocfilehash: a22a0de9a20f32ce1c9818bbcf29222a4b331420
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862425"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="8cbd0-102">Metodo ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="8cbd0-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="8cbd0-103">Restituisce un enumeratore per tutte le funzioni precedentemente compilate tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="8cbd0-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cbd0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cbd0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cbd0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8cbd0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8cbd0-106">out Puntatore all'enumeratore [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8cbd0-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cbd0-107">Note</span><span class="sxs-lookup"><span data-stu-id="8cbd0-107">Remarks</span></span>  
 <span data-ttu-id="8cbd0-108">Questo metodo può sovrapporsi a `JITCompilation` callback, ad esempio il metodo [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8cbd0-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="8cbd0-109">L'enumeratore restituito da questo metodo non include le funzioni caricate da immagini native generate con Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="8cbd0-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8cbd0-110">L'enumerazione restituita include solo "0" per il valore del campo `COR_PRF_FUNCTION::reJitId`.</span><span class="sxs-lookup"><span data-stu-id="8cbd0-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="8cbd0-111">Se sono necessari valori di `COR_PRF_FUNCTION::reJitId` validi, usare il metodo [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8cbd0-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cbd0-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8cbd0-112">Requirements</span></span>  
 <span data-ttu-id="8cbd0-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cbd0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cbd0-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8cbd0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8cbd0-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cbd0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cbd0-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cbd0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cbd0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cbd0-117">See also</span></span>

- [<span data-ttu-id="8cbd0-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="8cbd0-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="8cbd0-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="8cbd0-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="8cbd0-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="8cbd0-120">Profiling</span></span>](index.md)
