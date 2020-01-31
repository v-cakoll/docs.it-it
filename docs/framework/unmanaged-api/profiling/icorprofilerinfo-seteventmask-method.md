---
title: Metodo ICorProfilerInfo::SetEventMask
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
ms.openlocfilehash: ed39411fa88c38da58e8a881c47d19b3b8c9ff8d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869278"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="abfc1-102">Metodo ICorProfilerInfo::SetEventMask</span><span class="sxs-lookup"><span data-stu-id="abfc1-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="abfc1-103">Imposta un valore che specifica i tipi di eventi per i quali il profiler richiede la ricezione della notifica da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="abfc1-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abfc1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abfc1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abfc1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="abfc1-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="abfc1-106">[in] Valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="abfc1-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="abfc1-107">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="abfc1-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="abfc1-108">I bit sono descritti nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="abfc1-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abfc1-109">Note</span><span class="sxs-lookup"><span data-stu-id="abfc1-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abfc1-110">È necessario chiamare il metodo [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) anziché questo metodo.</span><span class="sxs-lookup"><span data-stu-id="abfc1-110">You should call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="abfc1-111">Sebbene il metodo `SetEventMask` continui a essere supportato, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) fornisce funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="abfc1-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abfc1-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="abfc1-112">Requirements</span></span>  
 <span data-ttu-id="abfc1-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abfc1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abfc1-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="abfc1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="abfc1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abfc1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abfc1-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abfc1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfc1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abfc1-117">See also</span></span>

- [<span data-ttu-id="abfc1-118">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="abfc1-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="abfc1-119">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="abfc1-119">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
