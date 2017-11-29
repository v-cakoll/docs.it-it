---
title: Metodo ICorProfilerInfo2::GetRVAStaticAddress
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetRVAStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64553e8f611a8111aaaf9ababd1a7556f1192740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="53658-102">Metodo ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="53658-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="53658-103">Ottiene l'indirizzo del campo statico specificato indirizzi virtuali relativi (RVA).</span><span class="sxs-lookup"><span data-stu-id="53658-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53658-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53658-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53658-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="53658-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="53658-106">[in] L'ID della classe che contiene il campo statico RVA richiesto.</span><span class="sxs-lookup"><span data-stu-id="53658-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="53658-107">[in] Token di metadati per il campo statico RVA richiesto.</span><span class="sxs-lookup"><span data-stu-id="53658-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="53658-108">[out] Un puntatore all'indirizzo del campo statico RVA.</span><span class="sxs-lookup"><span data-stu-id="53658-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53658-109">Note</span><span class="sxs-lookup"><span data-stu-id="53658-109">Remarks</span></span>  
 <span data-ttu-id="53658-110">Il `GetRVAStaticAddress` metodo può restituire uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="53658-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="53658-111">Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico indicato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="53658-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="53658-112">Gli indirizzi degli oggetti che possono trovarsi nell'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="53658-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="53658-113">Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, pertanto dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="53658-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="53658-114">Prima che venga completato il costruttore di classe di una classe, `GetRVAStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbe già essere inizializzato e possono essere oggetti radice del garbage collection.</span><span class="sxs-lookup"><span data-stu-id="53658-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53658-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53658-115">Requirements</span></span>  
 <span data-ttu-id="53658-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53658-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53658-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53658-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53658-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53658-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53658-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53658-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53658-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53658-120">See Also</span></span>  
 [<span data-ttu-id="53658-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="53658-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="53658-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="53658-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
