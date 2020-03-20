---
title: Get function (Unmanaged API Reference)
description: La funzione Get recupera il valore della proprietà specificato.
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
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174979"
---
# <a name="get-function"></a><span data-ttu-id="2e990-103">Funzione Get</span><span class="sxs-lookup"><span data-stu-id="2e990-103">Get function</span></span>

<span data-ttu-id="2e990-104">Recupera il valore della proprietà specificata, se esistente.</span><span class="sxs-lookup"><span data-stu-id="2e990-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="2e990-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e990-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="2e990-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e990-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="2e990-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="2e990-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="2e990-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="2e990-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="2e990-109">[in] Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2e990-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="2e990-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="2e990-110">[in] Reserved.</span></span> <span data-ttu-id="2e990-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="2e990-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="2e990-112">[fuori] Se la funzione restituisce correttamente, contiene il valore della `wszName` proprietà.</span><span class="sxs-lookup"><span data-stu-id="2e990-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="2e990-113">All'argomento `pval` vengono assegnati il tipo e il valore corretti per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="2e990-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="2e990-114">[fuori] Se la funzione restituisce correttamente, contiene una [costante di tipo CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) che indica il tipo di proprietà.</span><span class="sxs-lookup"><span data-stu-id="2e990-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="2e990-115">Il suo valore `null`può anche essere .</span><span class="sxs-lookup"><span data-stu-id="2e990-115">Its value can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="2e990-116">[fuori] Se la funzione restituisce correttamente, riceve informazioni sull'origine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2e990-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="2e990-117">Il valore `null`può essere , o una delle seguenti costanti WBEM_FLAVOR_TYPE definite nel file di intestazione *WbemCli.h:*</span><span class="sxs-lookup"><span data-stu-id="2e990-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span>

|<span data-ttu-id="2e990-118">Costante</span><span class="sxs-lookup"><span data-stu-id="2e990-118">Constant</span></span>  |<span data-ttu-id="2e990-119">valore</span><span class="sxs-lookup"><span data-stu-id="2e990-119">Value</span></span>  |<span data-ttu-id="2e990-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e990-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="2e990-121">0x40</span><span class="sxs-lookup"><span data-stu-id="2e990-121">0x40</span></span> | <span data-ttu-id="2e990-122">La proprietà è una proprietà di sistema standard.</span><span class="sxs-lookup"><span data-stu-id="2e990-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="2e990-123">0x20</span><span class="sxs-lookup"><span data-stu-id="2e990-123">0x20</span></span> | <span data-ttu-id="2e990-124">Per una classe: la proprietà viene ereditata dalla classe padre.</span><span class="sxs-lookup"><span data-stu-id="2e990-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="2e990-125">Per un'istanza: la proprietà, sebbene ereditata dalla classe padre, non è stata modificata dall'istanza.</span><span class="sxs-lookup"><span data-stu-id="2e990-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="2e990-126">0</span><span class="sxs-lookup"><span data-stu-id="2e990-126">0</span></span> | <span data-ttu-id="2e990-127">Per una classe: la proprietà appartiene alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="2e990-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="2e990-128">Per un'istanza: la proprietà viene modificata dall'istanza; ovvero è stato fornito un valore oppure è stato aggiunto o modificato un qualificatore.</span><span class="sxs-lookup"><span data-stu-id="2e990-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="2e990-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2e990-129">Return value</span></span>

<span data-ttu-id="2e990-130">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="2e990-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2e990-131">Costante</span><span class="sxs-lookup"><span data-stu-id="2e990-131">Constant</span></span>  |<span data-ttu-id="2e990-132">valore</span><span class="sxs-lookup"><span data-stu-id="2e990-132">Value</span></span>  |<span data-ttu-id="2e990-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e990-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="2e990-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="2e990-134">0x80041001</span></span> | <span data-ttu-id="2e990-135">C'è stato un fallimento generale.</span><span class="sxs-lookup"><span data-stu-id="2e990-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2e990-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2e990-136">0x80041008</span></span> | <span data-ttu-id="2e990-137">Uno o più parametri non sono validi.</span><span class="sxs-lookup"><span data-stu-id="2e990-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="2e990-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="2e990-138">0x80041002</span></span> | <span data-ttu-id="2e990-139">La proprietà specificata non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="2e990-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2e990-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2e990-140">0x80041006</span></span> | <span data-ttu-id="2e990-141">Memoria insufficiente per completare l’operazione.</span><span class="sxs-lookup"><span data-stu-id="2e990-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2e990-142">0</span><span class="sxs-lookup"><span data-stu-id="2e990-142">0</span></span> | <span data-ttu-id="2e990-143">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2e990-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="2e990-144">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2e990-144">Remarks</span></span>

<span data-ttu-id="2e990-145">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .</span><span class="sxs-lookup"><span data-stu-id="2e990-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="2e990-146">La `Get` funzione può anche restituire proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="2e990-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="2e990-147">All'argomento `pVal` vengono assegnati il tipo e il valore corretti per il qualificatore e la funzione [COM VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)</span><span class="sxs-lookup"><span data-stu-id="2e990-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="2e990-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e990-148">Requirements</span></span>

 <span data-ttu-id="2e990-149">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e990-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="2e990-150">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2e990-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="2e990-151">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2e990-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2e990-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e990-152">See also</span></span>

- [<span data-ttu-id="2e990-153">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="2e990-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
