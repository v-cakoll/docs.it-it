---
title: Interfaccia ICorDebugArrayValue
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
ms.openlocfilehash: 73898bf5f4303d677787bae587a16f2f325dee9e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970844"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="352f9-102">Interfaccia ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="352f9-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="352f9-103">Sottoclasse di ICorDebugHeapValue che rappresenta una matrice unidimensionale o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="352f9-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="352f9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="352f9-104">Methods</span></span>  
  
|<span data-ttu-id="352f9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="352f9-105">Method</span></span>|<span data-ttu-id="352f9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="352f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="352f9-107">Metodo GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="352f9-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="352f9-108">Ottiene l'indice di base di ogni dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="352f9-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="352f9-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="352f9-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="352f9-110">Ottiene il numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="352f9-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="352f9-111">Metodo GetDimensions</span><span class="sxs-lookup"><span data-stu-id="352f9-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="352f9-112">Ottiene le dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="352f9-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="352f9-113">Metodo GetElement</span><span class="sxs-lookup"><span data-stu-id="352f9-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="352f9-114">Ottiene un valore che rappresenta l'elemento specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="352f9-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="352f9-115">Metodo GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="352f9-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="352f9-116">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come una matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="352f9-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="352f9-117">Metodo GetElementType</span><span class="sxs-lookup"><span data-stu-id="352f9-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="352f9-118">Ottiene il tipo semplice di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="352f9-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="352f9-119">Metodo GetRank</span><span class="sxs-lookup"><span data-stu-id="352f9-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="352f9-120">Ottiene il numero di dimensioni nella matrice.</span><span class="sxs-lookup"><span data-stu-id="352f9-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="352f9-121">Metodo HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="352f9-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="352f9-122">Determina se la matrice dispone di indici di base.</span><span class="sxs-lookup"><span data-stu-id="352f9-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="352f9-123">Note</span><span class="sxs-lookup"><span data-stu-id="352f9-123">Remarks</span></span>  
 <span data-ttu-id="352f9-124">`ICorDebugArrayValue` supporta matrici unidimensionali e multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="352f9-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="352f9-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="352f9-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="352f9-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="352f9-126">Requirements</span></span>  
 <span data-ttu-id="352f9-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="352f9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="352f9-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="352f9-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="352f9-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="352f9-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="352f9-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="352f9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="352f9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="352f9-131">See also</span></span>
- [<span data-ttu-id="352f9-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="352f9-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
