---
title: Interfaccia ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175070"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="90eaf-102">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="90eaf-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="90eaf-103">Sottoclasse di [ICorProfilerInfo9](icorprofilerinfo9-interface.md) che fornisce metodi per modificare il linguaggio di controllo dell'attivazione delle funzioni, eseguire query sulle informazioni dal runtime e sospendere e riprendere il runtime.</span><span class="sxs-lookup"><span data-stu-id="90eaf-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="90eaf-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="90eaf-104">Methods</span></span>  

| <span data-ttu-id="90eaf-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="90eaf-105">Method</span></span>|<span data-ttu-id="90eaf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90eaf-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="90eaf-107">Metodo EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="90eaf-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="90eaf-108">Dato un ObjectID, callback e clientData, enumera ogni riferimento all'oggetto (se presente).</span><span class="sxs-lookup"><span data-stu-id="90eaf-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="90eaf-109">Metodo IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="90eaf-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="90eaf-110">Dato un ObjectID, determina se l'oggetto è in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="90eaf-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="90eaf-111">Metodo GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="90eaf-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="90eaf-112">Ottiene il valore della soglia LOH configurata.</span><span class="sxs-lookup"><span data-stu-id="90eaf-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="90eaf-113">Metodo RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="90eaf-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="90eaf-114">ReJITs i metodi richiesti, così come qualsiasi inliner s dei metodi richiesti.</span><span class="sxs-lookup"><span data-stu-id="90eaf-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="90eaf-115">Metodo SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="90eaf-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="90eaf-116">Sospende il runtime senza eseguire un catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="90eaf-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="90eaf-117">Metodo ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="90eaf-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="90eaf-118">Riprende il runtime senza eseguire un GC.</span><span class="sxs-lookup"><span data-stu-id="90eaf-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="90eaf-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90eaf-119">Requirements</span></span>  
<span data-ttu-id="90eaf-120">**Piattaforme:** Consultate [Sistemi operativi supportati da .NET Core.](../../../core/install/dependencies.md?pivots=os-windows)</span><span class="sxs-lookup"><span data-stu-id="90eaf-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="90eaf-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90eaf-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="90eaf-122">**Versioni .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90eaf-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="90eaf-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90eaf-123">See also</span></span>

- [<span data-ttu-id="90eaf-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="90eaf-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
