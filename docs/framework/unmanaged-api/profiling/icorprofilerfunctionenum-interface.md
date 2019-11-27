---
title: Interfaccia ICorProfilerFunctionEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
ms.openlocfilehash: 17f7243096b7ac18e456f8f31196055492015346
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447804"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="891bb-102">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="891bb-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="891bb-103">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="891bb-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="891bb-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="891bb-104">Methods</span></span>  
  
|<span data-ttu-id="891bb-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="891bb-105">Method</span></span>|<span data-ttu-id="891bb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="891bb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="891bb-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="891bb-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="891bb-108">Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="891bb-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="891bb-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="891bb-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="891bb-110">Ottiene il numero di funzioni che sono state caricate dall'applicazione o caricate forzatamente dal profiler.</span><span class="sxs-lookup"><span data-stu-id="891bb-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="891bb-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="891bb-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="891bb-112">Ottiene il numero specificato di funzioni contigue da una raccolta sequenziale di funzioni, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="891bb-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="891bb-113">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="891bb-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="891bb-114">Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.</span><span class="sxs-lookup"><span data-stu-id="891bb-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="891bb-115">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="891bb-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="891bb-116">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="891bb-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="891bb-117">Note</span><span class="sxs-lookup"><span data-stu-id="891bb-117">Remarks</span></span>  
 <span data-ttu-id="891bb-118">L'interfaccia `ICorProfilerFunctionEnum` è un enumeratore.</span><span class="sxs-lookup"><span data-stu-id="891bb-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="891bb-119">Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore.</span><span class="sxs-lookup"><span data-stu-id="891bb-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="891bb-120">In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi della matrice, evitando così i problemi associati al passaggio di matrici di grandi dimensioni come parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="891bb-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="891bb-121">`ICorProfilerFunctionEnum` enumera le funzioni che sono già state compilate tramite JIT, ma non include funzioni caricate da immagini native generate con Ngen. exe.</span><span class="sxs-lookup"><span data-stu-id="891bb-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="891bb-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="891bb-122">Requirements</span></span>  
 <span data-ttu-id="891bb-123">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="891bb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="891bb-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="891bb-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="891bb-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="891bb-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="891bb-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="891bb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891bb-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="891bb-127">See also</span></span>

- [<span data-ttu-id="891bb-128">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="891bb-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="891bb-129">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="891bb-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="891bb-130">Metodo EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="891bb-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
