---
title: Funzione CompareTo (riferimenti alle API non gestite)
description: La funzione CompareTo confronta un oggetto con un altro oggetto WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128703"
---
# <a name="compareto-function"></a><span data-ttu-id="97758-103">Funzione CompareTo</span><span class="sxs-lookup"><span data-stu-id="97758-103">CompareTo function</span></span>

<span data-ttu-id="97758-104">Confronta un oggetto con un altro oggetto di Gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="97758-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="97758-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97758-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="97758-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="97758-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="97758-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="97758-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="97758-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="97758-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="97758-109">in Combinazione bit per bit dei flag che specificano le caratteristiche dell'oggetto da considerare per il confronto.</span><span class="sxs-lookup"><span data-stu-id="97758-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="97758-110">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="97758-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="97758-111">in Oggetto per il confronto.</span><span class="sxs-lookup"><span data-stu-id="97758-111">[in] The object for comparison.</span></span> <span data-ttu-id="97758-112">`pCompareTo` deve essere un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) valida; non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="97758-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="97758-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97758-113">Return value</span></span>

<span data-ttu-id="97758-114">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="97758-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="97758-115">Costante</span><span class="sxs-lookup"><span data-stu-id="97758-115">Constant</span></span>  |<span data-ttu-id="97758-116">Value</span><span class="sxs-lookup"><span data-stu-id="97758-116">Value</span></span>  |<span data-ttu-id="97758-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97758-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="97758-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="97758-118">0x80041001</span></span> | <span data-ttu-id="97758-119">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="97758-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="97758-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="97758-120">0x80041008</span></span> | <span data-ttu-id="97758-121">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="97758-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="97758-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="97758-122">0x8004101d</span></span> | <span data-ttu-id="97758-123">Una seconda chiamata a `BeginEnumeration` è stata effettuata senza una chiamata corrispondente a [`EndEnumeration`](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="97758-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="97758-124">0</span><span class="sxs-lookup"><span data-stu-id="97758-124">0</span></span> | <span data-ttu-id="97758-125">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="97758-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="97758-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="97758-126">0x40003</span></span> | <span data-ttu-id="97758-127">Gli oggetti sono diversi.</span><span class="sxs-lookup"><span data-stu-id="97758-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="97758-128">0</span><span class="sxs-lookup"><span data-stu-id="97758-128">0</span></span> | <span data-ttu-id="97758-129">Gli oggetti sono gli stessi in base ai flag di confronto.</span><span class="sxs-lookup"><span data-stu-id="97758-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="97758-130">Note</span><span class="sxs-lookup"><span data-stu-id="97758-130">Remarks</span></span>

<span data-ttu-id="97758-131">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) .</span><span class="sxs-lookup"><span data-stu-id="97758-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="97758-132">I flag che possono essere passati come `lEnumFlags` argomento vengono definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="97758-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="97758-133">È possibile specificare le singole caratteristiche necessarie per il confronto specificando una combinazione bit per bit dei flag seguenti:</span><span class="sxs-lookup"><span data-stu-id="97758-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="97758-134">Costante</span><span class="sxs-lookup"><span data-stu-id="97758-134">Constant</span></span>  |<span data-ttu-id="97758-135">Value</span><span class="sxs-lookup"><span data-stu-id="97758-135">Value</span></span>  |<span data-ttu-id="97758-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97758-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="97758-137">2</span><span class="sxs-lookup"><span data-stu-id="97758-137">2</span></span> | <span data-ttu-id="97758-138">Ignorare l'origine (il server e lo spazio dei nomi da cui provengono).</span><span class="sxs-lookup"><span data-stu-id="97758-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="97758-139">1</span><span class="sxs-lookup"><span data-stu-id="97758-139">1</span></span> | <span data-ttu-id="97758-140">Ignora tutti i qualificatori (incluse la **chiave** e la **dinamica**)</span><span class="sxs-lookup"><span data-stu-id="97758-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="97758-141">4</span><span class="sxs-lookup"><span data-stu-id="97758-141">4</span></span> | <span data-ttu-id="97758-142">Ignorare i valori predefiniti delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="97758-142">Ignore default values of properties.</span></span> <span data-ttu-id="97758-143">Questo flag è valido solo per il confronto delle classi.</span><span class="sxs-lookup"><span data-stu-id="97758-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="97758-144">0x20</span><span class="sxs-lookup"><span data-stu-id="97758-144">0x20</span></span> | <span data-ttu-id="97758-145">Ignora le versioni del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="97758-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="97758-146">Questo flag prende ancora in considerazione i qualificatori, ma ignora le distinzioni di sapore, ad esempio le regole di propagazione e le restrizioni di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="97758-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="97758-147">0x10</span><span class="sxs-lookup"><span data-stu-id="97758-147">0x10</span></span> | <span data-ttu-id="97758-148">Ignora case per il confronto di valori stringa.</span><span class="sxs-lookup"><span data-stu-id="97758-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="97758-149">Questo vale sia per le stringhe che per i valori del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="97758-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="97758-150">Il confronto dei nomi di proprietà e qualificatore è sempre distinzione tra maiuscole e minuscole, indipendentemente dal fatto che questo flag sia impostato.</span><span class="sxs-lookup"><span data-stu-id="97758-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="97758-151">0x8</span><span class="sxs-lookup"><span data-stu-id="97758-151">0x8</span></span> | <span data-ttu-id="97758-152">Si supponga che gli oggetti da confrontare siano istanze della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="97758-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="97758-153">Di conseguenza, questo flag confronta solo le informazioni correlate all'istanza.</span><span class="sxs-lookup"><span data-stu-id="97758-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="97758-154">Usare questi flag per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="97758-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="97758-155">Se gli oggetti non sono della stessa classe, i risultati non sono definiti.</span><span class="sxs-lookup"><span data-stu-id="97758-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="97758-156">In alternativa, è possibile specificare un singolo flag composito come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="97758-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="97758-157">Costante</span><span class="sxs-lookup"><span data-stu-id="97758-157">Constant</span></span>  |<span data-ttu-id="97758-158">Value</span><span class="sxs-lookup"><span data-stu-id="97758-158">Value</span></span>  |<span data-ttu-id="97758-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97758-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="97758-160">0</span><span class="sxs-lookup"><span data-stu-id="97758-160">0</span></span> | <span data-ttu-id="97758-161">Prendere in considerazione tutte le funzionalità del confronto.</span><span class="sxs-lookup"><span data-stu-id="97758-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="97758-162">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97758-162">Requirements</span></span>

<span data-ttu-id="97758-163">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97758-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="97758-164">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="97758-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="97758-165">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="97758-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="97758-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97758-166">See also</span></span>

- [<span data-ttu-id="97758-167">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="97758-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
