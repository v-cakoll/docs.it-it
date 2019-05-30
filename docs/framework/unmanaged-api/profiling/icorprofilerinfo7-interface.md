---
title: Interfaccia ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a734bfdef89d4f8f9459f49a3ce2cee83faef9f6
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250983"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="f84ec-102">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="f84ec-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="f84ec-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="f84ec-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f84ec-104">Una sottoclasse [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) che fornisce un metodo per applicare appena definito i metadati per un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="f84ec-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f84ec-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f84ec-105">Methods</span></span>  
  
|<span data-ttu-id="f84ec-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="f84ec-106">Method</span></span>|<span data-ttu-id="f84ec-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f84ec-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f84ec-108">Metodo ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="f84ec-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="f84ec-109">Applica i metadati appena definito dal `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="f84ec-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="f84ec-110">Metodo GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="f84ec-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="f84ec-111">Restituisce la lunghezza di un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="f84ec-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="f84ec-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="f84ec-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="f84ec-113">Legge i byte da un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="f84ec-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f84ec-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f84ec-114">Requirements</span></span>  
 <span data-ttu-id="f84ec-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f84ec-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f84ec-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f84ec-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f84ec-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f84ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f84ec-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f84ec-118">See also</span></span>

- [<span data-ttu-id="f84ec-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f84ec-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
