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
ms.openlocfilehash: b9e404de96fa42509144904f5b2ff58e341578a9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740437"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="1a119-102">Metodo ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="1a119-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="1a119-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="1a119-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="1a119-104">Notifica al profiler ogni volta che viene aggiornato il flusso di simboli associato a un modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="1a119-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a119-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a119-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a119-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a119-106">Parameters</span></span>  
 <span data-ttu-id="1a119-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="1a119-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="1a119-108">Identificatore del modulo in memoria di cui viene aggiornato il flusso di simboli.</span><span class="sxs-lookup"><span data-stu-id="1a119-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a119-109">Note</span><span class="sxs-lookup"><span data-stu-id="1a119-109">Remarks</span></span>  
 <span data-ttu-id="1a119-110">Questo callback viene controllato impostando il flag della maschera di evento [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) quando si chiama il metodo [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1a119-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a119-111">Questo evento non è attualmente generato per i simboli creati o modificati in modo implicito tramite <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="1a119-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="1a119-112">Anche quando i simboli vengono forniti in primo piano in una chiamata a uno degli overload dei metodi <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> gestiti che includono un argomento `rawSymbolStore` per specificare i simboli per l'assembly, il runtime potrebbe non associare i dati simbolici al modulo fino a quando non si è verificato il callback [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1a119-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="1a119-113">Questo evento consente di raccogliere i simboli per tali moduli in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1a119-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a119-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1a119-114">Requirements</span></span>  
 <span data-ttu-id="1a119-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a119-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a119-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a119-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a119-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a119-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a119-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a119-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a119-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a119-119">See also</span></span>

- [<span data-ttu-id="1a119-120">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="1a119-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="1a119-121">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="1a119-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="1a119-122">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="1a119-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
