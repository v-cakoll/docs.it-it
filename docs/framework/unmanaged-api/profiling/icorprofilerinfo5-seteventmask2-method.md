---
title: Metodo ICorProfilerInfo5::SetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 1e1779c0f4f36b2d7b81832bc90cf5aee0b8a7df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130387"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="3b332-102">Metodo ICorProfilerInfo5::SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="3b332-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="3b332-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="3b332-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3b332-104">Imposta un valore che specifica i tipi di eventi per cui il profiler richiede la ricezione di notifiche da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3b332-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="3b332-105">Fornisce più funzionalità rispetto al metodo [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b332-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b332-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b332-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b332-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b332-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="3b332-108">[in] Valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="3b332-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="3b332-109">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="3b332-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="3b332-110">I bit sono descritti nell'enumerazione [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3b332-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="3b332-111">[in] Valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="3b332-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="3b332-112">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="3b332-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="3b332-113">I bit sono descritti nell'enumerazione [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3b332-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b332-114">Note</span><span class="sxs-lookup"><span data-stu-id="3b332-114">Remarks</span></span>  
 <span data-ttu-id="3b332-115">Il metodo `SetEventMask2` viene usato per impostare i callback per cui il profiler ha effettuato la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="3b332-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="3b332-116">In genere, si chiama il metodo [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) per determinare quali bit sono impostati, si eseguono un OR logico del relativo `pdwEventsLow` e `pdwEventsHigh` i valori e i nuovi bit che si desidera impostare, quindi si chiama il metodo di `SetEventMask2`.</span><span class="sxs-lookup"><span data-stu-id="3b332-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="3b332-117">Questo metodo è l'alternativa consigliata al metodo [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b332-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b332-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3b332-118">Requirements</span></span>  
 <span data-ttu-id="3b332-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b332-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b332-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b332-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b332-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b332-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b332-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b332-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b332-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b332-123">See also</span></span>

- [<span data-ttu-id="3b332-124">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="3b332-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="3b332-125">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="3b332-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
