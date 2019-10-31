---
title: Funzione BeginEnumeration (riferimenti alle API non gestite)
description: La funzione BeginEnumeration Reimposta un enumeratore all'inizio dell'enumerazione.
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
ms.openlocfilehash: 9e467234a45ae702a5b77a5f0fa8b75d4ff03c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124136"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="0965f-103">Funzione BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="0965f-103">BeginEnumeration function</span></span>
<span data-ttu-id="0965f-104">Reimposta un enumeratore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0965f-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0965f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0965f-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="0965f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0965f-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="0965f-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="0965f-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="0965f-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="0965f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="0965f-109">in Combinazione bit per bit dei flag o dei valori descritti nella sezione [osservazioni](#remarks) che controlla le proprietà incluse nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0965f-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="0965f-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0965f-110">Return value</span></span>

<span data-ttu-id="0965f-111">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="0965f-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0965f-112">Costante</span><span class="sxs-lookup"><span data-stu-id="0965f-112">Constant</span></span>  |<span data-ttu-id="0965f-113">Value</span><span class="sxs-lookup"><span data-stu-id="0965f-113">Value</span></span>  |<span data-ttu-id="0965f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0965f-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0965f-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0965f-115">0x80041008</span></span> | <span data-ttu-id="0965f-116">La combinazione di flag in `lEnumFlags` non è valida oppure è stato specificato un argomento non valido.</span><span class="sxs-lookup"><span data-stu-id="0965f-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="0965f-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="0965f-117">0x8004101d</span></span> | <span data-ttu-id="0965f-118">Una seconda chiamata a `BeginEnumeration` è stata effettuata senza una chiamata corrispondente a [`EndEnumeration`](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="0965f-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0965f-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0965f-119">0x80041006</span></span> | <span data-ttu-id="0965f-120">La memoria disponibile non è sufficiente per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0965f-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0965f-121">0</span><span class="sxs-lookup"><span data-stu-id="0965f-121">0</span></span> | <span data-ttu-id="0965f-122">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="0965f-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0965f-123">Note</span><span class="sxs-lookup"><span data-stu-id="0965f-123">Remarks</span></span>

<span data-ttu-id="0965f-124">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="0965f-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="0965f-125">I flag che possono essere passati come `lEnumFlags` argomento vengono definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="0965f-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="0965f-126">È possibile combinare un flag di ogni gruppo con qualsiasi flag di qualsiasi altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="0965f-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="0965f-127">Tuttavia, i flag dello stesso gruppo si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="0965f-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="0965f-128">**Gruppo 1**</span><span class="sxs-lookup"><span data-stu-id="0965f-128">**Group 1**</span></span>

|<span data-ttu-id="0965f-129">Costante</span><span class="sxs-lookup"><span data-stu-id="0965f-129">Constant</span></span>  |<span data-ttu-id="0965f-130">Value</span><span class="sxs-lookup"><span data-stu-id="0965f-130">Value</span></span>  |<span data-ttu-id="0965f-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0965f-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="0965f-132">0x4</span><span class="sxs-lookup"><span data-stu-id="0965f-132">0x4</span></span> | <span data-ttu-id="0965f-133">Includere le proprietà che costituiscono solo la chiave.</span><span class="sxs-lookup"><span data-stu-id="0965f-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="0965f-134">0x8</span><span class="sxs-lookup"><span data-stu-id="0965f-134">0x8</span></span> | <span data-ttu-id="0965f-135">Includere proprietà che sono solo riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="0965f-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="0965f-136">**Gruppo 2**</span><span class="sxs-lookup"><span data-stu-id="0965f-136">**Group 2**</span></span>

<span data-ttu-id="0965f-137">Costante</span><span class="sxs-lookup"><span data-stu-id="0965f-137">Constant</span></span>  |<span data-ttu-id="0965f-138">Value</span><span class="sxs-lookup"><span data-stu-id="0965f-138">Value</span></span>  |<span data-ttu-id="0965f-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0965f-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="0965f-140">0x30</span><span class="sxs-lookup"><span data-stu-id="0965f-140">0x30</span></span> | <span data-ttu-id="0965f-141">Limitare l'enumerazione solo alle proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="0965f-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="0965f-142">0x40</span><span class="sxs-lookup"><span data-stu-id="0965f-142">0x40</span></span> | <span data-ttu-id="0965f-143">Includere proprietà locali e propagate, escluse le proprietà di sistema dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0965f-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="0965f-144">Per le classi:</span><span class="sxs-lookup"><span data-stu-id="0965f-144">For classes:</span></span>

<span data-ttu-id="0965f-145">Costante</span><span class="sxs-lookup"><span data-stu-id="0965f-145">Constant</span></span>  |<span data-ttu-id="0965f-146">Value</span><span class="sxs-lookup"><span data-stu-id="0965f-146">Value</span></span>  |<span data-ttu-id="0965f-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0965f-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="0965f-148">0x100</span><span class="sxs-lookup"><span data-stu-id="0965f-148">0x100</span></span> | <span data-ttu-id="0965f-149">Limitare l'enumerazione alle proprietà sottoposte a override nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="0965f-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="0965f-150">0x100</span><span class="sxs-lookup"><span data-stu-id="0965f-150">0x100</span></span> | <span data-ttu-id="0965f-151">Limitare l'enumerazione alle proprietà sottoposte a override nella definizione della classe corrente e alle nuove proprietà definite nella classe.</span><span class="sxs-lookup"><span data-stu-id="0965f-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="0965f-152">0x300</span><span class="sxs-lookup"><span data-stu-id="0965f-152">0x300</span></span> | <span data-ttu-id="0965f-153">Maschera (anziché un flag) da applicare a un valore di `lEnumFlags` per verificare se è impostato `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`.</span><span class="sxs-lookup"><span data-stu-id="0965f-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="0965f-154">0x10</span><span class="sxs-lookup"><span data-stu-id="0965f-154">0x10</span></span> | <span data-ttu-id="0965f-155">Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="0965f-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="0965f-156">0x20</span><span class="sxs-lookup"><span data-stu-id="0965f-156">0x20</span></span> | <span data-ttu-id="0965f-157">Limitare l'enumerazione alle proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="0965f-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="0965f-158">Per le istanze:</span><span class="sxs-lookup"><span data-stu-id="0965f-158">For instances:</span></span>

<span data-ttu-id="0965f-159">Costante</span><span class="sxs-lookup"><span data-stu-id="0965f-159">Constant</span></span>  |<span data-ttu-id="0965f-160">Value</span><span class="sxs-lookup"><span data-stu-id="0965f-160">Value</span></span>  |<span data-ttu-id="0965f-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0965f-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="0965f-162">0x10</span><span class="sxs-lookup"><span data-stu-id="0965f-162">0x10</span></span> | <span data-ttu-id="0965f-163">Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="0965f-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="0965f-164">0x20</span><span class="sxs-lookup"><span data-stu-id="0965f-164">0x20</span></span> | <span data-ttu-id="0965f-165">Limitare l'enumerazione alle proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="0965f-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="0965f-166">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0965f-166">Requirements</span></span>  
 <span data-ttu-id="0965f-167">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0965f-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0965f-168">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0965f-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0965f-169">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0965f-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0965f-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0965f-170">See also</span></span>

- [<span data-ttu-id="0965f-171">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="0965f-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
