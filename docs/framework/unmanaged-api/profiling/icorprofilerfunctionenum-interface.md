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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e77ec9de198b673bb3b5fc4dad3cd1b0316f07c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092071"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="59343-102">Interfaccia ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="59343-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="59343-103">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="59343-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="59343-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="59343-104">Methods</span></span>  
  
|<span data-ttu-id="59343-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="59343-105">Method</span></span>|<span data-ttu-id="59343-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59343-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="59343-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="59343-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="59343-108">Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="59343-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="59343-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="59343-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="59343-110">Ottiene il numero di funzioni che sono state caricate dall'applicazione o caricate forzatamente dal profiler.</span><span class="sxs-lookup"><span data-stu-id="59343-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="59343-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="59343-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="59343-112">Ottiene il numero specificato di funzioni contigue da una raccolta sequenziale di funzioni, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="59343-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="59343-113">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="59343-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="59343-114">Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.</span><span class="sxs-lookup"><span data-stu-id="59343-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="59343-115">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="59343-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="59343-116">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="59343-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59343-117">Note</span><span class="sxs-lookup"><span data-stu-id="59343-117">Remarks</span></span>  
 <span data-ttu-id="59343-118">L'interfaccia `ICorProfilerFunctionEnum` è un enumeratore.</span><span class="sxs-lookup"><span data-stu-id="59343-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="59343-119">Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore.</span><span class="sxs-lookup"><span data-stu-id="59343-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="59343-120">In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi della matrice, evitando così i problemi associati al passaggio di matrici di grandi dimensioni come parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="59343-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 `ICorProfilerFunctionEnum` <span data-ttu-id="59343-121">Enumera le funzioni che sono già stato compilato tramite JIT, ma non includono le funzioni caricate da immagini native generate con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="59343-121">enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59343-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59343-122">Requirements</span></span>  
 <span data-ttu-id="59343-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59343-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59343-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59343-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59343-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59343-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="59343-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="59343-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="59343-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59343-127">See also</span></span>

- [<span data-ttu-id="59343-128">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="59343-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="59343-129">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="59343-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="59343-130">Metodo EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="59343-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
