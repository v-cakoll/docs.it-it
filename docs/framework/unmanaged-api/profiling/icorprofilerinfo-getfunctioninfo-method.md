---
title: Metodo ICorProfilerInfo::GetFunctionInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
ms.openlocfilehash: e7193526bb0da1d28da4bf6bde108fc4d3fba273
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503016"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="d4939-102">Metodo ICorProfilerInfo::GetFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="d4939-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="d4939-103">Ottiene la classe padre e il token di metadati per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="d4939-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4939-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4939-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4939-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4939-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d4939-106">in ID della funzione per cui ottenere la classe padre e il token di metadati.</span><span class="sxs-lookup"><span data-stu-id="d4939-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="d4939-107">[out] Puntatore alla classe padre della funzione.</span><span class="sxs-lookup"><span data-stu-id="d4939-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="d4939-108">[out] Puntatore al modulo in cui è definita la classe padre della funzione.</span><span class="sxs-lookup"><span data-stu-id="d4939-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="d4939-109">[out] Puntatore al token di metadati per la funzione.</span><span class="sxs-lookup"><span data-stu-id="d4939-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4939-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d4939-110">Remarks</span></span>  
 <span data-ttu-id="d4939-111">Il codice del profiler può chiamare [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) per ottenere un'interfaccia di metadati per un determinato modulo.</span><span class="sxs-lookup"><span data-stu-id="d4939-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="d4939-112">Il token di metadati restituito nella posizione a cui fa riferimento `pToken` può quindi essere usato per accedere ai metadati per la funzione.</span><span class="sxs-lookup"><span data-stu-id="d4939-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="d4939-113">Il `ClassID` di una funzione in una classe generica potrebbe non essere ottenibile senza informazioni contestuali sull'uso della funzione.</span><span class="sxs-lookup"><span data-stu-id="d4939-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="d4939-114">In questo caso, `pClassId` sarà 0.</span><span class="sxs-lookup"><span data-stu-id="d4939-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="d4939-115">Il codice del profiler deve usare [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) con un valore COR_PRF_FRAME_INFO per fornire un contesto maggiore.</span><span class="sxs-lookup"><span data-stu-id="d4939-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4939-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4939-116">Requirements</span></span>  
 <span data-ttu-id="d4939-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4939-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4939-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d4939-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4939-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4939-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4939-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4939-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4939-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4939-121">See also</span></span>

- [<span data-ttu-id="d4939-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d4939-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
