---
title: Interfaccia ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 0e9f76717aeff27e863245faac241927e7495076
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495489"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="03ac6-102">Interfaccia ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="03ac6-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="03ac6-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="03ac6-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="03ac6-104">Sottoclasse di [ICorProfilerInfo6](icorprofilerinfo6-interface.md) che fornisce un metodo per applicare i metadati appena definiti a un modulo e che fornisce l'accesso a un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="03ac6-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03ac6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="03ac6-105">Methods</span></span>  
  
|<span data-ttu-id="03ac6-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="03ac6-106">Method</span></span>|<span data-ttu-id="03ac6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03ac6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03ac6-108">Metodo ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="03ac6-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="03ac6-109">Applica i metadati appena definiti dai `IMetadataEmit::Define*` metodi a un modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="03ac6-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="03ac6-110">Metodo GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="03ac6-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="03ac6-111">Restituisce la lunghezza di un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="03ac6-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="03ac6-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="03ac6-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="03ac6-113">Legge i byte da un flusso di simboli in memoria.</span><span class="sxs-lookup"><span data-stu-id="03ac6-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03ac6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03ac6-114">Requirements</span></span>  
 <span data-ttu-id="03ac6-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03ac6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03ac6-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03ac6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03ac6-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03ac6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ac6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03ac6-118">See also</span></span>

- [<span data-ttu-id="03ac6-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="03ac6-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
