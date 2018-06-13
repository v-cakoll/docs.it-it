---
title: Metodo ICorProfilerInfo2::GetThreadStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a38c8323157cee866ac0ecab97532b9b72a932b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454126"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="71d9d-102">Metodo ICorProfilerInfo2::GetThreadStaticAddress</span><span class="sxs-lookup"><span data-stu-id="71d9d-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="71d9d-103">Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="71d9d-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71d9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71d9d-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71d9d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71d9d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="71d9d-106">[in] L'ID della classe che contiene il campo statico a livello di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="71d9d-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="71d9d-107">[in] Il token di metadati per il campo statico a livello di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="71d9d-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="71d9d-108">[in] L'ID del thread che è l'ambito per il campo statico richiesto.</span><span class="sxs-lookup"><span data-stu-id="71d9d-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="71d9d-109">[out] Un puntatore all'indirizzo del campo statico che si trova all'interno di thread specificato.</span><span class="sxs-lookup"><span data-stu-id="71d9d-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71d9d-110">Note</span><span class="sxs-lookup"><span data-stu-id="71d9d-110">Remarks</span></span>  
 <span data-ttu-id="71d9d-111">Il `GetThreadStaticAddress` metodo può restituire uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d9d-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="71d9d-112">Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico indicato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="71d9d-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="71d9d-113">Gli indirizzi degli oggetti che possono trovarsi nell'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="71d9d-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="71d9d-114">Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, quindi dopo i profiler di garbage collection non devono presupporre che sono validi.</span><span class="sxs-lookup"><span data-stu-id="71d9d-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="71d9d-115">Prima che venga completato il costruttore di classe di una classe, `GetThreadStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbe già essere inizializzato e oggetti radice del garbage collection.</span><span class="sxs-lookup"><span data-stu-id="71d9d-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71d9d-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71d9d-116">Requirements</span></span>  
 <span data-ttu-id="71d9d-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71d9d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71d9d-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71d9d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71d9d-119">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="71d9d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71d9d-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71d9d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d9d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71d9d-121">See Also</span></span>  
 [<span data-ttu-id="71d9d-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="71d9d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="71d9d-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="71d9d-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
