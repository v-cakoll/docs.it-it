---
title: BeginEnumeration function (Unmanaged API Reference)
description: La funzione BeginEnumeration reimposta un enumeratore all'inizio dell'enumerazione
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
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176877"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="f7b4a-103">Funzione BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="f7b4a-103">BeginEnumeration function</span></span>
<span data-ttu-id="f7b4a-104">Reimposta un enumeratore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f7b4a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7b4a-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="f7b4a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7b4a-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="f7b4a-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="f7b4a-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="f7b4a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="f7b4a-109">[in] Combinazione bit per bit dei flag o dei valori descritti nella sezione [Osservazioni](#remarks) che controlla le proprietà incluse nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="f7b4a-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f7b4a-110">Return value</span></span>

<span data-ttu-id="f7b4a-111">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="f7b4a-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f7b4a-112">Costante</span><span class="sxs-lookup"><span data-stu-id="f7b4a-112">Constant</span></span>  |<span data-ttu-id="f7b4a-113">valore</span><span class="sxs-lookup"><span data-stu-id="f7b4a-113">Value</span></span>  |<span data-ttu-id="f7b4a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b4a-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f7b4a-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f7b4a-115">0x80041008</span></span> | <span data-ttu-id="f7b4a-116">La combinazione di `lEnumFlags` flag in non è valida o è stato specificato un argomento non valido.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="f7b4a-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f7b4a-117">0x8004101d</span></span> | <span data-ttu-id="f7b4a-118">Una seconda `BeginEnumeration` chiamata è stata fatta [`EndEnumeration`](endenumeration.md)senza una chiamata intermedia a .</span><span class="sxs-lookup"><span data-stu-id="f7b4a-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f7b4a-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f7b4a-119">0x80041006</span></span> | <span data-ttu-id="f7b4a-120">Memoria insufficiente per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f7b4a-121">0</span><span class="sxs-lookup"><span data-stu-id="f7b4a-121">0</span></span> | <span data-ttu-id="f7b4a-122">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f7b4a-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f7b4a-123">Remarks</span></span>

<span data-ttu-id="f7b4a-124">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="f7b4a-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="f7b4a-125">I flag che possono `lEnumFlags` essere passati come argomento sono definiti nel file di intestazione *WbemCli.h* oppure è possibile definirli come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="f7b4a-126">È possibile combinare un flag di ogni gruppo con qualsiasi flag di qualsiasi altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="f7b4a-127">Tuttavia, i flag dello stesso gruppo si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="f7b4a-128">**Gruppo 1**</span><span class="sxs-lookup"><span data-stu-id="f7b4a-128">**Group 1**</span></span>

|<span data-ttu-id="f7b4a-129">Costante</span><span class="sxs-lookup"><span data-stu-id="f7b4a-129">Constant</span></span>  |<span data-ttu-id="f7b4a-130">valore</span><span class="sxs-lookup"><span data-stu-id="f7b4a-130">Value</span></span>  |<span data-ttu-id="f7b4a-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b4a-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="f7b4a-132">0x4</span><span class="sxs-lookup"><span data-stu-id="f7b4a-132">0x4</span></span> | <span data-ttu-id="f7b4a-133">Includere solo le proprietà che costituiscono la chiave.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="f7b4a-134">0x8</span><span class="sxs-lookup"><span data-stu-id="f7b4a-134">0x8</span></span> | <span data-ttu-id="f7b4a-135">Includere solo le proprietà che sono riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="f7b4a-136">**Gruppo 2**</span><span class="sxs-lookup"><span data-stu-id="f7b4a-136">**Group 2**</span></span>

<span data-ttu-id="f7b4a-137">Costante</span><span class="sxs-lookup"><span data-stu-id="f7b4a-137">Constant</span></span>  |<span data-ttu-id="f7b4a-138">valore</span><span class="sxs-lookup"><span data-stu-id="f7b4a-138">Value</span></span>  |<span data-ttu-id="f7b4a-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b4a-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="f7b4a-140">0x30 (in modo 0x30)</span><span class="sxs-lookup"><span data-stu-id="f7b4a-140">0x30</span></span> | <span data-ttu-id="f7b4a-141">Limitare l'enumerazione solo alle proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="f7b4a-142">0x40</span><span class="sxs-lookup"><span data-stu-id="f7b4a-142">0x40</span></span> | <span data-ttu-id="f7b4a-143">Includere le proprietà locali e propagate ma escludere le proprietà di sistema dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="f7b4a-144">Per le classi:</span><span class="sxs-lookup"><span data-stu-id="f7b4a-144">For classes:</span></span>

<span data-ttu-id="f7b4a-145">Costante</span><span class="sxs-lookup"><span data-stu-id="f7b4a-145">Constant</span></span>  |<span data-ttu-id="f7b4a-146">valore</span><span class="sxs-lookup"><span data-stu-id="f7b4a-146">Value</span></span>  |<span data-ttu-id="f7b4a-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b4a-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="f7b4a-148">0x100</span><span class="sxs-lookup"><span data-stu-id="f7b4a-148">0x100</span></span> | <span data-ttu-id="f7b4a-149">Limitare l'enumerazione alle proprietà sottoposte a override nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="f7b4a-150">0x100</span><span class="sxs-lookup"><span data-stu-id="f7b4a-150">0x100</span></span> | <span data-ttu-id="f7b4a-151">Limitare l'enumerazione alle proprietà sottoposte a override nella definizione di classe corrente e alle nuove proprietà definite nella classe.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="f7b4a-152">0x300 (in 300)</span><span class="sxs-lookup"><span data-stu-id="f7b4a-152">0x300</span></span> | <span data-ttu-id="f7b4a-153">Maschera (anziché un flag) da `lEnumFlags` applicare a `WBEM_FLAG_CLASS_OVERRIDES_ONLY` un `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` valore per verificare se è o è impostato.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="f7b4a-154">0x10</span><span class="sxs-lookup"><span data-stu-id="f7b4a-154">0x10</span></span> | <span data-ttu-id="f7b4a-155">Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="f7b4a-156">0x20</span><span class="sxs-lookup"><span data-stu-id="f7b4a-156">0x20</span></span> | <span data-ttu-id="f7b4a-157">Limitare l'enumerazione alle proprietà ereditate dalle classi base.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="f7b4a-158">Per le istanze:</span><span class="sxs-lookup"><span data-stu-id="f7b4a-158">For instances:</span></span>

<span data-ttu-id="f7b4a-159">Costante</span><span class="sxs-lookup"><span data-stu-id="f7b4a-159">Constant</span></span>  |<span data-ttu-id="f7b4a-160">valore</span><span class="sxs-lookup"><span data-stu-id="f7b4a-160">Value</span></span>  |<span data-ttu-id="f7b4a-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7b4a-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="f7b4a-162">0x10</span><span class="sxs-lookup"><span data-stu-id="f7b4a-162">0x10</span></span> | <span data-ttu-id="f7b4a-163">Limitare l'enumerazione alle proprietà definite o modificate nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="f7b4a-164">0x20</span><span class="sxs-lookup"><span data-stu-id="f7b4a-164">0x20</span></span> | <span data-ttu-id="f7b4a-165">Limitare l'enumerazione alle proprietà ereditate dalle classi base.</span><span class="sxs-lookup"><span data-stu-id="f7b4a-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="f7b4a-166">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7b4a-166">Requirements</span></span>  
 <span data-ttu-id="f7b4a-167">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b4a-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b4a-168">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f7b4a-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f7b4a-169">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b4a-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b4a-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b4a-170">See also</span></span>

- [<span data-ttu-id="f7b4a-171">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f7b4a-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
