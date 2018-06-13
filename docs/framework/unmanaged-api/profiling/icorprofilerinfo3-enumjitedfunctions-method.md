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
ms.openlocfilehash: 6f35a712472887a928b1732f076b39ac08724c7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456071"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="c33dc-102">Metodo ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="c33dc-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="c33dc-103">Restituisce un enumeratore per tutte le funzioni che erano in precedenza a compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="c33dc-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c33dc-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c33dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c33dc-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c33dc-106">[out] Un puntatore al [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c33dc-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c33dc-107">Note</span><span class="sxs-lookup"><span data-stu-id="c33dc-107">Remarks</span></span>  
 <span data-ttu-id="c33dc-108">Questo metodo può sovrapporsi con `JITCompilation` i callback, ad esempio il [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="c33dc-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="c33dc-109">L'enumeratore restituito da questo metodo non include le funzioni caricate da immagini native generate con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="c33dc-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c33dc-110">Include solo "0" per il valore di enumerazione restituito il `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="c33dc-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="c33dc-111">Se occorre valido `COR_PRF_FUNCTION::reJitId` valori, utilizzare il [icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="c33dc-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c33dc-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c33dc-112">Requirements</span></span>  
 <span data-ttu-id="c33dc-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c33dc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c33dc-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c33dc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c33dc-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c33dc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c33dc-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c33dc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c33dc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c33dc-117">See Also</span></span>  
 [<span data-ttu-id="c33dc-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="c33dc-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="c33dc-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c33dc-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c33dc-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="c33dc-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
