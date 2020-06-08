---
title: 'Metodo ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: c7e53816c2f571fe6ff68b517ed827459a0f1562
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499090"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="9c268-102">Metodo ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="9c268-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="9c268-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="9c268-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="9c268-104">Notifica al profiler ogni volta che viene aggiornato il flusso di simboli associato a un modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="9c268-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c268-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c268-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c268-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c268-106">Parameters</span></span>  
 <span data-ttu-id="9c268-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="9c268-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="9c268-108">Identificatore del modulo in memoria di cui viene aggiornato il flusso di simboli.</span><span class="sxs-lookup"><span data-stu-id="9c268-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c268-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9c268-109">Remarks</span></span>  
 <span data-ttu-id="9c268-110">Questo callback viene controllato impostando il flag della maschera di evento [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) quando si chiama il metodo [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9c268-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c268-111">Questo evento non è attualmente generato per i simboli creati o modificati in modo implicito tramite le <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="9c268-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="9c268-112">Anche quando i simboli vengono forniti in primo piano in una chiamata a uno degli overload dei <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> metodi gestiti che includono un `rawSymbolStore` argomento per specificare i simboli per l'assembly, il runtime potrebbe non associare effettivamente i dati simbolici al modulo fino a quando non si è verificato il callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9c268-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="9c268-113">Questo evento consente di raccogliere i simboli per tali moduli in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="9c268-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c268-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c268-114">Requirements</span></span>  
 <span data-ttu-id="9c268-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c268-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c268-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c268-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c268-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c268-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c268-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c268-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c268-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c268-119">See also</span></span>

- [<span data-ttu-id="9c268-120">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="9c268-120">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="9c268-121">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="9c268-121">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="9c268-122">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="9c268-122">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)
