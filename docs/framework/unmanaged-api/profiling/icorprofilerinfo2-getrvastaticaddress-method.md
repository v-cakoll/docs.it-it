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
ms.openlocfilehash: ca64d4f5932fb4a0c0486fee5ca1017a6d3adaf2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868629"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="ccd54-102">Metodo ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="ccd54-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="ccd54-103">Ottiene l'indirizzo del campo statico dell'indirizzo RVA (relativo Virtual Address) specificato.</span><span class="sxs-lookup"><span data-stu-id="ccd54-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccd54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccd54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccd54-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ccd54-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ccd54-106">in ID della classe che contiene il campo RVA-static richiesto.</span><span class="sxs-lookup"><span data-stu-id="ccd54-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="ccd54-107">in Token di metadati per il campo RVA-static richiesto.</span><span class="sxs-lookup"><span data-stu-id="ccd54-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="ccd54-108">out Puntatore all'indirizzo del campo RVA-static.</span><span class="sxs-lookup"><span data-stu-id="ccd54-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccd54-109">Note</span><span class="sxs-lookup"><span data-stu-id="ccd54-109">Remarks</span></span>  
 <span data-ttu-id="ccd54-110">Il metodo `GetRVAStaticAddress` può restituire uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="ccd54-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="ccd54-111">CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="ccd54-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="ccd54-112">Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ccd54-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="ccd54-113">Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.</span><span class="sxs-lookup"><span data-stu-id="ccd54-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="ccd54-114">Prima del completamento del costruttore della classe di una classe, `GetRVAStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, sebbene alcuni dei campi statici potrebbero essere già stati inizializzati e potrebbero essere radice Garbage Collection oggetti.</span><span class="sxs-lookup"><span data-stu-id="ccd54-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccd54-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ccd54-115">Requirements</span></span>  
 <span data-ttu-id="ccd54-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccd54-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccd54-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ccd54-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ccd54-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccd54-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccd54-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccd54-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd54-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccd54-120">See also</span></span>

- [<span data-ttu-id="ccd54-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ccd54-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ccd54-122">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="ccd54-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
