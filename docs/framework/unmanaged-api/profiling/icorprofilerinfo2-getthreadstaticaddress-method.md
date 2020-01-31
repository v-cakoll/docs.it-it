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
ms.openlocfilehash: 2c98f67e20ea36d7fbbb31be2e3761594b674c36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868603"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="0c563-102">Metodo ICorProfilerInfo2::GetThreadStaticAddress</span><span class="sxs-lookup"><span data-stu-id="0c563-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="0c563-103">Ottiene l'indirizzo del campo statico del thread specificato nell'ambito del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="0c563-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c563-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c563-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c563-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c563-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0c563-106">in ID della classe che contiene il campo statico di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="0c563-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="0c563-107">in Token di metadati per il campo statico di thread richiesto.</span><span class="sxs-lookup"><span data-stu-id="0c563-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="0c563-108">in ID del thread che rappresenta l'ambito per il campo statico richiesto.</span><span class="sxs-lookup"><span data-stu-id="0c563-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="0c563-109">out Puntatore all'indirizzo del campo statico che si trova all'interno del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="0c563-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c563-110">Note</span><span class="sxs-lookup"><span data-stu-id="0c563-110">Remarks</span></span>  
 <span data-ttu-id="0c563-111">Il metodo `GetThreadStaticAddress` può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="0c563-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="0c563-112">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="0c563-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="0c563-113">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0c563-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="0c563-114">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo che Garbage Collection Profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="0c563-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="0c563-115">Prima che il costruttore della classe di una classe venga completato, `GetThreadStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e vengono radicati Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="0c563-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c563-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0c563-116">Requirements</span></span>  
 <span data-ttu-id="0c563-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c563-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c563-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c563-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c563-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c563-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c563-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c563-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c563-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c563-121">See also</span></span>

- [<span data-ttu-id="0c563-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0c563-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="0c563-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="0c563-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
