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
ms.openlocfilehash: e61f6a104b8b9613db32ed6912395fd07c18dcff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864817"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="c7375-102">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="c7375-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="c7375-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="c7375-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="c7375-104">Sottoclasse di [ICorProfilerCallback6](icorprofilercallback6-interface.md) che fornisce un metodo callback usato da Common Language Runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c7375-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7375-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="c7375-105">Methods</span></span>  
  
|<span data-ttu-id="c7375-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="c7375-106">Method</span></span>|<span data-ttu-id="c7375-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7375-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7375-108">Metodo ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="c7375-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="c7375-109">Notifica al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="c7375-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7375-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c7375-110">Requirements</span></span>  
 <span data-ttu-id="c7375-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7375-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7375-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7375-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7375-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7375-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7375-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7375-114">See also</span></span>

- [<span data-ttu-id="c7375-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="c7375-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
