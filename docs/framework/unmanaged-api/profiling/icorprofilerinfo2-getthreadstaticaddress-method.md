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
ms.openlocfilehash: 3df6e4decf1c4641116dee5fab3ca83189b427c0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496763"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="5f655-102">Metodo ICorProfilerInfo2::GetThreadStaticAddress</span><span class="sxs-lookup"><span data-stu-id="5f655-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="5f655-103">Ottiene l'indirizzo del campo statico del thread specificato nell'ambito del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="5f655-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f655-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f655-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f655-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f655-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5f655-106">in ID della classe che contiene il campo statico di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="5f655-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="5f655-107">in Token di metadati per il campo statico di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="5f655-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="5f655-108">in ID del thread che rappresenta l'ambito per il campo statico richiesto.</span><span class="sxs-lookup"><span data-stu-id="5f655-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="5f655-109">out Puntatore all'indirizzo del campo statico che si trova all'interno del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="5f655-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f655-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5f655-110">Remarks</span></span>  
 <span data-ttu-id="5f655-111">Il `GetThreadStaticAddress` metodo può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="5f655-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="5f655-112">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="5f655-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="5f655-113">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="5f655-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="5f655-114">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo che Garbage Collection Profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="5f655-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="5f655-115">Prima che il costruttore della classe di una classe venga completato, `GetThreadStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e la radice Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="5f655-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f655-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f655-116">Requirements</span></span>  
 <span data-ttu-id="5f655-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f655-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f655-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f655-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f655-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f655-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f655-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f655-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f655-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f655-121">See also</span></span>

- [<span data-ttu-id="5f655-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5f655-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="5f655-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="5f655-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
