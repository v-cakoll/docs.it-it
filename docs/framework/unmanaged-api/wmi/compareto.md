---
title: Funzione CompareTo (riferimenti alle API non gestite)
description: La funzione CompareTo Confronta un oggetto a un altro oggetto WMI.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460408"
---
# <a name="compareto-function"></a><span data-ttu-id="a1ef9-103">CompareTo (funzione)</span><span class="sxs-lookup"><span data-stu-id="a1ef9-103">CompareTo function</span></span>
<span data-ttu-id="a1ef9-104">Confronta un oggetto a un altro oggetto di gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-104">Compares an object to another Windows management object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="a1ef9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1ef9-105">Syntax</span></span>  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a><span data-ttu-id="a1ef9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1ef9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a1ef9-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a1ef9-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`flags`  
<span data-ttu-id="a1ef9-109">[in] Combinazione bit per bit di flag che specificano le caratteristiche di oggetto da prendere in considerazione per il confronto.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="a1ef9-110">Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`  

<span data-ttu-id="a1ef9-111">[in] Oggetto per il confronto.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-111">[in] The object for comparison.</span></span> <span data-ttu-id="a1ef9-112">`pcompareTo` deve essere un valore valido [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) dell'istanza; non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-112">`pcompareTo` must be a valid [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a1ef9-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1ef9-113">Return value</span></span>

<span data-ttu-id="a1ef9-114">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="a1ef9-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a1ef9-115">Costante</span><span class="sxs-lookup"><span data-stu-id="a1ef9-115">Constant</span></span>  |<span data-ttu-id="a1ef9-116">Valore</span><span class="sxs-lookup"><span data-stu-id="a1ef9-116">Value</span></span>  |<span data-ttu-id="a1ef9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1ef9-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="a1ef9-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a1ef9-118">0x80041001</span></span> | <span data-ttu-id="a1ef9-119">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a1ef9-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a1ef9-120">0x80041008</span></span> | <span data-ttu-id="a1ef9-121">Un parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="a1ef9-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="a1ef9-122">0x8004101d</span></span> | <span data-ttu-id="a1ef9-123">Una seconda chiamata a `BeginEnumeration` è stato eseguito senza una corrispondente chiamata a [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="a1ef9-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="a1ef9-124">0</span><span class="sxs-lookup"><span data-stu-id="a1ef9-124">0</span></span> | <span data-ttu-id="a1ef9-125">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="a1ef9-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="a1ef9-126">0x40003</span></span> | <span data-ttu-id="a1ef9-127">Gli oggetti sono diversi.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="a1ef9-128">0</span><span class="sxs-lookup"><span data-stu-id="a1ef9-128">0</span></span> | <span data-ttu-id="a1ef9-129">Gli oggetti sono uguali in base ai flag di confronto.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-129">The objects are the same based on the comparison flags.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="a1ef9-130">Note</span><span class="sxs-lookup"><span data-stu-id="a1ef9-130">Remarks</span></span>

<span data-ttu-id="a1ef9-131">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-131">This function wraps a call to the [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a1ef9-132">I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="a1ef9-133">È possibile specificare le caratteristiche singole coinvolti nel confronto specificando una combinazione bit per bit dei flag seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1ef9-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="a1ef9-134">Costante</span><span class="sxs-lookup"><span data-stu-id="a1ef9-134">Constant</span></span>  |<span data-ttu-id="a1ef9-135">Valore</span><span class="sxs-lookup"><span data-stu-id="a1ef9-135">Value</span></span>  |<span data-ttu-id="a1ef9-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1ef9-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="a1ef9-137">2</span><span class="sxs-lookup"><span data-stu-id="a1ef9-137">2</span></span> | <span data-ttu-id="a1ef9-138">Ignorare l'origine (il server e lo spazio dei nomi da cui provengono).</span><span class="sxs-lookup"><span data-stu-id="a1ef9-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="a1ef9-139">1</span><span class="sxs-lookup"><span data-stu-id="a1ef9-139">1</span></span> | <span data-ttu-id="a1ef9-140">Ignorare tutti i qualificatori (inclusi **chiave** e **dinamica**)</span><span class="sxs-lookup"><span data-stu-id="a1ef9-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="a1ef9-141">4</span><span class="sxs-lookup"><span data-stu-id="a1ef9-141">4</span></span> | <span data-ttu-id="a1ef9-142">Ignora valori predefiniti delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-142">Ignore default values of properties.</span></span> <span data-ttu-id="a1ef9-143">Questo flag si applica solo al confronto delle classi.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="a1ef9-144">0x20</span><span class="sxs-lookup"><span data-stu-id="a1ef9-144">0x20</span></span> | <span data-ttu-id="a1ef9-145">Ignorare versioni del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="a1ef9-146">Questo flag ancora considerando qualificatori, ma ignora le distinzioni tra le quali le regole di propagazione e ignorare le restrizioni.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="a1ef9-147">0x10</span><span class="sxs-lookup"><span data-stu-id="a1ef9-147">0x10</span></span> | <span data-ttu-id="a1ef9-148">Ignorare i casi il confronto dei valori di stringa.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="a1ef9-149">Questo vale sia per le stringhe e valori del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="a1ef9-150">Il confronto dei nomi di proprietà e il qualificatore è sempre tra maiuscole e minuscole indipendentemente dal fatto se questo flag è impostato.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="a1ef9-151">0x8</span><span class="sxs-lookup"><span data-stu-id="a1ef9-151">0x8</span></span> | <span data-ttu-id="a1ef9-152">Si supponga che gli oggetti confrontati sono istanze della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-152">Assume that the objects being compared are instanes of the same class.</span></span> <span data-ttu-id="a1ef9-153">Di conseguenza, questo flag confronta solo informazioni correlate all'istanza.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="a1ef9-154">Utilizzare questo flag per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="a1ef9-155">Se gli oggetti non sono della stessa classe, i risultati sono indefiniti.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="a1ef9-156">In alternativa, è possibile specificare un solo flag composito come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a1ef9-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="a1ef9-157">Costante</span><span class="sxs-lookup"><span data-stu-id="a1ef9-157">Constant</span></span>  |<span data-ttu-id="a1ef9-158">Valore</span><span class="sxs-lookup"><span data-stu-id="a1ef9-158">Value</span></span>  |<span data-ttu-id="a1ef9-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1ef9-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="a1ef9-160">0</span><span class="sxs-lookup"><span data-stu-id="a1ef9-160">0</span></span> | <span data-ttu-id="a1ef9-161">Prendere in considerazione tutte le funzionalità di confronto.</span><span class="sxs-lookup"><span data-stu-id="a1ef9-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="a1ef9-162">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1ef9-162">Requirements</span></span>  
 <span data-ttu-id="a1ef9-163">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1ef9-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1ef9-164">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a1ef9-164">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a1ef9-165">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a1ef9-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ef9-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1ef9-166">See also</span></span>  
[<span data-ttu-id="a1ef9-167">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="a1ef9-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
