---
title: Metodo ICorProfilerInfo::GetEventMask
ms.date: 03/30/2017
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
ms.openlocfilehash: 7faa4a5f7b1ca1fbf165c40eb3a3cb32a42a21a4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498336"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="58c94-102">Metodo ICorProfilerInfo::GetEventMask</span><span class="sxs-lookup"><span data-stu-id="58c94-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="58c94-103">Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="58c94-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c94-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58c94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c94-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58c94-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="58c94-106">[out] Puntatore a un valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="58c94-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="58c94-107">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="58c94-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="58c94-108">I bit sono descritti nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="58c94-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58c94-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="58c94-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58c94-110">È necessario chiamare il metodo [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) anziché questo metodo.</span><span class="sxs-lookup"><span data-stu-id="58c94-110">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="58c94-111">Anche se il `SetEventMask` Metodo continua a essere supportato, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) fornisce funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="58c94-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c94-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58c94-112">Requirements</span></span>  
 <span data-ttu-id="58c94-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58c94-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c94-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58c94-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58c94-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58c94-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58c94-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c94-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58c94-117">See also</span></span>

- [<span data-ttu-id="58c94-118">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="58c94-118">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="58c94-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="58c94-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
