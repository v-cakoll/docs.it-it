---
title: Funzione BeginEnumeration (riferimenti alle API non gestite)
description: La funzione di BeginEnumeration Reimposta l'enumeratore all'inizio dell'enumerazione
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4221dbea2b5ad98f889e04eb8a9b6d992b59066e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212297"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="7e936-103">Funzione BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="7e936-103">BeginEnumeration function</span></span>
<span data-ttu-id="7e936-104">Reimposta l'enumeratore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7e936-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7e936-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e936-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="7e936-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e936-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="7e936-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="7e936-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="7e936-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="7e936-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="7e936-109">[in] Una combinazione bit per bit del flag o i valori descritti nel [osservazioni](#remarks) sezione che controlla le proprietà incluse nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7e936-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="7e936-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7e936-110">Return value</span></span>

<span data-ttu-id="7e936-111">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="7e936-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7e936-112">Costante</span><span class="sxs-lookup"><span data-stu-id="7e936-112">Constant</span></span>  |<span data-ttu-id="7e936-113">Value</span><span class="sxs-lookup"><span data-stu-id="7e936-113">Value</span></span>  |<span data-ttu-id="7e936-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e936-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7e936-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7e936-115">0x80041008</span></span> | <span data-ttu-id="7e936-116">La combinazione di flag in `lEnumFlags` non è valido o non valido è stato specificato l'argomento.</span><span class="sxs-lookup"><span data-stu-id="7e936-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="7e936-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="7e936-117">0x8004101d</span></span> | <span data-ttu-id="7e936-118">Una seconda chiamata a `BeginEnumeration` è stata eseguita senza una chiamata corrispondente a [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="7e936-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7e936-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7e936-119">0x80041006</span></span> | <span data-ttu-id="7e936-120">Memoria insufficiente è disponibile per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7e936-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7e936-121">0</span><span class="sxs-lookup"><span data-stu-id="7e936-121">0</span></span> | <span data-ttu-id="7e936-122">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="7e936-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7e936-123">Note</span><span class="sxs-lookup"><span data-stu-id="7e936-123">Remarks</span></span>

<span data-ttu-id="7e936-124">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) (metodo).</span><span class="sxs-lookup"><span data-stu-id="7e936-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="7e936-125">I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="7e936-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="7e936-126">È possibile combinare un flag di ogni gruppo con eventuali flag da qualsiasi altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="7e936-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="7e936-127">Tuttavia, i flag dallo stesso gruppo si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="7e936-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="7e936-128">**Gruppo 1**</span><span class="sxs-lookup"><span data-stu-id="7e936-128">**Group 1**</span></span>

|<span data-ttu-id="7e936-129">Costante</span><span class="sxs-lookup"><span data-stu-id="7e936-129">Constant</span></span>  |<span data-ttu-id="7e936-130">Value</span><span class="sxs-lookup"><span data-stu-id="7e936-130">Value</span></span>  |<span data-ttu-id="7e936-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e936-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="7e936-132">0x4</span><span class="sxs-lookup"><span data-stu-id="7e936-132">0x4</span></span> | <span data-ttu-id="7e936-133">Include le proprietà che costituiscono solo la chiave.</span><span class="sxs-lookup"><span data-stu-id="7e936-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="7e936-134">0x8</span><span class="sxs-lookup"><span data-stu-id="7e936-134">0x8</span></span> | <span data-ttu-id="7e936-135">Include le proprietà che sono solo i riferimenti agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7e936-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="7e936-136">**Gruppo 2**</span><span class="sxs-lookup"><span data-stu-id="7e936-136">**Group 2**</span></span>

<span data-ttu-id="7e936-137">Costante</span><span class="sxs-lookup"><span data-stu-id="7e936-137">Constant</span></span>  |<span data-ttu-id="7e936-138">Value</span><span class="sxs-lookup"><span data-stu-id="7e936-138">Value</span></span>  |<span data-ttu-id="7e936-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e936-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="7e936-140">0x30</span><span class="sxs-lookup"><span data-stu-id="7e936-140">0x30</span></span> | <span data-ttu-id="7e936-141">Limitare l'enumerazione per solo le proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="7e936-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="7e936-142">0x40</span><span class="sxs-lookup"><span data-stu-id="7e936-142">0x40</span></span> | <span data-ttu-id="7e936-143">Include le proprietà locali e propagate ma ne esclude le proprietà di sistema dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7e936-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="7e936-144">Per le classi:</span><span class="sxs-lookup"><span data-stu-id="7e936-144">For classes:</span></span>

<span data-ttu-id="7e936-145">Costante</span><span class="sxs-lookup"><span data-stu-id="7e936-145">Constant</span></span>  |<span data-ttu-id="7e936-146">Value</span><span class="sxs-lookup"><span data-stu-id="7e936-146">Value</span></span>  |<span data-ttu-id="7e936-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e936-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="7e936-148">0x100</span><span class="sxs-lookup"><span data-stu-id="7e936-148">0x100</span></span> | <span data-ttu-id="7e936-149">Limitare la proprietà viene sottoposto a override nella definizione della classe dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7e936-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="7e936-150">0x100</span><span class="sxs-lookup"><span data-stu-id="7e936-150">0x100</span></span> | <span data-ttu-id="7e936-151">Limitare l'enumerazione alle proprietà sottoposto a override nella definizione della classe corrente e alle nuove proprietà definite nella classe.</span><span class="sxs-lookup"><span data-stu-id="7e936-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="7e936-152">0x300</span><span class="sxs-lookup"><span data-stu-id="7e936-152">0x300</span></span> | <span data-ttu-id="7e936-153">Una maschera (invece di un flag) da applicare rispetto un' `lEnumFlags` valore per verificare se uno dei due `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` è impostata.</span><span class="sxs-lookup"><span data-stu-id="7e936-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7e936-154">0x10</span><span class="sxs-lookup"><span data-stu-id="7e936-154">0x10</span></span> | <span data-ttu-id="7e936-155">Limitare l'enumerazione alle proprietà definite o modificato nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="7e936-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7e936-156">0x20</span><span class="sxs-lookup"><span data-stu-id="7e936-156">0x20</span></span> | <span data-ttu-id="7e936-157">Limitare l'enumerazione delle proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="7e936-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="7e936-158">Per le istanze:</span><span class="sxs-lookup"><span data-stu-id="7e936-158">For instances:</span></span>

<span data-ttu-id="7e936-159">Costante</span><span class="sxs-lookup"><span data-stu-id="7e936-159">Constant</span></span>  |<span data-ttu-id="7e936-160">Value</span><span class="sxs-lookup"><span data-stu-id="7e936-160">Value</span></span>  |<span data-ttu-id="7e936-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e936-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7e936-162">0x10</span><span class="sxs-lookup"><span data-stu-id="7e936-162">0x10</span></span> | <span data-ttu-id="7e936-163">Limitare l'enumerazione alle proprietà definite o modificato nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="7e936-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7e936-164">0x20</span><span class="sxs-lookup"><span data-stu-id="7e936-164">0x20</span></span> | <span data-ttu-id="7e936-165">Limitare l'enumerazione delle proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="7e936-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="7e936-166">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e936-166">Requirements</span></span>  
 <span data-ttu-id="7e936-167">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e936-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e936-168">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7e936-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7e936-169">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7e936-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e936-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e936-170">See also</span></span>

- [<span data-ttu-id="7e936-171">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="7e936-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)