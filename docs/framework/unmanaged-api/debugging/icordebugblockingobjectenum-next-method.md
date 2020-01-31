---
title: Metodo ICorDebugBlockingObjectEnum::Next
ms.date: 03/30/2017
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
ms.openlocfilehash: c25f26bb0f1f34e3799bab4bec7e697d393cccb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784519"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="178c4-102">Metodo ICorDebugBlockingObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="178c4-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="178c4-103">Ottiene il numero specificato di oggetti [CorDebugBlockingObject](cordebugblockingobject-structure.md) dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="178c4-103">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="178c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="178c4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="178c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="178c4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="178c4-106">in Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="178c4-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="178c4-107">out Matrice di puntatori a oggetti [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="178c4-107">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="178c4-108">out Puntatore al numero di oggetti recuperati.</span><span class="sxs-lookup"><span data-stu-id="178c4-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="178c4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="178c4-109">Return Value</span></span>  
 <span data-ttu-id="178c4-110">Questo metodo restituisce gli HRESULT specifici seguenti.</span><span class="sxs-lookup"><span data-stu-id="178c4-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="178c4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="178c4-111">HRESULT</span></span>|<span data-ttu-id="178c4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="178c4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="178c4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="178c4-113">S_OK</span></span>|<span data-ttu-id="178c4-114">Il metodo è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="178c4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="178c4-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="178c4-115">S_FALSE</span></span>|<span data-ttu-id="178c4-116">`pceltFetched` non è uguale a `celt`.</span><span class="sxs-lookup"><span data-stu-id="178c4-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="178c4-117">Note</span><span class="sxs-lookup"><span data-stu-id="178c4-117">Remarks</span></span>  
 <span data-ttu-id="178c4-118">Questo metodo funziona come un tipico enumeratore COM.</span><span class="sxs-lookup"><span data-stu-id="178c4-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="178c4-119">I valori della matrice di input devono essere di almeno dimensioni `celt`.</span><span class="sxs-lookup"><span data-stu-id="178c4-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="178c4-120">La matrice verrà compilata con i valori `celt` successivi nell'enumerazione o con tutti i valori rimanenti se il numero di `celt` rimane.</span><span class="sxs-lookup"><span data-stu-id="178c4-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="178c4-121">Quando termina, questo metodo `pceltFetched` verrà compilato con il numero di valori recuperati.</span><span class="sxs-lookup"><span data-stu-id="178c4-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="178c4-122">Se `values` contiene puntatori o puntatori non validi a un buffer di dimensioni minori di `celt`o se `pceltFetched` è un puntatore non valido, il risultato sarà indefinito.</span><span class="sxs-lookup"><span data-stu-id="178c4-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="178c4-123">Sebbene non sia necessario rilasciare la struttura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , è necessario rilasciare l'interfaccia "ICorDebugValue" all'interno di essa.</span><span class="sxs-lookup"><span data-stu-id="178c4-123">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="178c4-124">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="178c4-124">Requirements</span></span>  
 <span data-ttu-id="178c4-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="178c4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="178c4-126">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="178c4-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="178c4-127">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="178c4-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="178c4-128">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="178c4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178c4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="178c4-129">See also</span></span>

- [<span data-ttu-id="178c4-130">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="178c4-130">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="178c4-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="178c4-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="178c4-132">Debug</span><span class="sxs-lookup"><span data-stu-id="178c4-132">Debugging</span></span>](index.md)
