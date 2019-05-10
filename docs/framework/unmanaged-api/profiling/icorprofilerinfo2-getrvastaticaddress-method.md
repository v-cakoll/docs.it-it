---
title: Metodo ICorProfilerInfo2::GetRVAStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c2d1aee741ac54e861f7068d883731745ca7788
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584302"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="50305-102">Metodo ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="50305-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="50305-103">Ottiene l'indirizzo del campo statico specificato di indirizzo virtuale relativo (RVA).</span><span class="sxs-lookup"><span data-stu-id="50305-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50305-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50305-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50305-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="50305-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="50305-106">[in] L'ID della classe che contiene il campo statico RVA richiesto.</span><span class="sxs-lookup"><span data-stu-id="50305-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="50305-107">[in] Token di metadati per il campo statico RVA richiesto.</span><span class="sxs-lookup"><span data-stu-id="50305-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="50305-108">[out] Un puntatore all'indirizzo del campo statico RVA.</span><span class="sxs-lookup"><span data-stu-id="50305-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50305-109">Note</span><span class="sxs-lookup"><span data-stu-id="50305-109">Remarks</span></span>  
 <span data-ttu-id="50305-110">Il `GetRVAStaticAddress` metodo può restituire uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="50305-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="50305-111">Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="50305-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="50305-112">Gli indirizzi di oggetti che possono trovarsi nell'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="50305-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="50305-113">Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, in modo che dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="50305-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="50305-114">Prima del completamento, il costruttore di classe della classe `GetRVAStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i relativi campi statici, anche se alcuni dei campi statici potrebbero essere già stato inizializzato e possono essere oggetti radice del garbage collection.</span><span class="sxs-lookup"><span data-stu-id="50305-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50305-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50305-115">Requirements</span></span>  
 <span data-ttu-id="50305-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50305-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50305-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50305-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50305-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50305-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50305-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50305-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50305-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50305-120">See also</span></span>

- [<span data-ttu-id="50305-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="50305-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="50305-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="50305-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
