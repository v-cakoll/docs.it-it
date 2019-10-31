---
title: Funzione Put (riferimenti alle API non gestite)
description: La funzione put assegna un nuovo valore a una proprietà denominata.
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
ms.openlocfilehash: f1bb8aa09a269e3b8fd23f393d63a275d308a77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127409"
---
# <a name="put-function"></a><span data-ttu-id="8e193-103">Funzione put</span><span class="sxs-lookup"><span data-stu-id="8e193-103">Put function</span></span>

<span data-ttu-id="8e193-104">Imposta una proprietà denominata su un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="8e193-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8e193-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e193-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="8e193-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e193-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="8e193-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="8e193-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="8e193-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="8e193-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="8e193-109">in Nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e193-109">[in] The name of the property.</span></span> <span data-ttu-id="8e193-110">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="8e193-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="8e193-111">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="8e193-111">[in] Reserved.</span></span> <span data-ttu-id="8e193-112">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="8e193-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="8e193-113">in Puntatore a un `VARIANT` valido che diventa il nuovo valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e193-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="8e193-114">Se `pVal` è `null` o punta a un `VARIANT` di tipo `VT_NULL`, la proprietà viene impostata su `null`.</span><span class="sxs-lookup"><span data-stu-id="8e193-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="8e193-115">in Tipo di `VARIANT` a cui punta `pVal`.</span><span class="sxs-lookup"><span data-stu-id="8e193-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="8e193-116">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="8e193-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="8e193-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8e193-117">Return value</span></span>

<span data-ttu-id="8e193-118">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="8e193-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8e193-119">Costante</span><span class="sxs-lookup"><span data-stu-id="8e193-119">Constant</span></span>  |<span data-ttu-id="8e193-120">Value</span><span class="sxs-lookup"><span data-stu-id="8e193-120">Value</span></span>  |<span data-ttu-id="8e193-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e193-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="8e193-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8e193-122">0x80041001</span></span> | <span data-ttu-id="8e193-123">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="8e193-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8e193-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8e193-124">0x80041008</span></span> | <span data-ttu-id="8e193-125">Uno o più parametri non sono validi.</span><span class="sxs-lookup"><span data-stu-id="8e193-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="8e193-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="8e193-126">0x8004102a</span></span> | <span data-ttu-id="8e193-127">Il tipo di proprietà non è riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8e193-127">The property type is not recognized.</span></span> <span data-ttu-id="8e193-128">Questo valore viene restituito quando si creano istanze della classe se la classe esiste già.</span><span class="sxs-lookup"><span data-stu-id="8e193-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8e193-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8e193-129">0x80041006</span></span> | <span data-ttu-id="8e193-130">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8e193-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="8e193-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="8e193-131">0x80041005</span></span> | <span data-ttu-id="8e193-132">Per instances: indica che `pVal` punta a una `VARIANT` di un tipo non corretto per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e193-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="8e193-133">Per le definizioni di classe: la proprietà esiste già nella classe padre e il nuovo tipo COM è diverso dal vecchio tipo COM.</span><span class="sxs-lookup"><span data-stu-id="8e193-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8e193-134">0</span><span class="sxs-lookup"><span data-stu-id="8e193-134">0</span></span> | <span data-ttu-id="8e193-135">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8e193-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8e193-136">Note</span><span class="sxs-lookup"><span data-stu-id="8e193-136">Remarks</span></span>

<span data-ttu-id="8e193-137">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .</span><span class="sxs-lookup"><span data-stu-id="8e193-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="8e193-138">Questa funzione sovrascrive sempre il valore della proprietà corrente con uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="8e193-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="8e193-139">Se [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a una definizione di classe, `Put` crea o aggiorna il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e193-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="8e193-140">Quando [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a un'istanza CIM, `Put` aggiorna solo il valore della proprietà. `Put` non è possibile creare un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e193-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="8e193-141">La proprietà di sistema `__CLASS` è scrivibile solo durante la creazione della classe, quando potrebbe non essere lasciata vuota.</span><span class="sxs-lookup"><span data-stu-id="8e193-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="8e193-142">Tutte le altre proprietà di sistema sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8e193-142">All other system properties are read-only.</span></span>

<span data-ttu-id="8e193-143">Un utente non può creare proprietà con nomi che iniziano o terminano con un carattere di sottolineatura ("_").</span><span class="sxs-lookup"><span data-stu-id="8e193-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="8e193-144">Questa operazione è riservata per le classi e le proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="8e193-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="8e193-145">Se la proprietà impostata dalla funzione `Put` esiste nella classe padre, il valore predefinito della proprietà viene modificato a meno che il tipo di proprietà non corrisponda al tipo di classe padre.</span><span class="sxs-lookup"><span data-stu-id="8e193-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="8e193-146">Se la proprietà non esiste e non è un tipo non corrispondente, viene creata la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e193-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="8e193-147">Usare il parametro `vtType` solo quando si creano nuove proprietà in una definizione di classe CIM e `pVal` è `null` o punta a un `VARIANT` di tipo `VT_NULL`.</span><span class="sxs-lookup"><span data-stu-id="8e193-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="8e193-148">In questo caso, il parametro `vType` specifica il tipo CIM della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e193-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="8e193-149">In tutti gli altri casi, `vtType` deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="8e193-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="8e193-150">`vtType` deve anche essere 0 se l'oggetto sottostante è un'istanza (anche se `Val` è `null`) perché il tipo della proprietà è fisso e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="8e193-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="8e193-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e193-151">Example</span></span>

<span data-ttu-id="8e193-152">Per un esempio, vedere il metodo [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .</span><span class="sxs-lookup"><span data-stu-id="8e193-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e193-153">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e193-153">Requirements</span></span>

<span data-ttu-id="8e193-154">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e193-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8e193-155">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="8e193-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="8e193-156">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e193-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8e193-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e193-157">See also</span></span>

- [<span data-ttu-id="8e193-158">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="8e193-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
