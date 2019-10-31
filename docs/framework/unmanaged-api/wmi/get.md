---
title: Funzione Get (riferimenti alle API non gestite)
description: La funzione Get recupera il valore della proprietà specificata.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 60f29b91000fd3c07efea88dcc319eb283a4af78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120331"
---
# <a name="get-function"></a><span data-ttu-id="c72b0-103">Funzione Get</span><span class="sxs-lookup"><span data-stu-id="c72b0-103">Get function</span></span>

<span data-ttu-id="c72b0-104">Recupera il valore della proprietà specificata, se esistente.</span><span class="sxs-lookup"><span data-stu-id="c72b0-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c72b0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c72b0-105">Syntax</span></span>

```cpp
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```

## <a name="parameters"></a><span data-ttu-id="c72b0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c72b0-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c72b0-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c72b0-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c72b0-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="c72b0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="c72b0-109">in Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c72b0-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="c72b0-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="c72b0-110">[in] Reserved.</span></span> <span data-ttu-id="c72b0-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="c72b0-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="c72b0-112">out Se la funzione restituisce correttamente, contiene il valore della proprietà `wszName`.</span><span class="sxs-lookup"><span data-stu-id="c72b0-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="c72b0-113">All'argomento `pval` vengono assegnati il tipo e il valore corretti per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="c72b0-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="c72b0-114">out Se la funzione restituisce correttamente, contiene una [costante di tipo CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) che indica il tipo di proprietà.</span><span class="sxs-lookup"><span data-stu-id="c72b0-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="c72b0-115">Il valore può anche essere `null`.</span><span class="sxs-lookup"><span data-stu-id="c72b0-115">Its value can also be `null`.</span></span> 

`plFlavor`\
<span data-ttu-id="c72b0-116">out Se la funzione restituisce correttamente, riceve informazioni sull'origine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c72b0-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="c72b0-117">Il valore può essere `null`o una delle seguenti costanti WBEM_FLAVOR_TYPE definite nel file di intestazione *WbemCli. h* :</span><span class="sxs-lookup"><span data-stu-id="c72b0-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="c72b0-118">Costante</span><span class="sxs-lookup"><span data-stu-id="c72b0-118">Constant</span></span>  |<span data-ttu-id="c72b0-119">Value</span><span class="sxs-lookup"><span data-stu-id="c72b0-119">Value</span></span>  |<span data-ttu-id="c72b0-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c72b0-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="c72b0-121">0x40</span><span class="sxs-lookup"><span data-stu-id="c72b0-121">0x40</span></span> | <span data-ttu-id="c72b0-122">La proprietà è una proprietà di sistema standard.</span><span class="sxs-lookup"><span data-stu-id="c72b0-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="c72b0-123">0x20</span><span class="sxs-lookup"><span data-stu-id="c72b0-123">0x20</span></span> | <span data-ttu-id="c72b0-124">Per una classe: la proprietà viene ereditata dalla classe padre.</span><span class="sxs-lookup"><span data-stu-id="c72b0-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="c72b0-125">Per un'istanza: la proprietà, mentre ereditata dalla classe padre, non è stata modificata dall'istanza di.</span><span class="sxs-lookup"><span data-stu-id="c72b0-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="c72b0-126">0</span><span class="sxs-lookup"><span data-stu-id="c72b0-126">0</span></span> | <span data-ttu-id="c72b0-127">Per una classe: la proprietà appartiene alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="c72b0-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="c72b0-128">Per un'istanza: la proprietà viene modificata dall'istanza di. ovvero è stato specificato un valore oppure è stato aggiunto o modificato un qualificatore.</span><span class="sxs-lookup"><span data-stu-id="c72b0-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="c72b0-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c72b0-129">Return value</span></span>

<span data-ttu-id="c72b0-130">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="c72b0-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c72b0-131">Costante</span><span class="sxs-lookup"><span data-stu-id="c72b0-131">Constant</span></span>  |<span data-ttu-id="c72b0-132">Value</span><span class="sxs-lookup"><span data-stu-id="c72b0-132">Value</span></span>  |<span data-ttu-id="c72b0-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c72b0-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="c72b0-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c72b0-134">0x80041001</span></span> | <span data-ttu-id="c72b0-135">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="c72b0-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c72b0-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c72b0-136">0x80041008</span></span> | <span data-ttu-id="c72b0-137">Uno o più parametri non sono validi.</span><span class="sxs-lookup"><span data-stu-id="c72b0-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c72b0-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c72b0-138">0x80041002</span></span> | <span data-ttu-id="c72b0-139">Impossibile trovare la proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="c72b0-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c72b0-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c72b0-140">0x80041006</span></span> | <span data-ttu-id="c72b0-141">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="c72b0-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c72b0-142">0</span><span class="sxs-lookup"><span data-stu-id="c72b0-142">0</span></span> | <span data-ttu-id="c72b0-143">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c72b0-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="c72b0-144">Note</span><span class="sxs-lookup"><span data-stu-id="c72b0-144">Remarks</span></span>

<span data-ttu-id="c72b0-145">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .</span><span class="sxs-lookup"><span data-stu-id="c72b0-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="c72b0-146">La funzione `Get` può inoltre restituire proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="c72b0-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="c72b0-147">All'argomento `pVal` vengono assegnati il tipo e il valore corretti per il qualificatore e la funzione COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)</span><span class="sxs-lookup"><span data-stu-id="c72b0-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="c72b0-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c72b0-148">Requirements</span></span>

 <span data-ttu-id="c72b0-149">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c72b0-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="c72b0-150">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="c72b0-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="c72b0-151">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c72b0-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c72b0-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c72b0-152">See also</span></span>

- [<span data-ttu-id="c72b0-153">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c72b0-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
