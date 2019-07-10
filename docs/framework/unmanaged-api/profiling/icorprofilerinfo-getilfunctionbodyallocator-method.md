---
title: Metodo ICorProfilerInfo::GetILFunctionBodyAllocator
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5651da4c0065a4ac479fe31e54225ee5df51b32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780614"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="4a0d5-102">Metodo ICorProfilerInfo::GetILFunctionBodyAllocator</span><span class="sxs-lookup"><span data-stu-id="4a0d5-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="4a0d5-103">Ottiene un'interfaccia che fornisce un metodo per allocare memoria da utilizzare per la sostituzione di corpo di un metodo in codice Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4a0d5-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a0d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a0d5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a0d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a0d5-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4a0d5-106">[in] L'ID del modulo in cui si trova il metodo.</span><span class="sxs-lookup"><span data-stu-id="4a0d5-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="4a0d5-107">[out] Un puntatore a un [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaccia che fornisce un metodo per allocare la memoria.</span><span class="sxs-lookup"><span data-stu-id="4a0d5-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a0d5-108">Note</span><span class="sxs-lookup"><span data-stu-id="4a0d5-108">Remarks</span></span>  
 <span data-ttu-id="4a0d5-109">Il corpo di un metodo in codice MSIL deve essere individuato come un indirizzo virtuale relativo (RVA), rispetto al modulo caricato, il che significa che segue il modulo all'interno di 4 GB.</span><span class="sxs-lookup"><span data-stu-id="4a0d5-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="4a0d5-110">Per renderne più semplice per uno strumento sostituire il corpo di un metodo, il `GetILFunctionBodyAllocator` metodo assicura che la memoria viene allocata all'interno dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="4a0d5-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a0d5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a0d5-111">Requirements</span></span>  
 <span data-ttu-id="4a0d5-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a0d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a0d5-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a0d5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a0d5-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a0d5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a0d5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a0d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0d5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a0d5-116">See also</span></span>

- [<span data-ttu-id="4a0d5-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="4a0d5-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
