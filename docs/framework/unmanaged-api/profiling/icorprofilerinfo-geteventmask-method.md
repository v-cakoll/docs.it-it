---
title: Metodo ICorProfilerInfo::GetEventMask
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
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f8bfc0dc5686aa560bfa8282256b5e476976136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="fc83e-102">Metodo ICorProfilerInfo::GetEventMask</span><span class="sxs-lookup"><span data-stu-id="fc83e-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="fc83e-103">Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fc83e-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc83e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc83e-104">Syntax</span></span>  
  
```  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc83e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc83e-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="fc83e-106">[out] Puntatore a un valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="fc83e-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="fc83e-107">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="fc83e-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="fc83e-108">I bit sono descritti nel [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="fc83e-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc83e-109">Note</span><span class="sxs-lookup"><span data-stu-id="fc83e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc83e-110">È necessario chiamare il [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) metodo anziché di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="fc83e-110">You should call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="fc83e-111">Sebbene il `SetEventMask` metodo continua a essere supportato, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) fornisce funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="fc83e-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc83e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc83e-112">Requirements</span></span>  
 <span data-ttu-id="fc83e-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc83e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc83e-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc83e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc83e-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc83e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc83e-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc83e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc83e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc83e-117">See Also</span></span>  
 [<span data-ttu-id="fc83e-118">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="fc83e-118">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)  
 [<span data-ttu-id="fc83e-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fc83e-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
