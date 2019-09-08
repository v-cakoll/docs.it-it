---
title: Funzione GetNames (riferimenti alle API non gestite)
description: La funzione GetNames recupera i nomi delle proprietà di un oggetto.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 748767596a8f4680a2d7b63cb0579acaed5f53f8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798522"
---
# <a name="getnames-function"></a><span data-ttu-id="d0ee9-103">Funzione GetNames</span><span class="sxs-lookup"><span data-stu-id="d0ee9-103">GetNames function</span></span>
<span data-ttu-id="d0ee9-104">Recupera un subset o tutti i nomi delle proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d0ee9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0ee9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="d0ee9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0ee9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d0ee9-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d0ee9-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="d0ee9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="d0ee9-109">in Puntatore a un oggetto valido `LPCWSTR` che specifica un nome di qualificatore che opera come parte di un filtro.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="d0ee9-110">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="d0ee9-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="d0ee9-111">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="d0ee9-112">in Combinazione di campi di bit.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="d0ee9-113">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="d0ee9-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="d0ee9-114">in Puntatore a una struttura valida `VARIANT` inizializzata su un valore di filtro.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="d0ee9-115">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="d0ee9-116">out `SAFEARRAY` Struttura che contiene i nomi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="d0ee9-117">Alla voce, questo parametro deve essere sempre un puntatore a `null`.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="d0ee9-118">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="d0ee9-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="d0ee9-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d0ee9-119">Return value</span></span>

<span data-ttu-id="d0ee9-120">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="d0ee9-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d0ee9-121">Costante</span><span class="sxs-lookup"><span data-stu-id="d0ee9-121">Constant</span></span>  |<span data-ttu-id="d0ee9-122">Value</span><span class="sxs-lookup"><span data-stu-id="d0ee9-122">Value</span></span>  |<span data-ttu-id="d0ee9-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0ee9-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="d0ee9-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d0ee9-124">0x80041001</span></span> | <span data-ttu-id="d0ee9-125">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d0ee9-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d0ee9-126">0x80041008</span></span> | <span data-ttu-id="d0ee9-127">Uno o più parametri non sono validi oppure è stata specificata una combinazione non corretta di flag e parametri.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d0ee9-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d0ee9-128">0x80041006</span></span> | <span data-ttu-id="d0ee9-129">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d0ee9-130">0</span><span class="sxs-lookup"><span data-stu-id="d0ee9-130">0</span></span> | <span data-ttu-id="d0ee9-131">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d0ee9-132">Note</span><span class="sxs-lookup"><span data-stu-id="d0ee9-132">Remarks</span></span>

<span data-ttu-id="d0ee9-133">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) .</span><span class="sxs-lookup"><span data-stu-id="d0ee9-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="d0ee9-134">Il denominato restituito è controllato da una combinazione di flag e parametri.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="d0ee9-135">Ad esempio, la funzione può restituire i nomi di tutte le proprietà o solo i nomi delle proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="d0ee9-136">Il filtro primario viene specificato nel `lFlags` parametro e gli altri parametri variano a seconda del parametro.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="d0ee9-137">I valori dei flag `lFlags` in sono campi di bit</span><span class="sxs-lookup"><span data-stu-id="d0ee9-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="d0ee9-138">I flag che possono essere passati come `lEnumFlags` argomento sono i campi di bit definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="d0ee9-139">È possibile combinare un flag di ogni gruppo con qualsiasi flag di qualsiasi altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="d0ee9-140">Tuttavia, i flag dello stesso gruppo si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="d0ee9-141">Flag gruppo 1</span><span class="sxs-lookup"><span data-stu-id="d0ee9-141">Group 1 flags</span></span> |<span data-ttu-id="d0ee9-142">Value</span><span class="sxs-lookup"><span data-stu-id="d0ee9-142">Value</span></span>  |<span data-ttu-id="d0ee9-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0ee9-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="d0ee9-144">0</span><span class="sxs-lookup"><span data-stu-id="d0ee9-144">0</span></span> | <span data-ttu-id="d0ee9-145">Restituisce tutti i nomi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-145">Return all property names.</span></span> <span data-ttu-id="d0ee9-146">`strQualifierName`e `pQualifierVal` sono inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="d0ee9-147">1</span><span class="sxs-lookup"><span data-stu-id="d0ee9-147">1</span></span> | <span data-ttu-id="d0ee9-148">Restituisce solo le proprietà con un qualificatore del nome specificato dal `strQualifierName` parametro.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="d0ee9-149">Se viene usato questo flag, è necessario specificare `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="d0ee9-150">2</span><span class="sxs-lookup"><span data-stu-id="d0ee9-150">2</span></span> |  <span data-ttu-id="d0ee9-151">Restituisce solo le proprietà che non dispongono di un qualificatore del nome specificato dal `strQualifierName` parametro.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="d0ee9-152">Se viene usato questo flag, è necessario specificare `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="d0ee9-153">3</span><span class="sxs-lookup"><span data-stu-id="d0ee9-153">3</span></span> | <span data-ttu-id="d0ee9-154">Restituisce solo le proprietà che hanno un qualificatore del nome specificato dal `wszQualifierName` parametro e hanno anche un valore identico a quello specificato `pQualifierVal` dalla struttura.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="d0ee9-155">Se viene usato questo flag, è necessario specificare sia `wszQualifierName` `pQualifierValue`che.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="d0ee9-156">Flag gruppo 2</span><span class="sxs-lookup"><span data-stu-id="d0ee9-156">Group 2 flags</span></span> |<span data-ttu-id="d0ee9-157">Value</span><span class="sxs-lookup"><span data-stu-id="d0ee9-157">Value</span></span>  |<span data-ttu-id="d0ee9-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0ee9-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="d0ee9-159">0x4</span><span class="sxs-lookup"><span data-stu-id="d0ee9-159">0x4</span></span> | <span data-ttu-id="d0ee9-160">Restituisce solo i nomi delle proprietà che definiscono le chiavi.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="d0ee9-161">0x8</span><span class="sxs-lookup"><span data-stu-id="d0ee9-161">0x8</span></span> | <span data-ttu-id="d0ee9-162">Restituisce solo i nomi di proprietà che sono riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="d0ee9-163">Flag gruppo 3</span><span class="sxs-lookup"><span data-stu-id="d0ee9-163">Group 3 flags</span></span> |<span data-ttu-id="d0ee9-164">Value</span><span class="sxs-lookup"><span data-stu-id="d0ee9-164">Value</span></span>  |<span data-ttu-id="d0ee9-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0ee9-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="d0ee9-166">0x10</span><span class="sxs-lookup"><span data-stu-id="d0ee9-166">0x10</span></span> | <span data-ttu-id="d0ee9-167">Restituisce solo i nomi di proprietà che appartengono alla classe più derivata.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="d0ee9-168">Escludere le proprietà dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="d0ee9-169">0x20</span><span class="sxs-lookup"><span data-stu-id="d0ee9-169">0x20</span></span> | <span data-ttu-id="d0ee9-170">Restituisce solo i nomi delle proprietà che appartengono alle classi padre.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="d0ee9-171">0x30</span><span class="sxs-lookup"><span data-stu-id="d0ee9-171">0x30</span></span> | <span data-ttu-id="d0ee9-172">Restituisce solo i nomi delle proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="d0ee9-173">0x40</span><span class="sxs-lookup"><span data-stu-id="d0ee9-173">0x40</span></span> | <span data-ttu-id="d0ee9-174">Restituisce solo i nomi delle proprietà non di sistema.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="d0ee9-175">La funzione alloca sempre un nuovo `SAFEARRAY` se restituisce `WBEM_S_NO_ERROR`ed `pstrNames` è sempre impostato in modo da puntare a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="d0ee9-176">La matrice restituita può avere 0 elementi se nessuna proprietà corrisponde ai filtri specificati.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="d0ee9-177">Se la funzione restituisce un valore diverso da `WBM_S_NO_ERROR`, non viene `SAFEARRAY` restituita una nuova struttura.</span><span class="sxs-lookup"><span data-stu-id="d0ee9-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="d0ee9-178">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d0ee9-178">Requirements</span></span>  
 <span data-ttu-id="d0ee9-179">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0ee9-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0ee9-180">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="d0ee9-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d0ee9-181">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d0ee9-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ee9-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0ee9-182">See also</span></span>

- [<span data-ttu-id="d0ee9-183">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d0ee9-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
