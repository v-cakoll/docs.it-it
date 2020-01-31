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
ms.openlocfilehash: 10e84b729c8af607165009a8591a69dbc1afcb1e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868382"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="b8b80-102">Metodo ICorProfilerInfo5::SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="b8b80-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="b8b80-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="b8b80-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b8b80-104">Imposta un valore che specifica i tipi di eventi per cui il profiler richiede la ricezione di notifiche da Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b8b80-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="b8b80-105">Fornisce più funzionalità rispetto al metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8b80-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b80-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8b80-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8b80-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8b80-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="b8b80-108">[in] Valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="b8b80-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="b8b80-109">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="b8b80-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="b8b80-110">I bit sono descritti nell'enumerazione [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b8b80-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="b8b80-111">[in] Valore a 4 byte che specifica le categorie di eventi.</span><span class="sxs-lookup"><span data-stu-id="b8b80-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="b8b80-112">Ogni bit controlla una funzionalità, un comportamento o un tipo di evento diverso.</span><span class="sxs-lookup"><span data-stu-id="b8b80-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="b8b80-113">I bit sono descritti nell'enumerazione [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b8b80-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8b80-114">Note</span><span class="sxs-lookup"><span data-stu-id="b8b80-114">Remarks</span></span>  
 <span data-ttu-id="b8b80-115">Il metodo `SetEventMask2` viene usato per impostare i callback per cui il profiler ha effettuato la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b8b80-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="b8b80-116">In genere, si chiama il metodo [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) per determinare quali bit sono impostati, si eseguono un OR logico del relativo `pdwEventsLow` e `pdwEventsHigh` i valori e i nuovi bit che si desidera impostare, quindi si chiama il metodo di `SetEventMask2`.</span><span class="sxs-lookup"><span data-stu-id="b8b80-116">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="b8b80-117">Questo metodo è l'alternativa consigliata al metodo [SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8b80-117">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8b80-118">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b8b80-118">Requirements</span></span>  
 <span data-ttu-id="b8b80-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8b80-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8b80-120">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8b80-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8b80-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8b80-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8b80-122">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8b80-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b80-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8b80-123">See also</span></span>

- [<span data-ttu-id="b8b80-124">Interfaccia ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="b8b80-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="b8b80-125">Metodo GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="b8b80-125">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
