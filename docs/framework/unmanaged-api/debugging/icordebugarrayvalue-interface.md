---
title: ICorDebugArrayValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13e226ccdcd6becc98d524c429b5cadae8d19c3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvalue-interface1"></a><span data-ttu-id="e5a45-102">ICorDebugArrayValue Interface1</span><span class="sxs-lookup"><span data-stu-id="e5a45-102">ICorDebugArrayValue Interface1</span></span>
<span data-ttu-id="e5a45-103">Sottoclasse di ICorDebugHeapValue che rappresenta una matrice unidimensionale o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="e5a45-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5a45-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e5a45-104">Methods</span></span>  
  
|<span data-ttu-id="e5a45-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e5a45-105">Method</span></span>|<span data-ttu-id="e5a45-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5a45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5a45-107">GetBaseIndicies (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="e5a45-108">Ottiene l'indice di base di ciascuna dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="e5a45-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="e5a45-109">GetCount (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="e5a45-110">Ottiene il numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e5a45-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="e5a45-111">GetDimensions (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="e5a45-112">Ottiene le dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="e5a45-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="e5a45-113">GetElement (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="e5a45-114">Ottiene un valore che rappresenta l'elemento specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e5a45-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="e5a45-115">GetElementAtPosition (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="e5a45-116">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come una matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="e5a45-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="e5a45-117">GetElementType (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="e5a45-118">Ottiene il tipo semplice degli elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e5a45-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="e5a45-119">GetRank (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="e5a45-120">Ottiene il numero di dimensioni nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e5a45-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="e5a45-121">HasBaseIndicies (metodo)</span><span class="sxs-lookup"><span data-stu-id="e5a45-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="e5a45-122">Determina se la matrice include gli indici di base.</span><span class="sxs-lookup"><span data-stu-id="e5a45-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a45-123">Note</span><span class="sxs-lookup"><span data-stu-id="e5a45-123">Remarks</span></span>  
 <span data-ttu-id="e5a45-124">`ICorDebugArrayValue`supporta matrici unidimensionali e multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="e5a45-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5a45-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e5a45-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a45-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5a45-126">Requirements</span></span>  
 <span data-ttu-id="e5a45-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5a45-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a45-128">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e5a45-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5a45-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5a45-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5a45-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a45-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a45-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5a45-131">See Also</span></span>  
 [<span data-ttu-id="e5a45-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e5a45-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
