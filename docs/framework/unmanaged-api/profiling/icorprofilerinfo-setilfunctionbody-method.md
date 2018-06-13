---
title: Metodo ICorProfilerInfo::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 886bb706be30481c082012bf057a001f37903b16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461656"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="305ce-102">Metodo ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="305ce-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="305ce-103">Sostituisce il corpo della funzione specificata nel modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="305ce-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="305ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="305ce-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="305ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="305ce-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="305ce-106">[in] L'ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="305ce-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="305ce-107">[in] Il token della funzione per cui si desidera sostituire il corpo.</span><span class="sxs-lookup"><span data-stu-id="305ce-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="305ce-108">[in] Nuova intestazione per la funzione.</span><span class="sxs-lookup"><span data-stu-id="305ce-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="305ce-109">Note</span><span class="sxs-lookup"><span data-stu-id="305ce-109">Remarks</span></span>  
 <span data-ttu-id="305ce-110">Il `SetILFunctionBody` metodo sostituisce l'indirizzo virtuale relativo della funzione nei metadati in modo che punti al nuovo corpo della funzione e regola le strutture di dati interno in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="305ce-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="305ce-111">Il `SetILFunctionBody` metodo può essere chiamato solo sulle funzioni che non sono mai stati compilati da un compilatore just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="305ce-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="305ce-112">Utilizzare il [ICorProfilerInfo:: GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) per allocare spazio per il nuovo metodo per assicurarsi che il buffer è compatibile.</span><span class="sxs-lookup"><span data-stu-id="305ce-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="305ce-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="305ce-113">Requirements</span></span>  
 <span data-ttu-id="305ce-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="305ce-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="305ce-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="305ce-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="305ce-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="305ce-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="305ce-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="305ce-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305ce-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="305ce-118">See Also</span></span>  
 [<span data-ttu-id="305ce-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="305ce-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
