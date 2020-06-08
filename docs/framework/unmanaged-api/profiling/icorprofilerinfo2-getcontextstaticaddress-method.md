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
ms.openlocfilehash: 7550caaa7cb4d7ed77dc36ecf0ce0e0cbc541db7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497062"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="53c6f-102">Metodo ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="53c6f-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="53c6f-103">Ottiene l'indirizzo per il campo statico del contesto specificato nell'ambito del contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="53c6f-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53c6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53c6f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="53c6f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="53c6f-106">in ID della classe che contiene il campo statico di contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="53c6f-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="53c6f-107">in Token di metadati per il campo statico di contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="53c6f-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="53c6f-108">in ID del contesto che rappresenta l'ambito per il campo statico del contesto richiesto.</span><span class="sxs-lookup"><span data-stu-id="53c6f-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="53c6f-109">out Puntatore all'indirizzo del campo statico che si trova all'interno del contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="53c6f-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53c6f-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="53c6f-110">Remarks</span></span>  
 <span data-ttu-id="53c6f-111">Il `GetContextStaticAddress` metodo può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="53c6f-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="53c6f-112">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="53c6f-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="53c6f-113">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="53c6f-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="53c6f-114">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="53c6f-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="53c6f-115">Prima che il costruttore della classe di una classe venga completato, `GetContextStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e la radice Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="53c6f-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53c6f-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53c6f-116">Requirements</span></span>  
 <span data-ttu-id="53c6f-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53c6f-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53c6f-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53c6f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53c6f-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53c6f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53c6f-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53c6f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c6f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53c6f-121">See also</span></span>

- [<span data-ttu-id="53c6f-122">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="53c6f-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="53c6f-123">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="53c6f-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
