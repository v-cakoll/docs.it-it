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
ms.openlocfilehash: 402d56b44c2b6f53f901e35c6d7b965811a40344
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636594"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="ebfaf-103">QualifierSet_GetNames (funzione)</span><span class="sxs-lookup"><span data-stu-id="ebfaf-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="ebfaf-104">Recupera i nomi di tutti i qualificatori o di determinati qualificatori disponibili dall'oggetto corrente o la proprietà.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ebfaf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebfaf-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="ebfaf-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ebfaf-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ebfaf-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ebfaf-108">[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="ebfaf-109">[in] Uno dei seguenti flag o valori che specifica i nomi da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="ebfaf-110">Costante</span><span class="sxs-lookup"><span data-stu-id="ebfaf-110">Constant</span></span>  |<span data-ttu-id="ebfaf-111">Value</span><span class="sxs-lookup"><span data-stu-id="ebfaf-111">Value</span></span>  |<span data-ttu-id="ebfaf-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ebfaf-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="ebfaf-113">0</span><span class="sxs-lookup"><span data-stu-id="ebfaf-113">0</span></span> | <span data-ttu-id="ebfaf-114">Restituire i nomi di tutti i qualificatori.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="ebfaf-115">0x10</span><span class="sxs-lookup"><span data-stu-id="ebfaf-115">0x10</span></span> | <span data-ttu-id="ebfaf-116">Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="ebfaf-117">Per una proprietà: Restituire solo gli e i qualificatori specifici per la proprietà (incluse le sostituzioni), non tali propagata dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="ebfaf-118">Per un'istanza: Restituire solo i nomi di qualificatore specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="ebfaf-119">Per una classe: Restituire solo i qualificatori specifici per la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="ebfaf-120">0x20</span><span class="sxs-lookup"><span data-stu-id="ebfaf-120">0x20</span></span> | <span data-ttu-id="ebfaf-121">Restituisce solo i nomi dei qualificatori propagati da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="ebfaf-122">Per una proprietà: Restituisce solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli dalla proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="ebfaf-123">Per un'istanza: Restituzione solo tali qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="ebfaf-124">Per una classe: Restituisce solo i nomi di qualificatore ereditati dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="ebfaf-125">[out] Un nuovo `SAFEARRAY` che contiene i nomi richiesti.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="ebfaf-126">La matrice può contenere 0 elementi.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-126">The array can have 0 elements.</span></span> <span data-ttu-id="ebfaf-127">Se si verifica un errore, un nuovo `SAFEARRAY` non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="ebfaf-128">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ebfaf-128">Return value</span></span>

<span data-ttu-id="ebfaf-129">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ebfaf-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ebfaf-130">Costante</span><span class="sxs-lookup"><span data-stu-id="ebfaf-130">Constant</span></span>  |<span data-ttu-id="ebfaf-131">Value</span><span class="sxs-lookup"><span data-stu-id="ebfaf-131">Value</span></span>  |<span data-ttu-id="ebfaf-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ebfaf-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ebfaf-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ebfaf-133">0x80041008</span></span> | <span data-ttu-id="ebfaf-134">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ebfaf-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ebfaf-135">0x80041006</span></span> | <span data-ttu-id="ebfaf-136">Memoria insufficiente è disponibile per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ebfaf-137">0</span><span class="sxs-lookup"><span data-stu-id="ebfaf-137">0</span></span> | <span data-ttu-id="ebfaf-138">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ebfaf-139">Note</span><span class="sxs-lookup"><span data-stu-id="ebfaf-139">Remarks</span></span>

<span data-ttu-id="ebfaf-140">Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ebfaf-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="ebfaf-141">Dopo aver recuperato i nomi di qualificatore, è possibile accedere in base al nome ogni qualificatore chiamando il [QualifierSet_Get](qualifierset-get.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="ebfaf-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="ebfaf-142">Non è un errore per un determinato oggetto di avere zero qualificatori, pertanto il numero di stringhe nelle `pstrNames` nell'output restituito può essere 0, anche se la funzione restituisce `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="ebfaf-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebfaf-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebfaf-143">Requirements</span></span>

<span data-ttu-id="ebfaf-144">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebfaf-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ebfaf-145">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ebfaf-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ebfaf-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ebfaf-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ebfaf-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebfaf-147">See also</span></span>

- [<span data-ttu-id="ebfaf-148">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ebfaf-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
