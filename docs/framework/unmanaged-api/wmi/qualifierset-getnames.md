---
title: Funzione QualifierSet_GetNames (riferimenti alle API non gestite)
description: La funzione QualifierSet_GetNames recupera i nomi dei qualificatori da un oggetto o una proprietà.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84059c5e5542e13b1d4fc4efcfc4c7f418db391e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877937"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="1749a-103">QualifierSet_GetNames (funzione)</span><span class="sxs-lookup"><span data-stu-id="1749a-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="1749a-104">Recupera i nomi di tutti i qualificatori o di determinati qualificatori disponibili dall'oggetto corrente o la proprietà.</span><span class="sxs-lookup"><span data-stu-id="1749a-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1749a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1749a-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="1749a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1749a-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="1749a-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="1749a-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1749a-108">[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.</span><span class="sxs-lookup"><span data-stu-id="1749a-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="1749a-109">[in] Uno dei seguenti flag o valori che specifica i nomi da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1749a-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="1749a-110">Costante</span><span class="sxs-lookup"><span data-stu-id="1749a-110">Constant</span></span>  |<span data-ttu-id="1749a-111">Valore</span><span class="sxs-lookup"><span data-stu-id="1749a-111">Value</span></span>  |<span data-ttu-id="1749a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1749a-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="1749a-113">0</span><span class="sxs-lookup"><span data-stu-id="1749a-113">0</span></span> | <span data-ttu-id="1749a-114">Restituire i nomi di tutti i qualificatori.</span><span class="sxs-lookup"><span data-stu-id="1749a-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="1749a-115">0x10</span><span class="sxs-lookup"><span data-stu-id="1749a-115">0x10</span></span> | <span data-ttu-id="1749a-116">Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1749a-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="1749a-117">Per una proprietà: restituire solo i qualificatori specifici per la proprietà (incluse le sostituzioni) e non i qualificatori propagata dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="1749a-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="1749a-118">Per un'istanza: restituire solo i nomi di qualificatore specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="1749a-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="1749a-119">Per una classe: restituire solo i qualificatori specifico beiong la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1749a-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="1749a-120">0x20</span><span class="sxs-lookup"><span data-stu-id="1749a-120">0x20</span></span> | <span data-ttu-id="1749a-121">Restituisce solo i nomi dei qualificatori propagati da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="1749a-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="1749a-122">Per una proprietà: restituire solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli dalla proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="1749a-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="1749a-123">Per un'istanza: restituzione solo tali qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="1749a-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="1749a-124">Per una classe: restituire solo i nomi di qualificatore ereditati dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="1749a-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="1749a-125">`pstrNames` [out] Un nuovo `SAFEARRAY` che contiene i nomi richiesti.</span><span class="sxs-lookup"><span data-stu-id="1749a-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="1749a-126">La matrice può contenere 0 elementi.</span><span class="sxs-lookup"><span data-stu-id="1749a-126">The array can have 0 elements.</span></span> <span data-ttu-id="1749a-127">Se si verifica un errore, un nuovo `SAFEARRAY` non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="1749a-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="1749a-128">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1749a-128">Return value</span></span>

<span data-ttu-id="1749a-129">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1749a-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1749a-130">Costante</span><span class="sxs-lookup"><span data-stu-id="1749a-130">Constant</span></span>  |<span data-ttu-id="1749a-131">Valore</span><span class="sxs-lookup"><span data-stu-id="1749a-131">Value</span></span>  |<span data-ttu-id="1749a-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1749a-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1749a-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1749a-133">0x80041008</span></span> | <span data-ttu-id="1749a-134">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="1749a-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1749a-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1749a-135">0x80041006</span></span> | <span data-ttu-id="1749a-136">Memoria insufficiente è disponibile per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1749a-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1749a-137">0</span><span class="sxs-lookup"><span data-stu-id="1749a-137">0</span></span> | <span data-ttu-id="1749a-138">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="1749a-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1749a-139">Note</span><span class="sxs-lookup"><span data-stu-id="1749a-139">Remarks</span></span>

<span data-ttu-id="1749a-140">Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) (metodo).</span><span class="sxs-lookup"><span data-stu-id="1749a-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="1749a-141">Dopo aver recuperato i nomi di qualificatore, è possibile accedere in base al nome ogni qualificatore chiamando il [QualifierSet_Get](qualifierset-get.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="1749a-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="1749a-142">Non è un errore per un determinato oggetto di avere zero qualificatori, pertanto il numero di stringhe nelle `pstrNames` nell'output restituito può essere 0, anche se la funzione restituisce `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="1749a-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="1749a-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1749a-143">Requirements</span></span>  
 <span data-ttu-id="1749a-144">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1749a-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1749a-145">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1749a-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1749a-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1749a-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1749a-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1749a-147">See also</span></span>  
[<span data-ttu-id="1749a-148">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1749a-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
