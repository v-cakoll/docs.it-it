---
title: Funzione CompareTo (riferimenti alle API non gestite)
description: La funzione CompareTo Confronta un oggetto in un altro oggetto WMI.
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
ms.openlocfilehash: fa46cf1fde4306af562248b4c12b048e3d8e2a51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717649"
---
# <a name="compareto-function"></a><span data-ttu-id="1df2b-103">CompareTo (funzione)</span><span class="sxs-lookup"><span data-stu-id="1df2b-103">CompareTo function</span></span>
<span data-ttu-id="1df2b-104">Confronta un oggetto con un altro oggetto di Gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="1df2b-104">Compares an object to another Windows management object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1df2b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1df2b-105">Syntax</span></span>  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a><span data-ttu-id="1df2b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1df2b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1df2b-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="1df2b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1df2b-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="1df2b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`  
<span data-ttu-id="1df2b-109">[in] Combinazione bit per bit di flag che specificano le caratteristiche dell'oggetto da prendere in considerazione per il confronto.</span><span class="sxs-lookup"><span data-stu-id="1df2b-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="1df2b-110">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="1df2b-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`  

<span data-ttu-id="1df2b-111">[in] Oggetto per il confronto.</span><span class="sxs-lookup"><span data-stu-id="1df2b-111">[in] The object for comparison.</span></span> <span data-ttu-id="1df2b-112">`pcompareTo` deve essere un valore valido [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) dell'istanza; non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="1df2b-112">`pcompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="1df2b-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1df2b-113">Return value</span></span>

<span data-ttu-id="1df2b-114">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1df2b-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1df2b-115">Costante</span><span class="sxs-lookup"><span data-stu-id="1df2b-115">Constant</span></span>  |<span data-ttu-id="1df2b-116">Value</span><span class="sxs-lookup"><span data-stu-id="1df2b-116">Value</span></span>  |<span data-ttu-id="1df2b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1df2b-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="1df2b-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1df2b-118">0x80041001</span></span> | <span data-ttu-id="1df2b-119">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="1df2b-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1df2b-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1df2b-120">0x80041008</span></span> | <span data-ttu-id="1df2b-121">Un parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="1df2b-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="1df2b-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="1df2b-122">0x8004101d</span></span> | <span data-ttu-id="1df2b-123">Una seconda chiamata a `BeginEnumeration` è stata eseguita senza una chiamata corrispondente a [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1df2b-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1df2b-124">0</span><span class="sxs-lookup"><span data-stu-id="1df2b-124">0</span></span> | <span data-ttu-id="1df2b-125">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="1df2b-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="1df2b-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="1df2b-126">0x40003</span></span> | <span data-ttu-id="1df2b-127">Gli oggetti sono diversi.</span><span class="sxs-lookup"><span data-stu-id="1df2b-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="1df2b-128">0</span><span class="sxs-lookup"><span data-stu-id="1df2b-128">0</span></span> | <span data-ttu-id="1df2b-129">Gli oggetti corrispondono in base ai flag di confronto.</span><span class="sxs-lookup"><span data-stu-id="1df2b-129">The objects are the same based on the comparison flags.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="1df2b-130">Note</span><span class="sxs-lookup"><span data-stu-id="1df2b-130">Remarks</span></span>

<span data-ttu-id="1df2b-131">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) (metodo).</span><span class="sxs-lookup"><span data-stu-id="1df2b-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="1df2b-132">I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="1df2b-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="1df2b-133">È possibile specificare le caratteristiche singole coinvolti nel confronto specificando una combinazione bit per bit dei flag seguenti:</span><span class="sxs-lookup"><span data-stu-id="1df2b-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="1df2b-134">Costante</span><span class="sxs-lookup"><span data-stu-id="1df2b-134">Constant</span></span>  |<span data-ttu-id="1df2b-135">Value</span><span class="sxs-lookup"><span data-stu-id="1df2b-135">Value</span></span>  |<span data-ttu-id="1df2b-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1df2b-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="1df2b-137">2</span><span class="sxs-lookup"><span data-stu-id="1df2b-137">2</span></span> | <span data-ttu-id="1df2b-138">Ignorare l'origine (server e lo spazio dei nomi da cui provengono).</span><span class="sxs-lookup"><span data-stu-id="1df2b-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="1df2b-139">1</span><span class="sxs-lookup"><span data-stu-id="1df2b-139">1</span></span> | <span data-ttu-id="1df2b-140">Ignora tutti i qualificatori (incluso **Key** e **dinamico**)</span><span class="sxs-lookup"><span data-stu-id="1df2b-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="1df2b-141">4</span><span class="sxs-lookup"><span data-stu-id="1df2b-141">4</span></span> | <span data-ttu-id="1df2b-142">Ignora valori predefiniti delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="1df2b-142">Ignore default values of properties.</span></span> <span data-ttu-id="1df2b-143">Questo flag si applica solo al confronto delle classi.</span><span class="sxs-lookup"><span data-stu-id="1df2b-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="1df2b-144">0x20</span><span class="sxs-lookup"><span data-stu-id="1df2b-144">0x20</span></span> | <span data-ttu-id="1df2b-145">Ignora contrassegno qualificatore.</span><span class="sxs-lookup"><span data-stu-id="1df2b-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="1df2b-146">Questo flag ancora qualificatori di prende in considerazione, ma ignora le distinzioni tra le quali le regole di propagazione e ignorare le restrizioni.</span><span class="sxs-lookup"><span data-stu-id="1df2b-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="1df2b-147">0x10</span><span class="sxs-lookup"><span data-stu-id="1df2b-147">0x10</span></span> | <span data-ttu-id="1df2b-148">Ignora maiuscole/minuscole nel confronto dei valori di stringa.</span><span class="sxs-lookup"><span data-stu-id="1df2b-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="1df2b-149">Questo vale sia per le stringhe e valori di qualificatore.</span><span class="sxs-lookup"><span data-stu-id="1df2b-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="1df2b-150">Il confronto dei nomi di proprietà e il qualificatore è sempre tra maiuscole e minuscole indipendentemente dal fatto che questo flag è impostato.</span><span class="sxs-lookup"><span data-stu-id="1df2b-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="1df2b-151">0x8</span><span class="sxs-lookup"><span data-stu-id="1df2b-151">0x8</span></span> | <span data-ttu-id="1df2b-152">Si supponga che gli oggetti da confrontare siano istanze della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="1df2b-152">Assume that the objects being compared are instanes of the same class.</span></span> <span data-ttu-id="1df2b-153">Di conseguenza, questo flag vengono confrontate solo informazioni relativa all'istanza.</span><span class="sxs-lookup"><span data-stu-id="1df2b-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="1df2b-154">Usare questo flag per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1df2b-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="1df2b-155">Se gli oggetti non sono della stessa classe, i risultati sono indefiniti.</span><span class="sxs-lookup"><span data-stu-id="1df2b-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="1df2b-156">In alternativa, è possibile specificare un singolo flag composito, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1df2b-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="1df2b-157">Costante</span><span class="sxs-lookup"><span data-stu-id="1df2b-157">Constant</span></span>  |<span data-ttu-id="1df2b-158">Valore</span><span class="sxs-lookup"><span data-stu-id="1df2b-158">Value</span></span>  |<span data-ttu-id="1df2b-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1df2b-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="1df2b-160">0</span><span class="sxs-lookup"><span data-stu-id="1df2b-160">0</span></span> | <span data-ttu-id="1df2b-161">Prendere in considerazione tutte le funzionalità nel confronto.</span><span class="sxs-lookup"><span data-stu-id="1df2b-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="1df2b-162">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1df2b-162">Requirements</span></span>  
 <span data-ttu-id="1df2b-163">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1df2b-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1df2b-164">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1df2b-164">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1df2b-165">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1df2b-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df2b-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1df2b-166">See also</span></span>
- [<span data-ttu-id="1df2b-167">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1df2b-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
