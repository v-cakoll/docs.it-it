---
title: Metodo ICorProfilerFunctionEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Next Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd9c01e014ee19c5e30fdc293d39787638e8b1d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="a1fa2-102">Metodo ICorProfilerFunctionEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a1fa2-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="a1fa2-103">Ottiene il numero specificato di funzioni contigue da una raccolta sequenziale di funzioni, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1fa2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1fa2-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1fa2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1fa2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a1fa2-106">[in] Numero delle funzioni da recuperare.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="a1fa2-107">[out] Matrice di valori `COR_PRF_FUNCTION`, ognuno dei quali rappresenta una funzione recuperata.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a1fa2-108">[out] Puntatore al numero di funzioni effettivamente restituite nella matrice `ids`.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1fa2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1fa2-109">Return Value</span></span>  
 <span data-ttu-id="a1fa2-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a1fa2-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1fa2-111">HRESULT</span></span>|<span data-ttu-id="a1fa2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1fa2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1fa2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1fa2-113">S_OK</span></span>|<span data-ttu-id="a1fa2-114">Sono stati restituiti `celt` elementi.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="a1fa2-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a1fa2-115">S_FALSE</span></span>|<span data-ttu-id="a1fa2-116">Sono stati restituiti meno di `celt` elementi, il che indica che l'enumerazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1fa2-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1fa2-117">Requirements</span></span>  
 <span data-ttu-id="a1fa2-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1fa2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1fa2-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1fa2-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1fa2-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1fa2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1fa2-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1fa2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fa2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1fa2-122">See Also</span></span>  
 [<span data-ttu-id="a1fa2-123">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="a1fa2-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="a1fa2-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a1fa2-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
