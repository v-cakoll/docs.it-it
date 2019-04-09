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
ms.openlocfilehash: d10bb7033688efce9488078d2ef605e2a29382f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221414"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="22492-102">Metodo ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="22492-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="22492-103">Sostituisce il corpo della funzione specificata nel modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="22492-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22492-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22492-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22492-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22492-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="22492-106">[in] L'ID del modulo in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="22492-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="22492-107">[in] Il token della funzione per cui si desidera sostituire il corpo.</span><span class="sxs-lookup"><span data-stu-id="22492-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="22492-108">[in] La nuova intestazione per la funzione.</span><span class="sxs-lookup"><span data-stu-id="22492-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22492-109">Note</span><span class="sxs-lookup"><span data-stu-id="22492-109">Remarks</span></span>  
 <span data-ttu-id="22492-110">Il `SetILFunctionBody` metodo sostituisce l'indirizzo virtuale relativo della funzione nei metadati in modo che punti al nuovo corpo della funzione e consente di regolare le strutture di dati interno in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="22492-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="22492-111">Il `SetILFunctionBody` metodo può essere chiamato solo sulle funzioni che non sono stati compilati mai da un compilatore just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="22492-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="22492-112">Usare la [GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) metodo per allocare spazio per il nuovo metodo per assicurarsi che il buffer è compatibile.</span><span class="sxs-lookup"><span data-stu-id="22492-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22492-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22492-113">Requirements</span></span>  
 <span data-ttu-id="22492-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22492-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22492-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22492-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22492-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22492-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="22492-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="22492-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22492-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22492-118">See also</span></span>

- [<span data-ttu-id="22492-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="22492-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
