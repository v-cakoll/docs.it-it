---
title: Funzione Put (riferimenti alle API non gestite)
description: La funzione Put assegna un nuovo valore per una proprietà denominata.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02c8ab3aa7fcc603b76fb4b1d09e7e73d04494be
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369194"
---
# <a name="put-function"></a><span data-ttu-id="d04b1-103">Funzione Put</span><span class="sxs-lookup"><span data-stu-id="d04b1-103">Put function</span></span>

<span data-ttu-id="d04b1-104">Imposta una proprietà denominata su un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="d04b1-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d04b1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d04b1-105">Syntax</span></span>

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a><span data-ttu-id="d04b1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d04b1-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d04b1-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="d04b1-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d04b1-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="d04b1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="d04b1-109">[in] Il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d04b1-109">[in] The name of the property.</span></span> <span data-ttu-id="d04b1-110">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="d04b1-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="d04b1-111">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="d04b1-111">[in] Reserved.</span></span> <span data-ttu-id="d04b1-112">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="d04b1-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="d04b1-113">[in] Un puntatore a un valore valido `VARIANT` che diventa il nuovo valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d04b1-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="d04b1-114">Se `pVal` viene `null` o punta a un `VARIANT` typu `VT_NULL`, la proprietà è impostata su `null`.</span><span class="sxs-lookup"><span data-stu-id="d04b1-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="d04b1-115">[in] Il tipo della `VARIANT` a cui punta `pVal`.</span><span class="sxs-lookup"><span data-stu-id="d04b1-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="d04b1-116">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d04b1-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="d04b1-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d04b1-117">Return value</span></span>

<span data-ttu-id="d04b1-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="d04b1-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d04b1-119">Costante</span><span class="sxs-lookup"><span data-stu-id="d04b1-119">Constant</span></span>  |<span data-ttu-id="d04b1-120">Valore</span><span class="sxs-lookup"><span data-stu-id="d04b1-120">Value</span></span>  |<span data-ttu-id="d04b1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d04b1-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="d04b1-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d04b1-122">0x80041001</span></span> | <span data-ttu-id="d04b1-123">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="d04b1-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d04b1-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d04b1-124">0x80041008</span></span> | <span data-ttu-id="d04b1-125">Uno o più parametri non vengono.</span><span class="sxs-lookup"><span data-stu-id="d04b1-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="d04b1-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="d04b1-126">0x8004102a</span></span> | <span data-ttu-id="d04b1-127">Il tipo di proprietà non è riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d04b1-127">The property type is not recognized.</span></span> <span data-ttu-id="d04b1-128">Questo valore viene restituito durante la creazione di istanze della classe se la classe esiste già.</span><span class="sxs-lookup"><span data-stu-id="d04b1-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d04b1-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d04b1-129">0x80041006</span></span> | <span data-ttu-id="d04b1-130">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d04b1-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="d04b1-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="d04b1-131">0x80041005</span></span> | <span data-ttu-id="d04b1-132">Per le istanze: Indica che `pVal` punta a un `VARIANT` di un tipo non corretto per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d04b1-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="d04b1-133">Per le definizioni di classe: La proprietà esiste già nella classe padre e il nuovo tipo COM è diverso dal vecchio tipo COM.</span><span class="sxs-lookup"><span data-stu-id="d04b1-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d04b1-134">0</span><span class="sxs-lookup"><span data-stu-id="d04b1-134">0</span></span> | <span data-ttu-id="d04b1-135">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d04b1-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d04b1-136">Note</span><span class="sxs-lookup"><span data-stu-id="d04b1-136">Remarks</span></span>

<span data-ttu-id="d04b1-137">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d04b1-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="d04b1-138">Questa funzione sovrascrive sempre il valore della proprietà corrente con uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="d04b1-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="d04b1-139">Se il [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a una definizione di classe, `Put` crea o aggiorna il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d04b1-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="d04b1-140">Quando [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a un'istanza di CIM `Put` aggiorna il valore della proprietà di sola lettura. `Put` non è possibile creare un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d04b1-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="d04b1-141">Il `__CLASS` proprietà di sistema è solo scrivibile durante la creazione della classe, quando si potrebbe non essere lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="d04b1-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="d04b1-142">Tutte le altre proprietà di sistema sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="d04b1-142">All other system properties are read-only.</span></span>

<span data-ttu-id="d04b1-143">Un utente non è possibile creare proprietà con nomi che iniziano o terminano con un carattere di sottolineatura ("_").</span><span class="sxs-lookup"><span data-stu-id="d04b1-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="d04b1-144">Questo è riservato per le proprietà e classi di sistema.</span><span class="sxs-lookup"><span data-stu-id="d04b1-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="d04b1-145">Se la proprietà impostata `Put` funzione presente nella classe padre, il valore predefinito della proprietà viene modificato, a meno che il tipo di proprietà non corrisponde al tipo di classe padre.</span><span class="sxs-lookup"><span data-stu-id="d04b1-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="d04b1-146">Se la proprietà non esiste e non è un tipo non corrispondente, la proprietà viene creata.</span><span class="sxs-lookup"><span data-stu-id="d04b1-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="d04b1-147">Usare la `vtType` parametro solo durante la creazione di nuove proprietà in una definizione di classe CIM e `pVal` viene `null` o punta a un `VARIANT` di tipo `VT_NULL`.</span><span class="sxs-lookup"><span data-stu-id="d04b1-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="d04b1-148">In questo caso, il `vType` parametro specifica il tipo CIM della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d04b1-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="d04b1-149">In tutti gli altri casi, `vtType` deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="d04b1-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="d04b1-150">`vtType` deve anche essere 0 se l'oggetto sottostante è un'istanza (anche se `Val` è `null`) perché il tipo della proprietà è fisso e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="d04b1-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="d04b1-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="d04b1-151">Example</span></span>

<span data-ttu-id="d04b1-152">Per un esempio, vedere la [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d04b1-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d04b1-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d04b1-153">Requirements</span></span>

<span data-ttu-id="d04b1-154">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d04b1-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d04b1-155">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d04b1-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d04b1-156">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d04b1-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d04b1-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d04b1-157">See also</span></span>

- [<span data-ttu-id="d04b1-158">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d04b1-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)