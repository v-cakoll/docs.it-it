---
title: Metodo ICorProfilerInfo3::GetThreadStaticAddress2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d657f0d6a28f19c45910fa354b7b40822ad12947
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="155a5-102">Metodo ICorProfilerInfo3::GetThreadStaticAddress2</span><span class="sxs-lookup"><span data-stu-id="155a5-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="155a5-103">Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del dominio dell'applicazione e del thread specificati.</span><span class="sxs-lookup"><span data-stu-id="155a5-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="155a5-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="155a5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="155a5-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="155a5-106">[in] L'ID della classe che contiene il campo statico a livello di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="155a5-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="155a5-107">[in] Il token di metadati per il campo statico a livello di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="155a5-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="155a5-108">[in] ID del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="155a5-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="155a5-109">[in] L'ID del thread che è l'ambito per il campo statico richiesto.</span><span class="sxs-lookup"><span data-stu-id="155a5-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="155a5-110">[out] Un puntatore all'indirizzo del campo statico che si trova all'interno di thread specificato.</span><span class="sxs-lookup"><span data-stu-id="155a5-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="155a5-111">Note</span><span class="sxs-lookup"><span data-stu-id="155a5-111">Remarks</span></span>  
 <span data-ttu-id="155a5-112">Il `GetThreadStaticAddress2` metodo può restituire uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="155a5-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="155a5-113">Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico indicato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="155a5-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="155a5-114">Gli indirizzi degli oggetti che possono trovarsi nell'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="155a5-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="155a5-115">Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, pertanto dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="155a5-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="155a5-116">Prima che venga completato il costruttore di classe di una classe, `GetThreadStaticAddress2` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbe già essere inizializzato e oggetti radice del garbage collection.</span><span class="sxs-lookup"><span data-stu-id="155a5-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="155a5-117">Il [ICorProfilerInfo2:: GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) è simile al metodo di `GetThreadStaticAddress2` (metodo), ma non accetta un argomento del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="155a5-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="155a5-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="155a5-118">Requirements</span></span>  
 <span data-ttu-id="155a5-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="155a5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="155a5-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="155a5-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="155a5-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="155a5-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="155a5-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="155a5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155a5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155a5-123">See Also</span></span>  
 [<span data-ttu-id="155a5-124">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="155a5-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="155a5-125">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="155a5-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="155a5-126">Profilatura</span><span class="sxs-lookup"><span data-stu-id="155a5-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
