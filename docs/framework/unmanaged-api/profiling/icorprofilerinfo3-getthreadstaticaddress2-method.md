---
title: Metodo ICorProfilerInfo3::GetThreadStaticAddress2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
ms.openlocfilehash: ee44c89ec30edcb6233081f0757fa0f7b7191178
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449639"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="c6f72-102">Metodo ICorProfilerInfo3::GetThreadStaticAddress2</span><span class="sxs-lookup"><span data-stu-id="c6f72-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="c6f72-103">Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del dominio dell'applicazione e del thread specificati.</span><span class="sxs-lookup"><span data-stu-id="c6f72-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f72-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6f72-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f72-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6f72-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c6f72-106">in ID della classe che contiene il campo statico di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="c6f72-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="c6f72-107">in Token di metadati per il campo statico di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="c6f72-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="c6f72-108">[in] ID del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6f72-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="c6f72-109">in ID del thread che rappresenta l'ambito per il campo statico richiesto.</span><span class="sxs-lookup"><span data-stu-id="c6f72-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="c6f72-110">out Puntatore all'indirizzo del campo statico che si trova all'interno del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="c6f72-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6f72-111">Note</span><span class="sxs-lookup"><span data-stu-id="c6f72-111">Remarks</span></span>  
 <span data-ttu-id="c6f72-112">Il metodo `GetThreadStaticAddress2` può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="c6f72-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
- <span data-ttu-id="c6f72-113">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="c6f72-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="c6f72-114">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c6f72-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="c6f72-115">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="c6f72-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="c6f72-116">Prima che il costruttore della classe di una classe venga completato, `GetThreadStaticAddress2` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e vengono radicati Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="c6f72-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="c6f72-117">Il metodo [ICorProfilerInfo2:: GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) è simile al metodo `GetThreadStaticAddress2`, ma non accetta un argomento del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6f72-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f72-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6f72-118">Requirements</span></span>  
 <span data-ttu-id="c6f72-119">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6f72-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f72-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6f72-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6f72-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6f72-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6f72-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f72-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f72-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6f72-123">See also</span></span>

- [<span data-ttu-id="c6f72-124">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="c6f72-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c6f72-125">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c6f72-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c6f72-126">Profilatura</span><span class="sxs-lookup"><span data-stu-id="c6f72-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
