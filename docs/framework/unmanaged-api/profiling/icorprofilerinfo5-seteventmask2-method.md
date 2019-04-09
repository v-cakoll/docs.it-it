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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266219894ffefa0d4066c6ca68c7cadf6265e098
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175812"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="b5d32-102">Metodo ICorProfilerInfo5::SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="b5d32-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="b5d32-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="b5d32-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b5d32-104">Imposta un valore che specifica i tipi di eventi per cui il profiler richiede la ricezione di notifiche da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b5d32-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="b5d32-105">Offre maggiori funzionalità rispetto al [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b5d32-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5d32-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5d32-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5d32-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5d32-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="b5d32-108">[in] Valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="b5d32-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="b5d32-109">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="b5d32-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="b5d32-110">I bit sono descritti nel [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b5d32-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="b5d32-111">[in] Valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="b5d32-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="b5d32-112">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="b5d32-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="b5d32-113">I bit sono descritti nel [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b5d32-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5d32-114">Note</span><span class="sxs-lookup"><span data-stu-id="b5d32-114">Remarks</span></span>  
 <span data-ttu-id="b5d32-115">Il metodo `SetEventMask2` viene usato per impostare i callback per cui il profiler ha effettuato la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b5d32-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="b5d32-116">In genere, si chiama il [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) metodo per determinare quali bit sono impostati, eseguire un OR logico dei relativi `pdwEventsLow` e `pdwEventsHigh` valori e dei nuovi bit si desidera impostare, quindi chiamare il `SetEventMask2` (metodo).</span><span class="sxs-lookup"><span data-stu-id="b5d32-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="b5d32-117">Questo metodo è l'alternativa consigliata per la [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b5d32-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5d32-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5d32-118">Requirements</span></span>  
 <span data-ttu-id="b5d32-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5d32-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5d32-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5d32-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5d32-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5d32-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b5d32-122">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b5d32-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b5d32-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5d32-123">See also</span></span>

- [<span data-ttu-id="b5d32-124">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="b5d32-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="b5d32-125">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="b5d32-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
