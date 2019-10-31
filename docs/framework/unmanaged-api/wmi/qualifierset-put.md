---
title: Funzione QualifierSet_Put (riferimenti alle API non gestite)
description: La funzione QualifierSet_Put scrive il qualificatore denominato e il relativo valore.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a35025c6d16455a51b7b22d822ba77337ddd894a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120239"
---
# <a name="qualifierset_put-function"></a><span data-ttu-id="345ec-103">QualifierSet_Put (funzione)</span><span class="sxs-lookup"><span data-stu-id="345ec-103">QualifierSet_Put function</span></span>

<span data-ttu-id="345ec-104">Scrive il qualificatore e il valore denominati.</span><span class="sxs-lookup"><span data-stu-id="345ec-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="345ec-105">Il nuovo qualificatore sovrascrive il valore precedente con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="345ec-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="345ec-106">Se il qualificatore non esiste, viene creato.</span><span class="sxs-lookup"><span data-stu-id="345ec-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="345ec-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="345ec-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="345ec-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="345ec-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="345ec-109">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="345ec-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="345ec-110">in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="345ec-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="345ec-111">in Nome del qualificatore da scrivere.</span><span class="sxs-lookup"><span data-stu-id="345ec-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="345ec-112">in Puntatore a un `VARIANT` valido che contiene il qualificatore da scrivere.</span><span class="sxs-lookup"><span data-stu-id="345ec-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="345ec-113">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="345ec-114">in Una delle costanti seguenti che definisce le versioni del qualificatore desiderate per questo qualificatore.</span><span class="sxs-lookup"><span data-stu-id="345ec-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="345ec-115">Il valore predefinito è `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="345ec-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="345ec-116">Costante</span><span class="sxs-lookup"><span data-stu-id="345ec-116">Constant</span></span>  |<span data-ttu-id="345ec-117">Value</span><span class="sxs-lookup"><span data-stu-id="345ec-117">Value</span></span>  |<span data-ttu-id="345ec-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="345ec-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="345ec-119">0</span><span class="sxs-lookup"><span data-stu-id="345ec-119">0</span></span> | <span data-ttu-id="345ec-120">Il qualificatore può essere sottoposto a override in una classe o un'istanza derivata.</span><span class="sxs-lookup"><span data-stu-id="345ec-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="345ec-121">**Si tratta del valore predefinito.**</span><span class="sxs-lookup"><span data-stu-id="345ec-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="345ec-122">1</span><span class="sxs-lookup"><span data-stu-id="345ec-122">1</span></span> | <span data-ttu-id="345ec-123">Il qualificatore viene propagato alle istanze.</span><span class="sxs-lookup"><span data-stu-id="345ec-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="345ec-124">2</span><span class="sxs-lookup"><span data-stu-id="345ec-124">2</span></span> | <span data-ttu-id="345ec-125">Il qualificatore viene propagato alle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="345ec-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="345ec-126">0x10</span><span class="sxs-lookup"><span data-stu-id="345ec-126">0x10</span></span> | <span data-ttu-id="345ec-127">Il qualificatore non può essere sottoposto a override in una classe o in un'istanza derivata.</span><span class="sxs-lookup"><span data-stu-id="345ec-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="345ec-128">0x80</span><span class="sxs-lookup"><span data-stu-id="345ec-128">0x80</span></span> | <span data-ttu-id="345ec-129">Il qualificatore è localizzato.</span><span class="sxs-lookup"><span data-stu-id="345ec-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="345ec-130">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="345ec-130">Return value</span></span>

<span data-ttu-id="345ec-131">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="345ec-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="345ec-132">Costante</span><span class="sxs-lookup"><span data-stu-id="345ec-132">Constant</span></span>  |<span data-ttu-id="345ec-133">Value</span><span class="sxs-lookup"><span data-stu-id="345ec-133">Value</span></span>  |<span data-ttu-id="345ec-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="345ec-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="345ec-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="345ec-135">0x8004101f</span></span> | <span data-ttu-id="345ec-136">Si è verificato un tentativo non valido di specificare il qualificatore di **chiave** su una proprietà che non può essere una chiave.</span><span class="sxs-lookup"><span data-stu-id="345ec-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="345ec-137">Le chiavi sono specificate nella definizione della classe per un oggetto e non possono essere modificate per ogni singola istanza.</span><span class="sxs-lookup"><span data-stu-id="345ec-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="345ec-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="345ec-138">0x80041008</span></span> | <span data-ttu-id="345ec-139">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="345ec-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="345ec-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="345ec-140">0x80041029</span></span> | <span data-ttu-id="345ec-141">Il parametro `pVal` non è di un tipo di qualificatore valido.</span><span class="sxs-lookup"><span data-stu-id="345ec-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="345ec-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="345ec-142">0x8004101a</span></span> | <span data-ttu-id="345ec-143">Non è possibile chiamare il metodo `QualifierSet_Put` sul qualificatore perché l'oggetto proprietario non consente le sostituzioni.</span><span class="sxs-lookup"><span data-stu-id="345ec-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="345ec-144">0</span><span class="sxs-lookup"><span data-stu-id="345ec-144">0</span></span> | <span data-ttu-id="345ec-145">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="345ec-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="345ec-146">Note</span><span class="sxs-lookup"><span data-stu-id="345ec-146">Remarks</span></span>

<span data-ttu-id="345ec-147">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) .</span><span class="sxs-lookup"><span data-stu-id="345ec-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="345ec-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="345ec-148">Requirements</span></span>

<span data-ttu-id="345ec-149">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="345ec-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="345ec-150">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="345ec-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="345ec-151">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="345ec-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="345ec-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="345ec-152">See also</span></span>

- [<span data-ttu-id="345ec-153">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="345ec-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
