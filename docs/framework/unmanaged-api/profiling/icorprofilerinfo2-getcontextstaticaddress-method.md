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
ms.openlocfilehash: d99e5000cdd0d7252764554025815dbace2289f4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868681"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="246ac-102">Metodo ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="246ac-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="246ac-103">Ottiene l'indirizzo per il campo statico del contesto specificato nell'ambito del contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="246ac-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="246ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="246ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="246ac-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="246ac-106">in ID della classe che contiene il campo statico di contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="246ac-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="246ac-107">in Token di metadati per il campo statico di contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="246ac-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="246ac-108">in ID del contesto che rappresenta l'ambito per il campo statico del contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="246ac-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="246ac-109">out Puntatore all'indirizzo del campo statico che si trova all'interno del contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="246ac-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="246ac-110">Note</span><span class="sxs-lookup"><span data-stu-id="246ac-110">Remarks</span></span>  
 <span data-ttu-id="246ac-111">Il metodo `GetContextStaticAddress` può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="246ac-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="246ac-112">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="246ac-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="246ac-113">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="246ac-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="246ac-114">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="246ac-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="246ac-115">Prima che il costruttore della classe di una classe venga completato, `GetContextStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e vengono radicati Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="246ac-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="246ac-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="246ac-116">Requirements</span></span>  
 <span data-ttu-id="246ac-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="246ac-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="246ac-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="246ac-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="246ac-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="246ac-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="246ac-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="246ac-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246ac-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="246ac-121">See also</span></span>

- [<span data-ttu-id="246ac-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="246ac-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="246ac-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="246ac-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
