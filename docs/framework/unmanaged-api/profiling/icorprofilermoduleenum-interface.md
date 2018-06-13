---
title: Interfaccia ICorProfilerModuleEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2275eb37d0e62c3f0ee8bbc8ea6db66901a3f1c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458065"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="cf881-102">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="cf881-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="cf881-103">Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.</span><span class="sxs-lookup"><span data-stu-id="cf881-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf881-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cf881-104">Methods</span></span>  
  
|<span data-ttu-id="cf881-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cf881-105">Method</span></span>|<span data-ttu-id="cf881-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf881-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf881-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="cf881-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="cf881-108">Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerModuleEnum`.</span><span class="sxs-lookup"><span data-stu-id="cf881-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="cf881-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="cf881-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="cf881-110">Ottiene il numero di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cf881-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="cf881-111">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="cf881-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="cf881-112">Ottiene il numero specificato di moduli contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="cf881-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="cf881-113">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="cf881-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="cf881-114">Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.</span><span class="sxs-lookup"><span data-stu-id="cf881-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="cf881-115">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="cf881-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="cf881-116">Sposta in avanti il cursore dell'enumeratore, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="cf881-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf881-117">Note</span><span class="sxs-lookup"><span data-stu-id="cf881-117">Remarks</span></span>  
 <span data-ttu-id="cf881-118">L'interfaccia `ICorProfilerModuleEnum` è un enumeratore.</span><span class="sxs-lookup"><span data-stu-id="cf881-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="cf881-119">Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore.</span><span class="sxs-lookup"><span data-stu-id="cf881-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="cf881-120">In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi della matrice, evitando così i problemi associati al passaggio di matrici di grandi dimensioni come parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="cf881-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf881-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf881-121">Requirements</span></span>  
 <span data-ttu-id="cf881-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf881-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf881-123">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf881-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf881-124">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cf881-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf881-125">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf881-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf881-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf881-126">See Also</span></span>  
 [<span data-ttu-id="cf881-127">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cf881-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="cf881-128">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="cf881-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="cf881-129">Metodo EnumModules</span><span class="sxs-lookup"><span data-stu-id="cf881-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
