---
title: Metodo ICorProfilerInfo5::GetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: 758e5b71443b127c80c820eb8531056530e81b13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495697"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="797d8-102">Metodo ICorProfilerInfo5::GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="797d8-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="797d8-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="797d8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="797d8-104">Ottiene le categorie di eventi correnti per le quali il profiler richiede la ricezione delle notifiche da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="797d8-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="797d8-105">Fornisce funzionalità non fornite dal metodo [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="797d8-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="797d8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="797d8-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="797d8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="797d8-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="797d8-108">[out] Puntatore a un valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="797d8-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="797d8-109">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="797d8-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="797d8-110">I bit sono descritti nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="797d8-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="797d8-111">[out] Puntatore a un valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="797d8-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="797d8-112">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="797d8-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="797d8-113">I bit sono descritti nell'enumerazione [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="797d8-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="797d8-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="797d8-114">Remarks</span></span>  
 <span data-ttu-id="797d8-115">Il metodo `GetEventMask2` consente di determinare i callback a cui il profiler ha eseguito la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="797d8-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="797d8-116">In genere, si esegue un OR logico dei `pdwEventsLow` `pdwEventsHigh` valori e e i nuovi bit che si desidera impostare, quindi si chiama il metodo [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="797d8-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="797d8-117">Questo metodo è l'alternativa consigliata al metodo [GetEventMask](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="797d8-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="797d8-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="797d8-118">Requirements</span></span>  
 <span data-ttu-id="797d8-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="797d8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="797d8-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="797d8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="797d8-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="797d8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="797d8-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="797d8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="797d8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="797d8-123">See also</span></span>

- [<span data-ttu-id="797d8-124">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="797d8-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="797d8-125">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="797d8-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
