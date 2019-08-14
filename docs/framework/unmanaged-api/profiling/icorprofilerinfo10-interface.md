---
title: Interfaccia ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 496959ecac5b16f1faa138aec90c5194d15cb105
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974011"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="d4a64-102">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="d4a64-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="d4a64-103">Sottoclasse di [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) che fornisce i metodi per modificare la funzione il, le informazioni di query dal runtime e sospendere e riprendere il Runtime.</span><span class="sxs-lookup"><span data-stu-id="d4a64-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="d4a64-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d4a64-104">Methods</span></span>  

| <span data-ttu-id="d4a64-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d4a64-105">Method</span></span>|<span data-ttu-id="d4a64-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4a64-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="d4a64-107">Metodo EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="d4a64-107">EnumerateObjectReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="d4a64-108">Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente).</span><span class="sxs-lookup"><span data-stu-id="d4a64-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="d4a64-109">Metodo IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="d4a64-109">IsFrozenObject Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="d4a64-110">Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d4a64-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="d4a64-111">Metodo GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="d4a64-111">GetLOHObjectSizeThreshold Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="d4a64-112">Ottiene il valore della soglia dell'oggetto LOH configurata.</span><span class="sxs-lookup"><span data-stu-id="d4a64-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="d4a64-113">Metodo RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="d4a64-113">RequestReJITWithInliners Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="d4a64-114">ReJITs i metodi richiesti, nonché tutti gli inliner dei metodi richiesti.</span><span class="sxs-lookup"><span data-stu-id="d4a64-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="d4a64-115">Metodo SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="d4a64-115">SuspendRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="d4a64-116">Sospende il runtime senza eseguire un GC.</span><span class="sxs-lookup"><span data-stu-id="d4a64-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="d4a64-117">Metodo ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="d4a64-117">ResumeRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="d4a64-118">Riprende il runtime senza eseguire un catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="d4a64-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="d4a64-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4a64-119">Requirements</span></span>  
<span data-ttu-id="d4a64-120">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="d4a64-120">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="d4a64-121">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="d4a64-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="d4a64-122">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4a64-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
## <a name="see-also"></a><span data-ttu-id="d4a64-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4a64-123">See also</span></span>
- [<span data-ttu-id="d4a64-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="d4a64-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
