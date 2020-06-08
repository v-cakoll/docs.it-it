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
ms.openlocfilehash: 525fa2efa39909390d874fb97d9f11e647340ea9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496945"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="6f6ff-102">Metodo ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="6f6ff-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="6f6ff-103">Ottiene l'indirizzo del campo statico dell'indirizzo RVA (relativo Virtual Address) specificato.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f6ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f6ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f6ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f6ff-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6f6ff-106">in ID della classe che contiene il campo RVA-static richiesto.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="6f6ff-107">in Token di metadati per il campo RVA-static richiesto.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="6f6ff-108">out Puntatore all'indirizzo del campo RVA-static.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f6ff-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6f6ff-109">Remarks</span></span>  
 <span data-ttu-id="6f6ff-110">Il `GetRVAStaticAddress` metodo può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="6f6ff-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="6f6ff-111">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="6f6ff-112">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="6f6ff-113">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="6f6ff-114">Prima che il costruttore della classe di una classe venga completato, `GetRVAStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, sebbene alcuni dei campi statici potrebbero essere già inizializzati e potrebbero essere radice Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="6f6ff-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f6ff-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f6ff-115">Requirements</span></span>  
 <span data-ttu-id="6f6ff-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f6ff-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f6ff-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f6ff-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f6ff-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f6ff-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f6ff-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f6ff-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f6ff-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f6ff-120">See also</span></span>

- [<span data-ttu-id="6f6ff-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6f6ff-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6f6ff-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="6f6ff-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
