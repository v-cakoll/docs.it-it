---
title: Funzione PutMethod (riferimenti alle API non gestite)
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
ms.openlocfilehash: 1d409507de593cf198fe87340eece6820eaefc63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127339"
---
# <a name="putmethod-function"></a><span data-ttu-id="b8565-103">PutMethod (funzione)</span><span class="sxs-lookup"><span data-stu-id="b8565-103">PutMethod function</span></span>
<span data-ttu-id="b8565-104">Crea un metodo.</span><span class="sxs-lookup"><span data-stu-id="b8565-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b8565-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8565-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="b8565-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8565-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b8565-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b8565-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b8565-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="b8565-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="b8565-109">in Nome del metodo da creare.</span><span class="sxs-lookup"><span data-stu-id="b8565-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="b8565-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="b8565-110">[in] Reserved.</span></span> <span data-ttu-id="b8565-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="b8565-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="b8565-112">in Puntatore a una copia della classe di [sistema __Parameters](/windows/desktop/WmiSdk/--parameters) che contiene i parametri di `in` per il metodo.</span><span class="sxs-lookup"><span data-stu-id="b8565-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="b8565-113">Questo parametro viene ignorato se impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="b8565-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="b8565-114">in  Puntatore a una copia della classe di [sistema __Parameters](/windows/desktop/WmiSdk/--parameters) che contiene i parametri di `out` per il metodo.</span><span class="sxs-lookup"><span data-stu-id="b8565-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="b8565-115">Questo parametro viene ignorato se impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="b8565-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b8565-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b8565-116">Return value</span></span>

<span data-ttu-id="b8565-117">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="b8565-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b8565-118">Costante</span><span class="sxs-lookup"><span data-stu-id="b8565-118">Constant</span></span>  |<span data-ttu-id="b8565-119">Value</span><span class="sxs-lookup"><span data-stu-id="b8565-119">Value</span></span>  |<span data-ttu-id="b8565-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8565-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b8565-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b8565-121">0x80041008</span></span> | <span data-ttu-id="b8565-122">Uno o più parametri non sono validi.</span><span class="sxs-lookup"><span data-stu-id="b8565-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="b8565-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="b8565-123">0x80041043</span></span> | <span data-ttu-id="b8565-124">Il `[in, out]` parametro del metodo specificato negli oggetti *pInSignature* e *pOutSignature* ha qualificatori diversi.</span><span class="sxs-lookup"><span data-stu-id="b8565-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="b8565-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="b8565-125">0x80041036</span></span> | <span data-ttu-id="b8565-126">Nel parametro di un metodo manca la specifica del qualificatore **ID** .</span><span class="sxs-lookup"><span data-stu-id="b8565-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="b8565-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="b8565-127">0x80041038</span></span> | <span data-ttu-id="b8565-128">La serie di ID assegnata ai parametri del metodo non è consecutiva o non inizia da 0.</span><span class="sxs-lookup"><span data-stu-id="b8565-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="b8565-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="b8565-129">0x80041039</span></span> | <span data-ttu-id="b8565-130">Il valore restituito per un metodo ha un qualificatore **ID** .</span><span class="sxs-lookup"><span data-stu-id="b8565-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="b8565-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="b8565-131">0x80041034</span></span> | <span data-ttu-id="b8565-132">È stato effettuato un tentativo di riutilizzare un nome di metodo esistente da una classe padre e le firme non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="b8565-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b8565-133">0</span><span class="sxs-lookup"><span data-stu-id="b8565-133">0</span></span> | <span data-ttu-id="b8565-134">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b8565-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b8565-135">Note</span><span class="sxs-lookup"><span data-stu-id="b8565-135">Remarks</span></span>

<span data-ttu-id="b8565-136">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .</span><span class="sxs-lookup"><span data-stu-id="b8565-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="b8565-137">Questa chiamata al metodo è supportata solo se `ptr` è una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="b8565-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="b8565-138">La manipolazione dei metodi non è disponibile dai puntatori [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="b8565-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="b8565-139">Gli utenti non possono creare metodi con nomi che iniziano o terminano con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="b8565-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="b8565-140">Questa operazione è riservata per le classi e le proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="b8565-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="b8565-141">Per un metodo, i parametri `in` e `out` sono descritti come proprietà negli oggetti [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="b8565-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="b8565-142">Per definire un parametro di `[in/out]`, è possibile aggiungere la stessa proprietà a entrambi gli oggetti a cui puntano i parametri `pInSignature` e `pOutSignature`.</span><span class="sxs-lookup"><span data-stu-id="b8565-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="b8565-143">In questo caso, le proprietà condividono lo stesso valore di qualificatore **ID** .</span><span class="sxs-lookup"><span data-stu-id="b8565-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="b8565-144">Ogni proprietà in un oggetto della classe [__Parameters](/windows/desktop/WmiSdk/--parameters) diverso da `ReturnValue` deve avere un qualificatore **ID** , un valore numerico in base zero che identifica l'ordine in cui vengono visualizzati i parametri.</span><span class="sxs-lookup"><span data-stu-id="b8565-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="b8565-145">Due parametri non possono avere lo stesso valore **ID** e nessun valore **ID** può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="b8565-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="b8565-146">Se si verifica una delle due condizioni, la funzione `PutMethod` restituisce `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="b8565-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="b8565-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8565-147">Example</span></span>

<span data-ttu-id="b8565-148">Per un esempio, vedere il metodo [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .</span><span class="sxs-lookup"><span data-stu-id="b8565-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8565-149">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8565-149">Requirements</span></span>  
 <span data-ttu-id="b8565-150">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8565-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8565-151">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="b8565-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b8565-152">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b8565-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8565-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8565-153">See also</span></span>

- [<span data-ttu-id="b8565-154">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b8565-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
