---
title: Funzione QualifierSet_GetNames (riferimenti alle API non gestite)
description: La funzione QualifierSet_GetNames recupera i nomi dei qualificatori da un oggetto o da una proprietà.
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
ms.openlocfilehash: bd0a67987dd8ffa825114726d066249aed40cf05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141699"
---
# <a name="qualifierset_getnames-function"></a><span data-ttu-id="37955-103">QualifierSet_GetNames (funzione)</span><span class="sxs-lookup"><span data-stu-id="37955-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="37955-104">Recupera i nomi di tutti i qualificatori o di determinati qualificatori disponibili dall'oggetto o dalla proprietà corrente.</span><span class="sxs-lookup"><span data-stu-id="37955-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="37955-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37955-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="37955-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="37955-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="37955-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="37955-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="37955-108">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="37955-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="37955-109">in Uno dei seguenti flag o valori che specifica i nomi da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="37955-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="37955-110">Costante</span><span class="sxs-lookup"><span data-stu-id="37955-110">Constant</span></span>  |<span data-ttu-id="37955-111">Value</span><span class="sxs-lookup"><span data-stu-id="37955-111">Value</span></span>  |<span data-ttu-id="37955-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37955-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="37955-113">0</span><span class="sxs-lookup"><span data-stu-id="37955-113">0</span></span> | <span data-ttu-id="37955-114">Restituisce i nomi di tutti i qualificatori.</span><span class="sxs-lookup"><span data-stu-id="37955-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="37955-115">0x10</span><span class="sxs-lookup"><span data-stu-id="37955-115">0x10</span></span> | <span data-ttu-id="37955-116">Restituisce solo i nomi dei qualificatori specifici della proprietà o dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="37955-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="37955-117">Per una proprietà: restituire solo i qualificatori specifici della proprietà (incluse le sostituzioni) e non i qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="37955-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="37955-118">Per un'istanza: restituire solo nomi di qualificatori specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="37955-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="37955-119">Per una classe: restituire solo i qualificatori specifici della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="37955-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="37955-120">0x20</span><span class="sxs-lookup"><span data-stu-id="37955-120">0x20</span></span> | <span data-ttu-id="37955-121">Restituisce solo i nomi dei qualificatori propagati da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="37955-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="37955-122">Per una proprietà: restituire solo i qualificatori propagati a questa proprietà dalla definizione della classe e non da quelli della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="37955-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="37955-123">Per un'istanza: restituire solo i qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="37955-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="37955-124">Per una classe: restituire solo i nomi dei qualificatori ereditati dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="37955-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="37955-125">out Nuovo `SAFEARRAY` contenente i nomi richiesti.</span><span class="sxs-lookup"><span data-stu-id="37955-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="37955-126">La matrice può avere 0 elementi.</span><span class="sxs-lookup"><span data-stu-id="37955-126">The array can have 0 elements.</span></span> <span data-ttu-id="37955-127">Se si verifica un errore, non viene restituito un nuovo `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="37955-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="37955-128">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="37955-128">Return value</span></span>

<span data-ttu-id="37955-129">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="37955-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="37955-130">Costante</span><span class="sxs-lookup"><span data-stu-id="37955-130">Constant</span></span>  |<span data-ttu-id="37955-131">Value</span><span class="sxs-lookup"><span data-stu-id="37955-131">Value</span></span>  |<span data-ttu-id="37955-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37955-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="37955-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="37955-133">0x80041008</span></span> | <span data-ttu-id="37955-134">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="37955-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="37955-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="37955-135">0x80041006</span></span> | <span data-ttu-id="37955-136">La memoria disponibile non è sufficiente per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="37955-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="37955-137">0</span><span class="sxs-lookup"><span data-stu-id="37955-137">0</span></span> | <span data-ttu-id="37955-138">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="37955-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="37955-139">Note</span><span class="sxs-lookup"><span data-stu-id="37955-139">Remarks</span></span>

<span data-ttu-id="37955-140">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) .</span><span class="sxs-lookup"><span data-stu-id="37955-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="37955-141">Una volta recuperati i nomi dei qualificatori, è possibile accedere a ogni qualificatore in base al nome chiamando la funzione [QualifierSet_Get](qualifierset-get.md) .</span><span class="sxs-lookup"><span data-stu-id="37955-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="37955-142">Non si tratta di un errore per un dato oggetto con qualificatori zero, quindi il numero di stringhe nel `pstrNames` restituito può essere 0, anche se la funzione restituisce `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="37955-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="37955-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37955-143">Requirements</span></span>

<span data-ttu-id="37955-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37955-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="37955-145">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="37955-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="37955-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="37955-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="37955-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37955-147">See also</span></span>

- [<span data-ttu-id="37955-148">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="37955-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
