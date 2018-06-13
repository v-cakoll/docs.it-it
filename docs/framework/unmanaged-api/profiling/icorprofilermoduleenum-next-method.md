---
title: Metodo ICorProfilerModuleEnum::Next
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 974879b854f7a4c18aa4625ea88abb4953123f3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456150"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="e424d-102">Metodo ICorProfilerModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e424d-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="e424d-103">Ottiene il numero specificato di moduli contigui da una raccolta sequenziale di moduli, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="e424d-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e424d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e424d-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e424d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e424d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e424d-106">[in] Numero di moduli da recuperare.</span><span class="sxs-lookup"><span data-stu-id="e424d-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="e424d-107">[out] Matrice di valori `ModuleID`, ognuno dei quali rappresenta un modulo recuperato.</span><span class="sxs-lookup"><span data-stu-id="e424d-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e424d-108">[out] Puntatore al numero di elementi effettivamente restituiti nella matrice `ids`.</span><span class="sxs-lookup"><span data-stu-id="e424d-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e424d-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e424d-109">Return Value</span></span>  
 <span data-ttu-id="e424d-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="e424d-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e424d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e424d-111">HRESULT</span></span>|<span data-ttu-id="e424d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e424d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e424d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e424d-113">S_OK</span></span>|<span data-ttu-id="e424d-114">Sono stati restituiti `celt` elementi.</span><span class="sxs-lookup"><span data-stu-id="e424d-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="e424d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e424d-115">S_FALSE</span></span>|<span data-ttu-id="e424d-116">Sono stati restituiti meno di `celt` elementi, il che indica che l'enumerazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e424d-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e424d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e424d-117">Requirements</span></span>  
 <span data-ttu-id="e424d-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e424d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e424d-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e424d-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e424d-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e424d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e424d-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e424d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e424d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e424d-122">See Also</span></span>  
 [<span data-ttu-id="e424d-123">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="e424d-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="e424d-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="e424d-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
