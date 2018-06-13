---
title: ICorDebugArrayValue Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a96f2b21e524f03ea3290be268244eaceeb5c7f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408177"
---
# <a name="icordebugarrayvalue-interface1"></a><span data-ttu-id="1be0a-102">ICorDebugArrayValue Interface1</span><span class="sxs-lookup"><span data-stu-id="1be0a-102">ICorDebugArrayValue Interface1</span></span>
<span data-ttu-id="1be0a-103">Sottoclasse di ICorDebugHeapValue che rappresenta una matrice unidimensionale o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="1be0a-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1be0a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1be0a-104">Methods</span></span>  
  
|<span data-ttu-id="1be0a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1be0a-105">Method</span></span>|<span data-ttu-id="1be0a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1be0a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1be0a-107">Metodo GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="1be0a-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="1be0a-108">Ottiene l'indice di base di ciascuna dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="1be0a-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="1be0a-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="1be0a-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="1be0a-110">Ottiene il numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="1be0a-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="1be0a-111">Metodo GetDimensions</span><span class="sxs-lookup"><span data-stu-id="1be0a-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="1be0a-112">Ottiene le dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="1be0a-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="1be0a-113">Metodo GetElement</span><span class="sxs-lookup"><span data-stu-id="1be0a-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="1be0a-114">Ottiene un valore che rappresenta l'elemento specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="1be0a-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="1be0a-115">Metodo GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="1be0a-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="1be0a-116">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come una matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="1be0a-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="1be0a-117">Metodo GetElementType</span><span class="sxs-lookup"><span data-stu-id="1be0a-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="1be0a-118">Ottiene il tipo semplice degli elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="1be0a-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="1be0a-119">Metodo GetRank</span><span class="sxs-lookup"><span data-stu-id="1be0a-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="1be0a-120">Ottiene il numero di dimensioni nella matrice.</span><span class="sxs-lookup"><span data-stu-id="1be0a-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="1be0a-121">Metodo HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="1be0a-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="1be0a-122">Determina se la matrice include gli indici di base.</span><span class="sxs-lookup"><span data-stu-id="1be0a-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1be0a-123">Note</span><span class="sxs-lookup"><span data-stu-id="1be0a-123">Remarks</span></span>  
 <span data-ttu-id="1be0a-124">`ICorDebugArrayValue` supporta matrici unidimensionali e multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="1be0a-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1be0a-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="1be0a-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1be0a-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1be0a-126">Requirements</span></span>  
 <span data-ttu-id="1be0a-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1be0a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1be0a-128">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1be0a-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1be0a-129">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1be0a-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1be0a-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1be0a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be0a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1be0a-131">See Also</span></span>  
 [<span data-ttu-id="1be0a-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1be0a-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
