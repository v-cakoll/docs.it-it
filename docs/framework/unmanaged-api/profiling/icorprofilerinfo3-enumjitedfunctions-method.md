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
ms.openlocfilehash: 7525d107fec7229d9b86eee63bde2aaf2d701b1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000649"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="c13bc-102">Metodo ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="c13bc-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="c13bc-103">Restituisce un enumeratore per tutte le funzioni che erano in precedenza a compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="c13bc-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c13bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c13bc-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c13bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c13bc-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c13bc-106">[out] Un puntatore per il [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c13bc-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c13bc-107">Note</span><span class="sxs-lookup"><span data-stu-id="c13bc-107">Remarks</span></span>  
 <span data-ttu-id="c13bc-108">Questo metodo potrebbe sovrapporsi `JITCompilation` callback, ad esempio il [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c13bc-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="c13bc-109">Enumeratore restituito da questo metodo non include le funzioni caricate da immagini native generate con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="c13bc-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c13bc-110">Enumerazione restituita include solo "0" per il valore della `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="c13bc-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="c13bc-111">Se è necessario validi `COR_PRF_FUNCTION::reJitId` valori, usare il [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c13bc-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13bc-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c13bc-112">Requirements</span></span>  
 <span data-ttu-id="c13bc-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c13bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c13bc-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c13bc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c13bc-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c13bc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c13bc-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c13bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13bc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c13bc-117">See also</span></span>

- [<span data-ttu-id="c13bc-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="c13bc-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c13bc-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c13bc-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c13bc-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="c13bc-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
