---
title: Funzione BeginEnumeration (riferimenti alle API non gestite)
description: La funzione BeginEnumeration Reimposta l'enumeratore all'inizio dell'enumerazione
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginEnumeration
helpviewer_keywords: BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12a742774bff22030bdfaaa34e431059e016a4bf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="4f56e-103">BeginEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="4f56e-103">BeginEnumeration function</span></span>
<span data-ttu-id="4f56e-104">Reimposta l'enumeratore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f56e-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4f56e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f56e-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="4f56e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f56e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4f56e-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="4f56e-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="4f56e-108">`ptr`[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="4f56e-108">`ptr` [in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="4f56e-109">[in] Combinazione bit per bit dei valori descritti in o flag di [osservazioni](#remarks) sezione che controlla le proprietà incluse nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f56e-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="4f56e-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f56e-110">Return value</span></span>

<span data-ttu-id="4f56e-111">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="4f56e-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4f56e-112">Costante</span><span class="sxs-lookup"><span data-stu-id="4f56e-112">Constant</span></span>  |<span data-ttu-id="4f56e-113">Valore</span><span class="sxs-lookup"><span data-stu-id="4f56e-113">Value</span></span>  |<span data-ttu-id="4f56e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f56e-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4f56e-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4f56e-115">0x80041008</span></span> | <span data-ttu-id="4f56e-116">La combinazione di flag in `lEnumFlags` non è valido o non valido è stato specificato l'argomento.</span><span class="sxs-lookup"><span data-stu-id="4f56e-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4f56e-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4f56e-117">0x8004101d</span></span> | <span data-ttu-id="4f56e-118">Una seconda chiamata a `BeginEnumeration` è stato eseguito senza una corrispondente chiamata a [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4f56e-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4f56e-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4f56e-119">0x80041006</span></span> | <span data-ttu-id="4f56e-120">Memoria insufficiente è disponibile per avviare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f56e-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4f56e-121">0</span><span class="sxs-lookup"><span data-stu-id="4f56e-121">0</span></span> | <span data-ttu-id="4f56e-122">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="4f56e-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4f56e-123">Note</span><span class="sxs-lookup"><span data-stu-id="4f56e-123">Remarks</span></span>

<span data-ttu-id="4f56e-124">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="4f56e-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="4f56e-125">I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="4f56e-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="4f56e-126">È possibile combinare un flag di ogni gruppo con un flag da qualsiasi altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="4f56e-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="4f56e-127">Tuttavia, i flag dello stesso gruppo si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="4f56e-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="4f56e-128">**Gruppo 1**</span><span class="sxs-lookup"><span data-stu-id="4f56e-128">**Group 1**</span></span>

|<span data-ttu-id="4f56e-129">Costante</span><span class="sxs-lookup"><span data-stu-id="4f56e-129">Constant</span></span>  |<span data-ttu-id="4f56e-130">Valore</span><span class="sxs-lookup"><span data-stu-id="4f56e-130">Value</span></span>  |<span data-ttu-id="4f56e-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f56e-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="4f56e-132">0x4</span><span class="sxs-lookup"><span data-stu-id="4f56e-132">0x4</span></span> | <span data-ttu-id="4f56e-133">Includono le proprietà che costituiscono la chiave solo.</span><span class="sxs-lookup"><span data-stu-id="4f56e-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="4f56e-134">0x8</span><span class="sxs-lookup"><span data-stu-id="4f56e-134">0x8</span></span> | <span data-ttu-id="4f56e-135">Le proprietà solo i riferimenti agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="4f56e-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="4f56e-136">**Gruppo 2**</span><span class="sxs-lookup"><span data-stu-id="4f56e-136">**Group 2**</span></span>

<span data-ttu-id="4f56e-137">Costante</span><span class="sxs-lookup"><span data-stu-id="4f56e-137">Constant</span></span>  |<span data-ttu-id="4f56e-138">Valore</span><span class="sxs-lookup"><span data-stu-id="4f56e-138">Value</span></span>  |<span data-ttu-id="4f56e-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f56e-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="4f56e-140">0x30</span><span class="sxs-lookup"><span data-stu-id="4f56e-140">0x30</span></span> | <span data-ttu-id="4f56e-141">Limitare l'enumerazione solo le proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="4f56e-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="4f56e-142">0x40</span><span class="sxs-lookup"><span data-stu-id="4f56e-142">0x40</span></span> | <span data-ttu-id="4f56e-143">Include le proprietà locali e propagate ma esclude le proprietà di sistema dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f56e-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="4f56e-144">Per le classi:</span><span class="sxs-lookup"><span data-stu-id="4f56e-144">For classes:</span></span>

<span data-ttu-id="4f56e-145">Costante</span><span class="sxs-lookup"><span data-stu-id="4f56e-145">Constant</span></span>  |<span data-ttu-id="4f56e-146">Valore</span><span class="sxs-lookup"><span data-stu-id="4f56e-146">Value</span></span>  |<span data-ttu-id="4f56e-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f56e-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="4f56e-148">0x100</span><span class="sxs-lookup"><span data-stu-id="4f56e-148">0x100</span></span> | <span data-ttu-id="4f56e-149">Limitare la proprietà viene sottoposto a override nella definizione della classe dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f56e-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="4f56e-150">0x100</span><span class="sxs-lookup"><span data-stu-id="4f56e-150">0x100</span></span> | <span data-ttu-id="4f56e-151">Limitare l'enumerazione per proprietà sottoposto a override in una definizione di classe corrente e per le nuove proprietà definita nella classe.</span><span class="sxs-lookup"><span data-stu-id="4f56e-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="4f56e-152">0x300</span><span class="sxs-lookup"><span data-stu-id="4f56e-152">0x300</span></span> | <span data-ttu-id="4f56e-153">Una maschera (anziché un flag) da applicare rispetto una `lEnumFlags` valore da controllare se il valore `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` è impostata.</span><span class="sxs-lookup"><span data-stu-id="4f56e-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4f56e-154">0x10</span><span class="sxs-lookup"><span data-stu-id="4f56e-154">0x10</span></span> | <span data-ttu-id="4f56e-155">Limitare la proprietà che vengono definite o modificate nella stessa classe dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f56e-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="4f56e-156">0x20</span><span class="sxs-lookup"><span data-stu-id="4f56e-156">0x20</span></span> | <span data-ttu-id="4f56e-157">Limitare l'enumerazione di proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="4f56e-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="4f56e-158">Per le istanze:</span><span class="sxs-lookup"><span data-stu-id="4f56e-158">For instances:</span></span>

<span data-ttu-id="4f56e-159">Costante</span><span class="sxs-lookup"><span data-stu-id="4f56e-159">Constant</span></span>  |<span data-ttu-id="4f56e-160">Valore</span><span class="sxs-lookup"><span data-stu-id="4f56e-160">Value</span></span>  |<span data-ttu-id="4f56e-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f56e-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4f56e-162">0x10</span><span class="sxs-lookup"><span data-stu-id="4f56e-162">0x10</span></span> | <span data-ttu-id="4f56e-163">Limitare la proprietà che vengono definite o modificate nella stessa classe dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4f56e-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="4f56e-164">0x20</span><span class="sxs-lookup"><span data-stu-id="4f56e-164">0x20</span></span> | <span data-ttu-id="4f56e-165">Limitare l'enumerazione di proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="4f56e-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="4f56e-166">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f56e-166">Requirements</span></span>  
 <span data-ttu-id="4f56e-167">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f56e-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f56e-168">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4f56e-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4f56e-169">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4f56e-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f56e-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f56e-170">See also</span></span>  
[<span data-ttu-id="4f56e-171">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="4f56e-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
