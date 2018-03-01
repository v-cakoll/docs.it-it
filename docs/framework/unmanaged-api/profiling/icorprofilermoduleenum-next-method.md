---
title: Metodo ICorProfilerModuleEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fca8a0f999ccc497c1929faa6cead04a1ec2774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="31778-102">Metodo ICorProfilerModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="31778-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="31778-103">Ottiene il numero specificato di moduli contigui da una raccolta sequenziale di moduli, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="31778-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31778-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31778-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31778-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31778-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="31778-106">[in] Numero di moduli da recuperare.</span><span class="sxs-lookup"><span data-stu-id="31778-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="31778-107">[out] Matrice di valori `ModuleID`, ognuno dei quali rappresenta un modulo recuperato.</span><span class="sxs-lookup"><span data-stu-id="31778-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="31778-108">[out] Puntatore al numero di elementi effettivamente restituiti nella matrice `ids`.</span><span class="sxs-lookup"><span data-stu-id="31778-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31778-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="31778-109">Return Value</span></span>  
 <span data-ttu-id="31778-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="31778-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="31778-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31778-111">HRESULT</span></span>|<span data-ttu-id="31778-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31778-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31778-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="31778-113">S_OK</span></span>|<span data-ttu-id="31778-114">Sono stati restituiti `celt` elementi.</span><span class="sxs-lookup"><span data-stu-id="31778-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="31778-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="31778-115">S_FALSE</span></span>|<span data-ttu-id="31778-116">Sono stati restituiti meno di `celt` elementi, il che indica che l'enumerazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="31778-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31778-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31778-117">Requirements</span></span>  
 <span data-ttu-id="31778-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31778-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31778-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31778-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31778-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31778-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31778-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31778-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31778-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31778-122">See Also</span></span>  
 [<span data-ttu-id="31778-123">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="31778-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="31778-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="31778-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
