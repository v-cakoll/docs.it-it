---
title: Metodo ICorDebugBlockingObjectEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f2e2168ea1b03e5a2339baf019da59f1e83a71a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="89f87-102">Metodo ICorDebugBlockingObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="89f87-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="89f87-103">Ottiene il numero specificato di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) oggetti nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="89f87-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f87-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89f87-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89f87-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89f87-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="89f87-106">[in] Il numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="89f87-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="89f87-107">[out] Una matrice di puntatori a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="89f87-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="89f87-108">[out] Puntatore al numero di oggetti che sono stati recuperati.</span><span class="sxs-lookup"><span data-stu-id="89f87-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89f87-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="89f87-109">Return Value</span></span>  
 <span data-ttu-id="89f87-110">Questo metodo restituisce gli HRESULT specifici seguenti.</span><span class="sxs-lookup"><span data-stu-id="89f87-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="89f87-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89f87-111">HRESULT</span></span>|<span data-ttu-id="89f87-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89f87-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89f87-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="89f87-113">S_OK</span></span>|<span data-ttu-id="89f87-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="89f87-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="89f87-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="89f87-115">S_FALSE</span></span>|<span data-ttu-id="89f87-116">`pceltFetched` non è uguale a `celt`.</span><span class="sxs-lookup"><span data-stu-id="89f87-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89f87-117">Note</span><span class="sxs-lookup"><span data-stu-id="89f87-117">Remarks</span></span>  
 <span data-ttu-id="89f87-118">Questo metodo funziona come un enumeratore COM tipico.</span><span class="sxs-lookup"><span data-stu-id="89f87-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="89f87-119">I valori della matrice di input devono essere almeno di dimensioni `celt`.</span><span class="sxs-lookup"><span data-stu-id="89f87-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="89f87-120">La matrice verrà compilata con uno successivo `celt` valori nell'enumerazione o con tutti gli altri valori se meno di `celt` rimangono.</span><span class="sxs-lookup"><span data-stu-id="89f87-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="89f87-121">Quando termina, questo metodo `pceltFetched` verrà compilata con il numero di valori che sono stati recuperati.</span><span class="sxs-lookup"><span data-stu-id="89f87-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="89f87-122">Se `values` contiene i puntatori non validi o punta a un buffer di dimensioni inferiori a quelle `celt`, o se `pceltFetched` è un puntatore non valido, il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="89f87-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89f87-123">Sebbene il [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) struttura non deve essere rilasciato, l'interfaccia "ICorDebugValue" all'interno devono essere rilasciate.</span><span class="sxs-lookup"><span data-stu-id="89f87-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="89f87-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89f87-124">Requirements</span></span>  
 <span data-ttu-id="89f87-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f87-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f87-126">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="89f87-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89f87-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89f87-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89f87-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f87-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f87-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89f87-129">See Also</span></span>  
 [<span data-ttu-id="89f87-130">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="89f87-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="89f87-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="89f87-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="89f87-132">Debug</span><span class="sxs-lookup"><span data-stu-id="89f87-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
