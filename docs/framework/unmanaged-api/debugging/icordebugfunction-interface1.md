---
title: Interfaccia ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca21911f3d16b79887b9d6d8185f8fab17651321
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093215"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="4ca87-102">Interfaccia ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="4ca87-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="4ca87-103">Rappresenta una funzione o un metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="4ca87-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ca87-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4ca87-104">Methods</span></span>  
  
|<span data-ttu-id="4ca87-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4ca87-105">Method</span></span>|<span data-ttu-id="4ca87-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ca87-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ca87-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4ca87-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="4ca87-108">Crea un punto di interruzione all'inizio di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4ca87-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="4ca87-109">Metodo GetClass</span><span class="sxs-lookup"><span data-stu-id="4ca87-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="4ca87-110">Ottiene un oggetto ICorDebugClass che rappresenta la classe di di che questa funzione è un membro.</span><span class="sxs-lookup"><span data-stu-id="4ca87-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="4ca87-111">Metodo GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="4ca87-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="4ca87-112">Ottiene il numero di versione dell'ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4ca87-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="4ca87-113">Metodo GetILCode</span><span class="sxs-lookup"><span data-stu-id="4ca87-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="4ca87-114">Ottiene il codice Microsoft intermediate language (MSIL) per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4ca87-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="4ca87-115">Metodo GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="4ca87-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="4ca87-116">Ottiene i metadati del token per la firma della variabile locale della funzione che è rappresentata da questo `ICorDebugFunction` istanza.</span><span class="sxs-lookup"><span data-stu-id="4ca87-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="4ca87-117">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="4ca87-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="4ca87-118">Ottiene il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="4ca87-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="4ca87-119">Metodo GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="4ca87-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="4ca87-120">Ottiene il codice nativo per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4ca87-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="4ca87-121">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="4ca87-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="4ca87-122">Ottiene i metadati del token per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="4ca87-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ca87-123">Note</span><span class="sxs-lookup"><span data-stu-id="4ca87-123">Remarks</span></span>  
 <span data-ttu-id="4ca87-124">Il `ICorDebugFunction` interfaccia non rappresenta una funzione con parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4ca87-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="4ca87-125">Ad esempio, un' `ICorDebugFunction` istanza rappresenterebbe `Func<T>` ma non `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="4ca87-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="4ca87-126">Chiamare [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) per recuperare i parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="4ca87-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="4ca87-127">La relazione tra i token di metadati del metodo `mdMethodDef`e un metodo `ICorDebugFunction` oggetto è dipende dal fatto che modifica e continuazione è consentita nella funzione:</span><span class="sxs-lookup"><span data-stu-id="4ca87-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="4ca87-128">Se Modifica e continuazione non è consentito nella funzione, esiste una relazione uno a uno tra i `ICorDebugFunction` oggetto e il `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="4ca87-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="4ca87-129">Vale a dire, la funzione di disponibile `ICorDebugFunction` oggetto e l'altra `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="4ca87-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="4ca87-130">Se Modifica e continuazione è consentito nella funzione, esiste una relazione molti-a-uno tra i `ICorDebugFunction` oggetto e il `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="4ca87-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="4ca87-131">Vale a dire, la funzione può avere molte istanze di `ICorDebugFunction`, uno per ogni versione della funzione, ma una sola `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="4ca87-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ca87-132">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="4ca87-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ca87-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ca87-133">Requirements</span></span>  
 <span data-ttu-id="4ca87-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ca87-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca87-135">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ca87-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ca87-136">**Libreria:**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ca87-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ca87-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ca87-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca87-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ca87-138">See also</span></span>

- [<span data-ttu-id="4ca87-139">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4ca87-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
