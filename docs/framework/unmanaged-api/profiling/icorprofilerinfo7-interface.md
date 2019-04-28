---
title: Interfaccia ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8586031c5bcb0303a64b67ee601fe41b81ee3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786243"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="b8456-102">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="b8456-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="b8456-103">[Supportato in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="b8456-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="b8456-104">Una sottoclasse [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) che fornisce un metodo per applicare appena definito i metadati per un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="b8456-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8456-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b8456-105">Methods</span></span>  
  
|<span data-ttu-id="b8456-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b8456-106">Method</span></span>|<span data-ttu-id="b8456-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8456-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8456-108">Metodo ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="b8456-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="b8456-109">Applica i metadati appena definito dal `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="b8456-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="b8456-110">Metodo GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="b8456-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="b8456-111">Restituisce la lunghezza di un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="b8456-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="b8456-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="b8456-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="b8456-113">Legge i byte da un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="b8456-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8456-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8456-114">Requirements</span></span>  
 <span data-ttu-id="b8456-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8456-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8456-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8456-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8456-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8456-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8456-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8456-118">See also</span></span>

- [<span data-ttu-id="b8456-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b8456-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
