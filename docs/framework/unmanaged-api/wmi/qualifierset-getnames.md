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
ms.openlocfilehash: b7c96439cf50c18e336baa70cf463b9463203290
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461178"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="bb365-103">QualifierSet_GetNames (funzione)</span><span class="sxs-lookup"><span data-stu-id="bb365-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="bb365-104">Recupera i nomi di tutti i qualificatori o di alcuni qualificatori disponibili dall'oggetto corrente o dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="bb365-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bb365-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb365-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="bb365-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb365-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="bb365-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="bb365-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="bb365-108">[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="bb365-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="bb365-109">[in] Uno dei flag seguenti o valori che specifica i nomi da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bb365-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="bb365-110">Costante</span><span class="sxs-lookup"><span data-stu-id="bb365-110">Constant</span></span>  |<span data-ttu-id="bb365-111">Valore</span><span class="sxs-lookup"><span data-stu-id="bb365-111">Value</span></span>  |<span data-ttu-id="bb365-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb365-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="bb365-113">0</span><span class="sxs-lookup"><span data-stu-id="bb365-113">0</span></span> | <span data-ttu-id="bb365-114">Restituisce i nomi di tutti i qualificatori.</span><span class="sxs-lookup"><span data-stu-id="bb365-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="bb365-115">0x10</span><span class="sxs-lookup"><span data-stu-id="bb365-115">0x10</span></span> | <span data-ttu-id="bb365-116">Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bb365-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="bb365-117">Per una proprietà: restituire solo i qualificatori specifici per la proprietà (inclusi sostituzioni) e non i qualificatori propagate dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="bb365-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="bb365-118">Ad esempio: restituire solo i nomi di qualificatore specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="bb365-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="bb365-119">Per una classe: restituire solo i qualificatori specifico beiong la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="bb365-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="bb365-120">0x20</span><span class="sxs-lookup"><span data-stu-id="bb365-120">0x20</span></span> | <span data-ttu-id="bb365-121">Restituire solo i nomi dei qualificatori propagati da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="bb365-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="bb365-122">Per una proprietà: restituiscono solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli di proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="bb365-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="bb365-123">Ad esempio: restituzione solo tali qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="bb365-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="bb365-124">Per una classe: restituiscono solo i nomi di qualificatore ereditati dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="bb365-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="bb365-125">`pstrNames` [out] Un nuovo `SAFEARRAY` che contiene i nomi richiesti.</span><span class="sxs-lookup"><span data-stu-id="bb365-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="bb365-126">La matrice può contenere 0 elementi.</span><span class="sxs-lookup"><span data-stu-id="bb365-126">The array can have 0 elements.</span></span> <span data-ttu-id="bb365-127">Se si verifica un errore, un nuovo `SAFEARRAY` non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="bb365-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="bb365-128">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bb365-128">Return value</span></span>

<span data-ttu-id="bb365-129">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="bb365-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bb365-130">Costante</span><span class="sxs-lookup"><span data-stu-id="bb365-130">Constant</span></span>  |<span data-ttu-id="bb365-131">Valore</span><span class="sxs-lookup"><span data-stu-id="bb365-131">Value</span></span>  |<span data-ttu-id="bb365-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb365-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bb365-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bb365-133">0x80041008</span></span> | <span data-ttu-id="bb365-134">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="bb365-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bb365-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bb365-135">0x80041006</span></span> | <span data-ttu-id="bb365-136">Memoria insufficiente è disponibile per avviare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bb365-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bb365-137">0</span><span class="sxs-lookup"><span data-stu-id="bb365-137">0</span></span> | <span data-ttu-id="bb365-138">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="bb365-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bb365-139">Note</span><span class="sxs-lookup"><span data-stu-id="bb365-139">Remarks</span></span>

<span data-ttu-id="bb365-140">Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="bb365-140">This function wraps a call to the [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="bb365-141">Dopo aver recuperato i nomi di qualificatore, è possibile accedere in base al nome ogni qualificatore chiamando il [QualifierSet_Get](qualifierset-get.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="bb365-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="bb365-142">Non è un errore di un determinato oggetto di qualificatori di zero, pertanto il numero di stringhe in `pstrNames` restituito può essere 0, anche se la funzione restituisce `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="bb365-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb365-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb365-143">Requirements</span></span>  
 <span data-ttu-id="bb365-144">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb365-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb365-145">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bb365-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bb365-146">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb365-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb365-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb365-147">See also</span></span>  
[<span data-ttu-id="bb365-148">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="bb365-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
