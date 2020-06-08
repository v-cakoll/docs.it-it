---
title: Interfaccia ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: 9a49d8e1ff31942c6564ab560d6726b9ede26466
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499142"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="d58f8-102">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="d58f8-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="d58f8-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="d58f8-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d58f8-104">Sottoclasse di [ICorProfilerCallback6](icorprofilercallback6-interface.md) che fornisce un metodo callback usato da Common Language Runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d58f8-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d58f8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d58f8-105">Methods</span></span>  
  
|<span data-ttu-id="d58f8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d58f8-106">Method</span></span>|<span data-ttu-id="d58f8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d58f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d58f8-108">Metodo ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="d58f8-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="d58f8-109">Notifica al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d58f8-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d58f8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d58f8-110">Requirements</span></span>  
 <span data-ttu-id="d58f8-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d58f8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58f8-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d58f8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d58f8-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d58f8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58f8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d58f8-114">See also</span></span>

- [<span data-ttu-id="d58f8-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="d58f8-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
