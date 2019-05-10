---
title: Metodo ICorProfilerInfo2::GetContextStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02694933aca160e1f2c28554eb6758163ed8efc8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619934"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="1a5ac-102">Metodo ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="1a5ac-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="1a5ac-103">Ottiene l'indirizzo per il campo statico di contesto specificato che si trova nell'ambito del contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a5ac-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a5ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a5ac-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1a5ac-106">[in] ID della classe che contiene il campo statico di contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="1a5ac-107">[in] Il token di metadati per il campo statico di contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="1a5ac-108">[in] L'ID del contesto che è l'ambito per il campo statico di contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="1a5ac-109">[out] Un puntatore all'indirizzo del campo statico è all'interno del contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a5ac-110">Note</span><span class="sxs-lookup"><span data-stu-id="1a5ac-110">Remarks</span></span>  
 <span data-ttu-id="1a5ac-111">Il `GetContextStaticAddress` metodo può restituire uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a5ac-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="1a5ac-112">Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="1a5ac-113">Gli indirizzi di oggetti che possono trovarsi nell'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="1a5ac-114">Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, in modo che dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="1a5ac-115">Prima del completamento, il costruttore di classe della classe `GetContextStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i relativi campi statici, anche se alcuni dei campi statici potrebbero essere già stato inizializzato e oggetti radice del garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1a5ac-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a5ac-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a5ac-116">Requirements</span></span>  
 <span data-ttu-id="1a5ac-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a5ac-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a5ac-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a5ac-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a5ac-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a5ac-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a5ac-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a5ac-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a5ac-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a5ac-121">See also</span></span>

- [<span data-ttu-id="1a5ac-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1a5ac-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="1a5ac-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="1a5ac-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
