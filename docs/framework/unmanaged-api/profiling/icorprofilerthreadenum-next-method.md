---
title: Metodo ICorProfilerThreadEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Next
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3295f3dc9af50fb62a2008f59819a51a6032a48b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="ea477-102">Metodo ICorProfilerThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ea477-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="ea477-103">Ottiene il numero specificato di thread contigui da una raccolta sequenziale di moduli, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="ea477-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea477-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea477-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea477-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea477-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ea477-106">[in] Numero di thread da recuperare.</span><span class="sxs-lookup"><span data-stu-id="ea477-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="ea477-107">[out] Matrice di valori `ThreadID`, ognuno dei quali rappresenta un thread recuperato.</span><span class="sxs-lookup"><span data-stu-id="ea477-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ea477-108">[out] Puntatore al numero di thread effettivamente restituiti nella matrice `ids`.</span><span class="sxs-lookup"><span data-stu-id="ea477-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea477-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ea477-109">Return Value</span></span>  
 <span data-ttu-id="ea477-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="ea477-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ea477-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea477-111">HRESULT</span></span>|<span data-ttu-id="ea477-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea477-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea477-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea477-113">S_OK</span></span>|<span data-ttu-id="ea477-114">Sono stati restituiti `celt` elementi.</span><span class="sxs-lookup"><span data-stu-id="ea477-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="ea477-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ea477-115">S_FALSE</span></span>|<span data-ttu-id="ea477-116">Sono stati restituiti meno di `celt` elementi, il che indica che l'enumerazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ea477-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea477-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea477-117">Requirements</span></span>  
 <span data-ttu-id="ea477-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea477-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea477-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ea477-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea477-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea477-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea477-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea477-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea477-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea477-122">See Also</span></span>  
 [<span data-ttu-id="ea477-123">ICorProfilerThreadEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ea477-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="ea477-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="ea477-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
