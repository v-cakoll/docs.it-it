---
title: Interfaccia ICorProfilerInfo7
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13282bec74df5e6159148aa4fbe92a84d035e044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="3d90c-102">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="3d90c-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="3d90c-103">[Supportato in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="3d90c-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="3d90c-104">Una sottoclasse di [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) che fornisce un metodo per applicare appena definito i metadati per un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="3d90c-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d90c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3d90c-105">Methods</span></span>  
  
|<span data-ttu-id="3d90c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3d90c-106">Method</span></span>|<span data-ttu-id="3d90c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d90c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d90c-108">Metodo ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="3d90c-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="3d90c-109">Applica i metadati appena definito per il `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="3d90c-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="3d90c-110">Metodo GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="3d90c-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="3d90c-111">Restituisce la lunghezza di un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="3d90c-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="3d90c-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="3d90c-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="3d90c-113">Legge i byte dal flusso simbolo in memoria.</span><span class="sxs-lookup"><span data-stu-id="3d90c-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d90c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d90c-114">Requirements</span></span>  
 <span data-ttu-id="3d90c-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d90c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d90c-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d90c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d90c-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d90c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d90c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d90c-118">See Also</span></span>  
 [<span data-ttu-id="3d90c-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="3d90c-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
