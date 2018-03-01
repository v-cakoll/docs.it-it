---
title: Metodo ICorProfilerInfo2::GetAppDomainStaticAddress
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
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fad6cccc3992f001780bf8bd1a4c879dc6aa754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="930b8-102">Metodo ICorProfilerInfo2::GetAppDomainStaticAddress</span><span class="sxs-lookup"><span data-stu-id="930b8-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="930b8-103">Ottiene l'indirizzo del campo statico a livello di dominio dell'applicazione specificata nell'ambito del dominio dell'applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="930b8-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="930b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="930b8-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="930b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="930b8-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="930b8-106">[in] L'ID della classe che contiene il campo statico a livello di dominio di applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="930b8-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="930b8-107">[in] Il token di metadati per il campo statico a livello di dominio di applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="930b8-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="930b8-108">[in] L'ID del dominio dell'applicazione che è l'ambito per il campo statico richiesto.</span><span class="sxs-lookup"><span data-stu-id="930b8-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="930b8-109">[out] Un puntatore all'indirizzo del campo statico è all'interno del dominio di applicazione specificata.</span><span class="sxs-lookup"><span data-stu-id="930b8-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="930b8-110">Note</span><span class="sxs-lookup"><span data-stu-id="930b8-110">Remarks</span></span>  
 <span data-ttu-id="930b8-111">Il `GetAppDomainStaticAddress` metodo può restituire uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="930b8-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="930b8-112">Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico indicato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="930b8-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="930b8-113">Gli indirizzi degli oggetti che possono trovarsi nell'heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="930b8-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="930b8-114">Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, pertanto dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="930b8-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="930b8-115">Prima che venga completato il costruttore di classe di una classe, `GetAppDomainStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbe già essere inizializzato e oggetti radice del garbage collection.</span><span class="sxs-lookup"><span data-stu-id="930b8-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="930b8-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="930b8-116">Requirements</span></span>  
 <span data-ttu-id="930b8-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="930b8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="930b8-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="930b8-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="930b8-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="930b8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="930b8-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="930b8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930b8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="930b8-121">See Also</span></span>  
 [<span data-ttu-id="930b8-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="930b8-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="930b8-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="930b8-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
