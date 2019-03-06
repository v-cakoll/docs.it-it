---
title: Funzione QualifierSet_BeginEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_BeginEnumeration Reimposta l'enumeratore dei qualificatori di un oggetto.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663434d3e3d44dc0c406e71592651493bd8f8dc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375415"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="3f780-103">QualifierSet_BeginEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="3f780-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="3f780-104">Reimposta un enumeratore dei qualificatori di un oggetto all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3f780-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3f780-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f780-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="3f780-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f780-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="3f780-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="3f780-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="3f780-108">[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.</span><span class="sxs-lookup"><span data-stu-id="3f780-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="3f780-109">[in] Una combinazione bit per bit del flag o i valori descritti nel [osservazioni](#remarks) sezione che specifica i qualificatori da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3f780-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="3f780-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f780-110">Return value</span></span>

<span data-ttu-id="3f780-111">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="3f780-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3f780-112">Costante</span><span class="sxs-lookup"><span data-stu-id="3f780-112">Constant</span></span>  |<span data-ttu-id="3f780-113">Value</span><span class="sxs-lookup"><span data-stu-id="3f780-113">Value</span></span>  |<span data-ttu-id="3f780-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f780-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3f780-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3f780-115">0x80041008</span></span> | <span data-ttu-id="3f780-116">Il parametro `lFlags` non è valido.</span><span class="sxs-lookup"><span data-stu-id="3f780-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="3f780-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="3f780-117">0x8004101d</span></span> | <span data-ttu-id="3f780-118">Una seconda chiamata a `QualifierSet_BeginEnumeration` è stata eseguita senza una chiamata corrispondente a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3f780-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3f780-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3f780-119">0x80041006</span></span> | <span data-ttu-id="3f780-120">Memoria insufficiente è disponibile per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3f780-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3f780-121">0</span><span class="sxs-lookup"><span data-stu-id="3f780-121">0</span></span> | <span data-ttu-id="3f780-122">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3f780-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="3f780-123">Note</span><span class="sxs-lookup"><span data-stu-id="3f780-123">Remarks</span></span>

<span data-ttu-id="3f780-124">Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3f780-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="3f780-125">Per enumerare tutti i qualificatori su un oggetto, questo metodo deve essere chiamato prima della prima chiamata a [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="3f780-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="3f780-126">L'ordine in cui vengono enumerati i qualificatori è garantito a essere invariante per un'enumerazione specificata.</span><span class="sxs-lookup"><span data-stu-id="3f780-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="3f780-127">I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="3f780-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="3f780-128">Costante</span><span class="sxs-lookup"><span data-stu-id="3f780-128">Constant</span></span>  |<span data-ttu-id="3f780-129">Value</span><span class="sxs-lookup"><span data-stu-id="3f780-129">Value</span></span>  |<span data-ttu-id="3f780-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f780-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="3f780-131">0</span><span class="sxs-lookup"><span data-stu-id="3f780-131">0</span></span> | <span data-ttu-id="3f780-132">Restituire i nomi di tutti i qualificatori.</span><span class="sxs-lookup"><span data-stu-id="3f780-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="3f780-133">0x10</span><span class="sxs-lookup"><span data-stu-id="3f780-133">0x10</span></span> | <span data-ttu-id="3f780-134">Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3f780-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="3f780-135">Per una proprietà: Restituire solo gli e i qualificatori specifici per la proprietà (incluse le sostituzioni), non tali propagata dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="3f780-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="3f780-136">Per un'istanza: Restituire solo i nomi di qualificatore specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="3f780-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="3f780-137">Per una classe: Restituire solo i qualificatori specifici per la classe derivata.</span><span class="sxs-lookup"><span data-stu-id="3f780-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="3f780-138">0x20</span><span class="sxs-lookup"><span data-stu-id="3f780-138">0x20</span></span> | <span data-ttu-id="3f780-139">Restituisce solo i nomi dei qualificatori propagati da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="3f780-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="3f780-140">Per una proprietà: Restituisce solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli dalla proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="3f780-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="3f780-141">Per un'istanza: Restituzione solo tali qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="3f780-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="3f780-142">Per una classe: Restituisce solo i nomi di qualificatore ereditati dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="3f780-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="3f780-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f780-143">Requirements</span></span>

<span data-ttu-id="3f780-144">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f780-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3f780-145">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3f780-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3f780-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3f780-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3f780-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f780-147">See also</span></span>

- [<span data-ttu-id="3f780-148">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="3f780-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)