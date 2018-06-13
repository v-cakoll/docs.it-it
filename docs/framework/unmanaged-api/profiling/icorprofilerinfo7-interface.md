---
title: Interfaccia ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79a722cd3318def36c20a49c1567c6f0d4989d39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455406"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="f054f-102">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="f054f-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="f054f-103">[Supportato in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="f054f-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="f054f-104">Una sottoclasse di [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) che fornisce un metodo per applicare appena definito i metadati per un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="f054f-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f054f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f054f-105">Methods</span></span>  
  
|<span data-ttu-id="f054f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="f054f-106">Method</span></span>|<span data-ttu-id="f054f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f054f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f054f-108">Metodo ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="f054f-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="f054f-109">Applica i metadati appena definito per il `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="f054f-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="f054f-110">Metodo GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="f054f-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="f054f-111">Restituisce la lunghezza di un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="f054f-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="f054f-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="f054f-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="f054f-113">Legge i byte dal flusso simbolo in memoria.</span><span class="sxs-lookup"><span data-stu-id="f054f-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f054f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f054f-114">Requirements</span></span>  
 <span data-ttu-id="f054f-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f054f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f054f-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f054f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f054f-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f054f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f054f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f054f-118">See Also</span></span>  
 [<span data-ttu-id="f054f-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f054f-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
