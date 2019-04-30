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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bc65b0181a7c0ab7877273b3747ece91544f99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049258"
---
# <a name="putmethod-function"></a><span data-ttu-id="8ab5a-103">PutMethod (funzione)</span><span class="sxs-lookup"><span data-stu-id="8ab5a-103">PutMethod function</span></span>
<span data-ttu-id="8ab5a-104">Crea un metodo.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8ab5a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ab5a-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="8ab5a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ab5a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8ab5a-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8ab5a-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="8ab5a-109">[in] Il nome del metodo da creare.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="8ab5a-110">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-110">[in] Reserved.</span></span> <span data-ttu-id="8ab5a-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="8ab5a-112">[in] Un puntatore a una copia del [classe di sistema Parameters](/windows/desktop/WmiSdk/--parameters) che contiene il `in` parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="8ab5a-113">Questo parametro viene ignorato se impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="8ab5a-114">[in]  Un puntatore a una copia del [classe di sistema Parameters](/windows/desktop/WmiSdk/--parameters) che contiene il `out` parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="8ab5a-115">Questo parametro viene ignorato se impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8ab5a-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ab5a-116">Return value</span></span>

<span data-ttu-id="8ab5a-117">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="8ab5a-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8ab5a-118">Costante</span><span class="sxs-lookup"><span data-stu-id="8ab5a-118">Constant</span></span>  |<span data-ttu-id="8ab5a-119">Value</span><span class="sxs-lookup"><span data-stu-id="8ab5a-119">Value</span></span>  |<span data-ttu-id="8ab5a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ab5a-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8ab5a-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8ab5a-121">0x80041008</span></span> | <span data-ttu-id="8ab5a-122">Uno o più parametri non vengono.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="8ab5a-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="8ab5a-123">0x80041043</span></span> | <span data-ttu-id="8ab5a-124">Il `[in, out]` parametro del metodo specificato in entrambe le *pInSignature* e *pOutSignature* gli oggetti hanno qualificatori diversi.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="8ab5a-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="8ab5a-125">0x80041036</span></span> | <span data-ttu-id="8ab5a-126">Un parametro del metodo manca la specifica del **ID** qualificatore.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="8ab5a-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="8ab5a-127">0x80041038</span></span> | <span data-ttu-id="8ab5a-128">La serie di ID viene assegnata ai parametri del metodo non consecutiva o non iniziano da 0.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="8ab5a-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="8ab5a-129">0x80041039</span></span> | <span data-ttu-id="8ab5a-130">Il valore restituito per un metodo ha un **ID** qualificatore.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="8ab5a-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="8ab5a-131">0x80041034</span></span> | <span data-ttu-id="8ab5a-132">Si è verificato un tentativo di riusare un nome di metodo esistente da una classe padre e le firme non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8ab5a-133">0</span><span class="sxs-lookup"><span data-stu-id="8ab5a-133">0</span></span> | <span data-ttu-id="8ab5a-134">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="8ab5a-135">Note</span><span class="sxs-lookup"><span data-stu-id="8ab5a-135">Remarks</span></span>

<span data-ttu-id="8ab5a-136">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="8ab5a-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="8ab5a-137">Questa chiamata al metodo è supportata solo se `ptr` è una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="8ab5a-138">Manipolazione di metodo non è disponibile dal [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatori che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="8ab5a-139">Gli utenti non è possibile creare metodi con nomi che iniziano o terminano con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="8ab5a-140">Questo è riservato per le proprietà e classi di sistema.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="8ab5a-141">Per un metodo, il `in` e `out` sono descritti i parametri come proprietà nella [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) oggetti.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="8ab5a-142">Un' `[in/out]` parametro può essere definito aggiungendo la stessa proprietà per entrambi gli oggetti a cui punta il `pInSignature` e `pOutSignature` parametri.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="8ab5a-143">In questo caso, le proprietà condividono lo stesso **ID** valore del qualificatore.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="8ab5a-144">Ogni proprietà in un [Parameters](/windows/desktop/WmiSdk/--parameters) classe oggetto diverso da `ReturnValue` deve avere un' **ID** qualificatore, un valore numerico in base zero che identifica l'ordine in cui vengono visualizzati i parametri.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="8ab5a-145">Nessuna due parametri possono avere lo stesso **ID** valore e nessun **ID** valore può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="8ab5a-146">Se si verifica una delle due condizioni, il `PutMethod` funzione restituisce `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="8ab5a-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="8ab5a-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ab5a-147">Example</span></span>

<span data-ttu-id="8ab5a-148">Per un esempio, vedere la [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="8ab5a-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8ab5a-149">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ab5a-149">Requirements</span></span>  
 <span data-ttu-id="8ab5a-150">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ab5a-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ab5a-151">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8ab5a-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8ab5a-152">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8ab5a-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab5a-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ab5a-153">See also</span></span>

- [<span data-ttu-id="8ab5a-154">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="8ab5a-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
