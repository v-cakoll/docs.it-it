---
title: Funzione QualifierSet_BeginEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_BeginEnumeration Reimposta un enumeratore dei qualificatori di un oggetto.
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
ms.openlocfilehash: 79edbd876fc9992f088b9adb159e005c735a72cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127320"
---
# <a name="qualifierset_beginenumeration-function"></a><span data-ttu-id="11542-103">QualifierSet_BeginEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="11542-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="11542-104">Reimposta un enumeratore dei qualificatori di un oggetto all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="11542-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="11542-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11542-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="11542-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="11542-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="11542-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="11542-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="11542-108">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="11542-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="11542-109">in Combinazione bit per bit dei flag o valori descritti nella sezione [osservazioni](#remarks) che specifica i qualificatori da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="11542-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="11542-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="11542-110">Return value</span></span>

<span data-ttu-id="11542-111">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="11542-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="11542-112">Costante</span><span class="sxs-lookup"><span data-stu-id="11542-112">Constant</span></span>  |<span data-ttu-id="11542-113">Value</span><span class="sxs-lookup"><span data-stu-id="11542-113">Value</span></span>  |<span data-ttu-id="11542-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11542-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="11542-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="11542-115">0x80041008</span></span> | <span data-ttu-id="11542-116">Il parametro `lFlags` non è valido.</span><span class="sxs-lookup"><span data-stu-id="11542-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="11542-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="11542-117">0x8004101d</span></span> | <span data-ttu-id="11542-118">Una seconda chiamata a `QualifierSet_BeginEnumeration` è stata effettuata senza una chiamata corrispondente a [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="11542-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="11542-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="11542-119">0x80041006</span></span> | <span data-ttu-id="11542-120">La memoria disponibile non è sufficiente per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="11542-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="11542-121">0</span><span class="sxs-lookup"><span data-stu-id="11542-121">0</span></span> | <span data-ttu-id="11542-122">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="11542-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="11542-123">Note</span><span class="sxs-lookup"><span data-stu-id="11542-123">Remarks</span></span>

<span data-ttu-id="11542-124">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) .</span><span class="sxs-lookup"><span data-stu-id="11542-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="11542-125">Per enumerare tutti i qualificatori in un oggetto, questo metodo deve essere chiamato prima della prima chiamata a [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="11542-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="11542-126">L'ordine in cui vengono enumerati i qualificatori è sicuramente invariante per una determinata enumerazione.</span><span class="sxs-lookup"><span data-stu-id="11542-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="11542-127">I flag che possono essere passati come `lEnumFlags` argomento vengono definiti nel file di intestazione *WbemCli. h* oppure possono essere definiti come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="11542-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="11542-128">Costante</span><span class="sxs-lookup"><span data-stu-id="11542-128">Constant</span></span>  |<span data-ttu-id="11542-129">Value</span><span class="sxs-lookup"><span data-stu-id="11542-129">Value</span></span>  |<span data-ttu-id="11542-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11542-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="11542-131">0</span><span class="sxs-lookup"><span data-stu-id="11542-131">0</span></span> | <span data-ttu-id="11542-132">Restituisce i nomi di tutti i qualificatori.</span><span class="sxs-lookup"><span data-stu-id="11542-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="11542-133">0x10</span><span class="sxs-lookup"><span data-stu-id="11542-133">0x10</span></span> | <span data-ttu-id="11542-134">Restituisce solo i nomi dei qualificatori specifici della proprietà o dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="11542-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="11542-135">Per una proprietà: restituire solo i qualificatori specifici della proprietà (incluse le sostituzioni) e non i qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="11542-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="11542-136">Per un'istanza: restituire solo nomi di qualificatori specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="11542-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="11542-137">Per una classe: restituire solo i qualificatori specifici della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="11542-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="11542-138">0x20</span><span class="sxs-lookup"><span data-stu-id="11542-138">0x20</span></span> | <span data-ttu-id="11542-139">Restituisce solo i nomi dei qualificatori propagati da un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="11542-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="11542-140">Per una proprietà: restituire solo i qualificatori propagati a questa proprietà dalla definizione della classe e non da quelli della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="11542-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="11542-141">Per un'istanza: restituire solo i qualificatori propagati dalla definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="11542-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="11542-142">Per una classe: restituire solo i nomi dei qualificatori ereditati dalle classi padre.</span><span class="sxs-lookup"><span data-stu-id="11542-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="11542-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11542-143">Requirements</span></span>

<span data-ttu-id="11542-144">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11542-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="11542-145">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="11542-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="11542-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="11542-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="11542-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11542-147">See also</span></span>

- [<span data-ttu-id="11542-148">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="11542-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
