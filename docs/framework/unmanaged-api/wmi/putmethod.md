---
title: PutMethod function (Unmanaged API Reference)
description: La funzione PutMethod crea un metodo.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174914"
---
# <a name="putmethod-function"></a><span data-ttu-id="b6197-103">Funzione PutMethod</span><span class="sxs-lookup"><span data-stu-id="b6197-103">PutMethod function</span></span>
<span data-ttu-id="b6197-104">Crea un metodo.</span><span class="sxs-lookup"><span data-stu-id="b6197-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b6197-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6197-105">Syntax</span></span>  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="b6197-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6197-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b6197-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b6197-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b6197-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="b6197-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="b6197-109">[in] Nome del metodo da creare.</span><span class="sxs-lookup"><span data-stu-id="b6197-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="b6197-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="b6197-110">[in] Reserved.</span></span> <span data-ttu-id="b6197-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="b6197-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="b6197-112">[in] Puntatore a una copia della classe `in` di sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) che contiene i parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="b6197-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="b6197-113">Questo parametro viene `null`ignorato se impostato su .</span><span class="sxs-lookup"><span data-stu-id="b6197-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="b6197-114">[in]  Puntatore a una copia della classe `out` di sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) che contiene i parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="b6197-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="b6197-115">Questo parametro viene `null`ignorato se impostato su .</span><span class="sxs-lookup"><span data-stu-id="b6197-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b6197-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b6197-116">Return value</span></span>

<span data-ttu-id="b6197-117">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="b6197-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b6197-118">Costante</span><span class="sxs-lookup"><span data-stu-id="b6197-118">Constant</span></span>  |<span data-ttu-id="b6197-119">valore</span><span class="sxs-lookup"><span data-stu-id="b6197-119">Value</span></span>  |<span data-ttu-id="b6197-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6197-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b6197-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b6197-121">0x80041008</span></span> | <span data-ttu-id="b6197-122">Uno o più parametri non sono validi.</span><span class="sxs-lookup"><span data-stu-id="b6197-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="b6197-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="b6197-123">0x80041043</span></span> | <span data-ttu-id="b6197-124">Il `[in, out]` parametro del metodo specificato in entrambi gli oggetti *pInSignature* e *pOutSignature* hanno qualificatori diversi.</span><span class="sxs-lookup"><span data-stu-id="b6197-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="b6197-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="b6197-125">0x80041036</span></span> | <span data-ttu-id="b6197-126">In un parametro del metodo manca la specifica del qualificatore **DI ID.**</span><span class="sxs-lookup"><span data-stu-id="b6197-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="b6197-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="b6197-127">0x80041038</span></span> | <span data-ttu-id="b6197-128">La serie di ID assegnata ai parametri del metodo non è consecutiva o non inizia da 0.</span><span class="sxs-lookup"><span data-stu-id="b6197-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="b6197-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="b6197-129">0x80041039</span></span> | <span data-ttu-id="b6197-130">Il valore restituito per un metodo ha un qualificatore **di ID.**</span><span class="sxs-lookup"><span data-stu-id="b6197-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="b6197-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="b6197-131">0x80041034</span></span> | <span data-ttu-id="b6197-132">È stato effettuato un tentativo di riutilizzare un nome di metodo esistente da una classe padre e le firme non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="b6197-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b6197-133">0</span><span class="sxs-lookup"><span data-stu-id="b6197-133">0</span></span> | <span data-ttu-id="b6197-134">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b6197-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b6197-135">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b6197-135">Remarks</span></span>

<span data-ttu-id="b6197-136">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .</span><span class="sxs-lookup"><span data-stu-id="b6197-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="b6197-137">Questa chiamata al metodo `ptr` è supportata solo se è una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="b6197-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="b6197-138">La modifica del metodo non è disponibile dai puntatori [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="b6197-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="b6197-139">Gli utenti non possono creare metodi con nomi che iniziano o terminano con un segno di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="b6197-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="b6197-140">Questa operazione è riservata alle classi e alle proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="b6197-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="b6197-141">Per un metodo, i `in` parametri e `out` vengono descritti come proprietà negli oggetti [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="b6197-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="b6197-142">Un `[in/out]` parametro può essere definito aggiungendo la stessa `pInSignature` proprietà `pOutSignature` a entrambi gli oggetti a cui puntano i parametri e .</span><span class="sxs-lookup"><span data-stu-id="b6197-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="b6197-143">In questo caso, le proprietà condividono lo stesso valore del qualificatore **ID.**</span><span class="sxs-lookup"><span data-stu-id="b6197-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="b6197-144">Ogni proprietà in un oggetto `ReturnValue` di classe [__Parameters](/windows/desktop/WmiSdk/--parameters) diverso da deve avere un qualificatore **ID,** un valore numerico in base zero che identifica l'ordine in cui vengono visualizzati i parametri.</span><span class="sxs-lookup"><span data-stu-id="b6197-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="b6197-145">Due parametri non possono avere lo stesso valore **ID** e nessun valore **ID** può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="b6197-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="b6197-146">Se si verifica `PutMethod` una `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`delle condizioni, la funzione restituisce .</span><span class="sxs-lookup"><span data-stu-id="b6197-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="b6197-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6197-147">Example</span></span>

<span data-ttu-id="b6197-148">Per un esempio, vedere il [metodo IWbemClassObject::PutMethod.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)</span><span class="sxs-lookup"><span data-stu-id="b6197-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6197-149">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6197-149">Requirements</span></span>  
 <span data-ttu-id="b6197-150">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6197-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6197-151">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b6197-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b6197-152">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b6197-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6197-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6197-153">See also</span></span>

- [<span data-ttu-id="b6197-154">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b6197-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
