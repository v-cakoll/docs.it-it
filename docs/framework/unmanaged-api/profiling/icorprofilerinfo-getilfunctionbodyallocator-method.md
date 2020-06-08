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
ms.openlocfilehash: 967f38add9ae5996c6ac33388203b55161a84e39
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498271"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="1de9b-102">Metodo ICorProfilerInfo::GetILFunctionBodyAllocator</span><span class="sxs-lookup"><span data-stu-id="1de9b-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="1de9b-103">Ottiene un'interfaccia che fornisce un metodo per allocare la memoria da utilizzare per lo swapping del corpo di un metodo nel codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="1de9b-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1de9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1de9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1de9b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="1de9b-106">in ID del modulo in cui risiede il metodo.</span><span class="sxs-lookup"><span data-stu-id="1de9b-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="1de9b-107">out Puntatore a un'interfaccia [IMethodMalloc](imethodmalloc-interface.md) che fornisce un metodo per allocare la memoria.</span><span class="sxs-lookup"><span data-stu-id="1de9b-107">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1de9b-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1de9b-108">Remarks</span></span>  
 <span data-ttu-id="1de9b-109">Il corpo di un metodo nel codice MSIL deve essere posizionato come un indirizzo RVA (relativo Virtual Address), relativo al modulo caricato, il che significa che segue il modulo entro 4 GB.</span><span class="sxs-lookup"><span data-stu-id="1de9b-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="1de9b-110">Per semplificare lo scambio del corpo di un metodo da parte di uno strumento, il `GetILFunctionBodyAllocator` metodo assicura che la memoria venga allocata all'interno di tale intervallo.</span><span class="sxs-lookup"><span data-stu-id="1de9b-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de9b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1de9b-111">Requirements</span></span>  
 <span data-ttu-id="1de9b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de9b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de9b-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1de9b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1de9b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1de9b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1de9b-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de9b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de9b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de9b-116">See also</span></span>

- [<span data-ttu-id="1de9b-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1de9b-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
