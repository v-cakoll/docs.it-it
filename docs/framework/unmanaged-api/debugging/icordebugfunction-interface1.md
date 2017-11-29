---
title: ICorDebugFunction Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction
helpviewer_keywords: ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327ef9f74e94e3b1b20e78eb6a833038b5bfe16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction-interface1"></a><span data-ttu-id="5d085-102">ICorDebugFunction Interface1</span><span class="sxs-lookup"><span data-stu-id="5d085-102">ICorDebugFunction Interface1</span></span>
<span data-ttu-id="5d085-103">Rappresenta una funzione o un metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="5d085-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d085-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5d085-104">Methods</span></span>  
  
|<span data-ttu-id="5d085-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5d085-105">Method</span></span>|<span data-ttu-id="5d085-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d085-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d085-107">CreateBreakpoint (metodo)</span><span class="sxs-lookup"><span data-stu-id="5d085-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="5d085-108">Crea un punto di interruzione all'inizio di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5d085-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="5d085-109">GetClass (metodo)</span><span class="sxs-lookup"><span data-stu-id="5d085-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="5d085-110">Ottiene un oggetto ICorDebugClass che rappresenta la classe di che questa funzione è membro.</span><span class="sxs-lookup"><span data-stu-id="5d085-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="5d085-111">GetCurrentVersionNumber (metodo)</span><span class="sxs-lookup"><span data-stu-id="5d085-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="5d085-112">Ottiene il numero di versione dell'ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5d085-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="5d085-113">GetILCode (metodo)</span><span class="sxs-lookup"><span data-stu-id="5d085-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="5d085-114">Ottiene il codice di Microsoft intermediate language (MSIL) per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5d085-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="5d085-115">Metodo GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="5d085-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="5d085-116">Ottiene i metadati di token per la firma di variabile locale della funzione che è rappresentata da questo `ICorDebugFunction` istanza.</span><span class="sxs-lookup"><span data-stu-id="5d085-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="5d085-117">GetModule (metodo)</span><span class="sxs-lookup"><span data-stu-id="5d085-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="5d085-118">Ottiene il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="5d085-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="5d085-119">GetNativeCode (metodo)</span><span class="sxs-lookup"><span data-stu-id="5d085-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="5d085-120">Ottiene il codice nativo per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5d085-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="5d085-121">GetToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="5d085-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="5d085-122">Ottiene i metadati del token per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5d085-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d085-123">Note</span><span class="sxs-lookup"><span data-stu-id="5d085-123">Remarks</span></span>  
 <span data-ttu-id="5d085-124">Il `ICorDebugFunction` interfaccia non rappresenta una funzione con parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="5d085-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="5d085-125">Ad esempio, un `ICorDebugFunction` istanza rappresenterebbero `Func<T>` ma non `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="5d085-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="5d085-126">Chiamare [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) per recuperare i parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="5d085-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="5d085-127">La relazione tra il token di metadati di un metodo `mdMethodDef`e un metodo `ICorDebugFunction` dipende se Modifica e continuazione è consentito nella funzione:</span><span class="sxs-lookup"><span data-stu-id="5d085-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="5d085-128">Se non è consentita, un tipo di relazione esiste tra la `ICorDebugFunction` oggetto e `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5d085-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="5d085-129">Ovvero, la funzione ha un `ICorDebugFunction` oggetto e una `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5d085-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="5d085-130">Se Modifica e continuazione è consentito nella funzione, è presente una relazione molti-a-uno tra il `ICorDebugFunction` oggetto e `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5d085-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="5d085-131">Ovvero, la funzione può avere molte istanze di `ICorDebugFunction`, uno per ogni versione della funzione, ma solo uno `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5d085-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d085-132">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="5d085-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d085-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d085-133">Requirements</span></span>  
 <span data-ttu-id="5d085-134">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d085-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d085-135">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5d085-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d085-136">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d085-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d085-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d085-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d085-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d085-138">See Also</span></span>  
 [<span data-ttu-id="5d085-139">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5d085-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
