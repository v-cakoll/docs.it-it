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
ms.openlocfilehash: ae65c59efe1d925b5e058e8664d1e093fdfec875
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917198"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="84f41-102">Interfaccia ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="84f41-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="84f41-103">Rappresenta una funzione o un metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="84f41-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84f41-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="84f41-104">Methods</span></span>  
  
|<span data-ttu-id="84f41-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="84f41-105">Method</span></span>|<span data-ttu-id="84f41-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84f41-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84f41-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="84f41-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="84f41-108">Crea un punto di interruzione all'inizio di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="84f41-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="84f41-109">Metodo GetClass</span><span class="sxs-lookup"><span data-stu-id="84f41-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="84f41-110">Ottiene un oggetto ICorDebugClass che rappresenta la classe di cui questa funzione è membro.</span><span class="sxs-lookup"><span data-stu-id="84f41-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="84f41-111">Metodo GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="84f41-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="84f41-112">Ottiene il numero di versione dell'Ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="84f41-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="84f41-113">Metodo GetILCode</span><span class="sxs-lookup"><span data-stu-id="84f41-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="84f41-114">Ottiene il codice MSIL (Microsoft Intermediate Language) per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="84f41-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="84f41-115">Metodo GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="84f41-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="84f41-116">Ottiene il token di metadati per la firma della variabile locale della funzione rappresentata da questa `ICorDebugFunction` istanza.</span><span class="sxs-lookup"><span data-stu-id="84f41-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="84f41-117">Metodo GetModule</span><span class="sxs-lookup"><span data-stu-id="84f41-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="84f41-118">Ottiene il modulo in cui è definita questa funzione.</span><span class="sxs-lookup"><span data-stu-id="84f41-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="84f41-119">Metodo GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="84f41-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="84f41-120">Ottiene il codice nativo per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="84f41-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="84f41-121">Metodo GetToken</span><span class="sxs-lookup"><span data-stu-id="84f41-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="84f41-122">Ottiene il token di metadati per questa funzione.</span><span class="sxs-lookup"><span data-stu-id="84f41-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84f41-123">Note</span><span class="sxs-lookup"><span data-stu-id="84f41-123">Remarks</span></span>  
 <span data-ttu-id="84f41-124">L' `ICorDebugFunction` interfaccia non rappresenta una funzione con parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="84f41-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="84f41-125">Un' `ICorDebugFunction` `Func<string>` istanza`Func<T>` , ad esempio, rappresenterebbe, ma non.</span><span class="sxs-lookup"><span data-stu-id="84f41-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="84f41-126">Chiamare [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) per ottenere i parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="84f41-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="84f41-127">La relazione tra il token di metadati di un `mdMethodDef`metodo, e l'oggetto `ICorDebugFunction` di un metodo dipende dalla possibilità di modificare e continuare nella funzione:</span><span class="sxs-lookup"><span data-stu-id="84f41-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="84f41-128">Se la funzione modifica e continuazione non è consentita, esiste una relazione uno-a-uno `ICorDebugFunction` tra l'oggetto `mdMethodDef` e il token.</span><span class="sxs-lookup"><span data-stu-id="84f41-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="84f41-129">Ovvero, la funzione dispone di un `ICorDebugFunction` oggetto e di `mdMethodDef` un token.</span><span class="sxs-lookup"><span data-stu-id="84f41-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="84f41-130">Se la funzione modifica e continuazione è consentita, esiste una relazione molti-a-uno `ICorDebugFunction` tra l'oggetto `mdMethodDef` e il token.</span><span class="sxs-lookup"><span data-stu-id="84f41-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="84f41-131">Ovvero, la funzione può avere molte istanze di `ICorDebugFunction`, una per ogni versione della funzione, ma solo un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="84f41-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84f41-132">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="84f41-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84f41-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84f41-133">Requirements</span></span>  
 <span data-ttu-id="84f41-134">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84f41-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84f41-135">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="84f41-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84f41-136">**Libreria**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84f41-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="84f41-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84f41-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f41-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84f41-138">See also</span></span>

- [<span data-ttu-id="84f41-139">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="84f41-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
