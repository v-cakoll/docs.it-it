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
ms.openlocfilehash: 5fe472c4a0053ec9e37d7d61ffde5cf21d65dd2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863491"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="d3891-102">Metodo ICorProfilerInfo::GetILFunctionBodyAllocator</span><span class="sxs-lookup"><span data-stu-id="d3891-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="d3891-103">Ottiene un'interfaccia che fornisce un metodo per allocare la memoria da utilizzare per lo swapping del corpo di un metodo nel codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="d3891-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3891-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3891-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3891-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3891-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d3891-106">in ID del modulo in cui risiede il metodo.</span><span class="sxs-lookup"><span data-stu-id="d3891-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="d3891-107">out Puntatore a un'interfaccia [IMethodMalloc](imethodmalloc-interface.md) che fornisce un metodo per allocare la memoria.</span><span class="sxs-lookup"><span data-stu-id="d3891-107">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3891-108">Note</span><span class="sxs-lookup"><span data-stu-id="d3891-108">Remarks</span></span>  
 <span data-ttu-id="d3891-109">Il corpo di un metodo nel codice MSIL deve essere posizionato come un indirizzo RVA (relativo Virtual Address), relativo al modulo caricato, il che significa che segue il modulo entro 4 GB.</span><span class="sxs-lookup"><span data-stu-id="d3891-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="d3891-110">Per semplificare lo scambio del corpo di un metodo da parte di uno strumento, il `GetILFunctionBodyAllocator` metodo garantisce che la memoria venga allocata all'interno di tale intervallo.</span><span class="sxs-lookup"><span data-stu-id="d3891-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3891-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d3891-111">Requirements</span></span>  
 <span data-ttu-id="d3891-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3891-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3891-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3891-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3891-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3891-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3891-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3891-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3891-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3891-116">See also</span></span>

- [<span data-ttu-id="d3891-117">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d3891-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
