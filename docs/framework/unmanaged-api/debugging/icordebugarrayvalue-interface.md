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
ms.openlocfilehash: bd1e86b83c43af20604416f158ab9e74f399821b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894960"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="faca3-102">Interfaccia ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="faca3-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="faca3-103">Sottoclasse di ICorDebugHeapValue che rappresenta una matrice unidimensionale o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="faca3-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="faca3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="faca3-104">Methods</span></span>  
  
|<span data-ttu-id="faca3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="faca3-105">Method</span></span>|<span data-ttu-id="faca3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="faca3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="faca3-107">Metodo GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="faca3-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="faca3-108">Ottiene l'indice di base di ogni dimensione nella matrice.</span><span class="sxs-lookup"><span data-stu-id="faca3-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="faca3-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="faca3-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="faca3-110">Ottiene il numero totale di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="faca3-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="faca3-111">Metodo GetDimensions</span><span class="sxs-lookup"><span data-stu-id="faca3-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="faca3-112">Ottiene le dimensioni della matrice.</span><span class="sxs-lookup"><span data-stu-id="faca3-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="faca3-113">Metodo GetElement</span><span class="sxs-lookup"><span data-stu-id="faca3-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="faca3-114">Ottiene un valore che rappresenta l'elemento specificato nella matrice.</span><span class="sxs-lookup"><span data-stu-id="faca3-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="faca3-115">Metodo GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="faca3-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="faca3-116">Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come matrice unidimensionale in base zero.</span><span class="sxs-lookup"><span data-stu-id="faca3-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="faca3-117">Metodo GetElementType</span><span class="sxs-lookup"><span data-stu-id="faca3-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="faca3-118">Ottiene il tipo semplice degli elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="faca3-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="faca3-119">Metodo GetRank</span><span class="sxs-lookup"><span data-stu-id="faca3-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="faca3-120">Ottiene il numero di dimensioni nella matrice.</span><span class="sxs-lookup"><span data-stu-id="faca3-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="faca3-121">Metodo HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="faca3-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="faca3-122">Determina se la matrice dispone di indici di base.</span><span class="sxs-lookup"><span data-stu-id="faca3-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faca3-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="faca3-123">Remarks</span></span>  
 <span data-ttu-id="faca3-124">`ICorDebugArrayValue`supporta matrici unidimensionali e multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="faca3-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="faca3-125">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="faca3-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faca3-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="faca3-126">Requirements</span></span>  
 <span data-ttu-id="faca3-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faca3-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faca3-128">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faca3-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faca3-129">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faca3-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faca3-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faca3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faca3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faca3-131">See also</span></span>

- [<span data-ttu-id="faca3-132">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="faca3-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
