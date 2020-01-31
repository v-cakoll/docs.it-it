---
title: Interfaccia ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: e90a1ffbc037636e4296bbd4f4c3c5082885e9f3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863244"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="46b90-102">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="46b90-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="46b90-103">Sottoclasse di [ICorProfilerInfo9](icorprofilerinfo9-interface.md) che fornisce i metodi per modificare la funzione il, le informazioni di query dal runtime e sospendere e riprendere il Runtime.</span><span class="sxs-lookup"><span data-stu-id="46b90-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="46b90-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="46b90-104">Methods</span></span>  

| <span data-ttu-id="46b90-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="46b90-105">Method</span></span>|<span data-ttu-id="46b90-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46b90-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="46b90-107">Metodo EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="46b90-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="46b90-108">Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente).</span><span class="sxs-lookup"><span data-stu-id="46b90-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="46b90-109">Metodo IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="46b90-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="46b90-110">Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="46b90-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="46b90-111">Metodo GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="46b90-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="46b90-112">Ottiene il valore della soglia dell'oggetto LOH configurata.</span><span class="sxs-lookup"><span data-stu-id="46b90-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="46b90-113">Metodo RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="46b90-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="46b90-114">ReJITs i metodi richiesti, nonché tutti gli inliner dei metodi richiesti.</span><span class="sxs-lookup"><span data-stu-id="46b90-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="46b90-115">Metodo SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="46b90-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="46b90-116">Sospende il runtime senza eseguire un GC.</span><span class="sxs-lookup"><span data-stu-id="46b90-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="46b90-117">Metodo ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="46b90-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="46b90-118">Riprende il runtime senza eseguire un catalogo globale.</span><span class="sxs-lookup"><span data-stu-id="46b90-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="46b90-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="46b90-119">Requirements</span></span>  
<span data-ttu-id="46b90-120">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="46b90-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="46b90-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46b90-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="46b90-122">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46b90-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="46b90-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46b90-123">See also</span></span>

- [<span data-ttu-id="46b90-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="46b90-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
