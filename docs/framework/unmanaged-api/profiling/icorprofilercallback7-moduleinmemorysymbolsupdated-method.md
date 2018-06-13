---
title: Metodo ICorProfilerCallback7::ModuleInMemorySymbolsUpdated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9aa690378a32ffee2def672f02dc8b5582647a5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455814"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="bcdfc-102">Metodo ICorProfilerCallback7::ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="bcdfc-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="bcdfc-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="bcdfc-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="bcdfc-104">Notifica al profiler ogni volta che viene aggiornato il flusso di simboli associato a un modulo in memoria.</span><span class="sxs-lookup"><span data-stu-id="bcdfc-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcdfc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcdfc-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcdfc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bcdfc-106">Parameters</span></span>  
 <span data-ttu-id="bcdfc-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="bcdfc-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="bcdfc-108">L'identificatore del modulo in memoria flusso il cui simbolo è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="bcdfc-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcdfc-109">Note</span><span class="sxs-lookup"><span data-stu-id="bcdfc-109">Remarks</span></span>  
 <span data-ttu-id="bcdfc-110">Questo callback viene controllato impostando il [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) flag maschera eventi quando si chiama il [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="bcdfc-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcdfc-111">Questo evento non viene generato per i simboli in modo implicito creato o modificato tramite attualmente <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="bcdfc-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="bcdfc-112">Anche quando i simboli sono inizio in una chiamata a uno degli overload di gestito <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> metodi che include un `rawSymbolStore` argomento per specificare i simboli per l'assembly, il runtime potrebbe non effettivamente associare i dati sui simboli con il modulo fino a quando non dopo il [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback si è verificato.</span><span class="sxs-lookup"><span data-stu-id="bcdfc-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="bcdfc-113">Questo evento fornisce una versione successiva opportunità per raccogliere i simboli per tali moduli.</span><span class="sxs-lookup"><span data-stu-id="bcdfc-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcdfc-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcdfc-114">Requirements</span></span>  
 <span data-ttu-id="bcdfc-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcdfc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcdfc-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bcdfc-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bcdfc-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bcdfc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcdfc-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcdfc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcdfc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcdfc-119">See Also</span></span>  
 [<span data-ttu-id="bcdfc-120">Metodo ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="bcdfc-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="bcdfc-121">Metodo SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="bcdfc-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="bcdfc-122">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="bcdfc-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
