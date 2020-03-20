---
title: Funzione GetObjectText (riferimenti alle API non gestite)
description: La funzione GetObjectText restituisce un rendering testuale di un oggetto nella sintassi MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176786"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="09296-103">Funzione GetObjectText</span><span class="sxs-lookup"><span data-stu-id="09296-103">GetObjectText function</span></span>
<span data-ttu-id="09296-104">Restituisce un rendering testuale dell'oggetto nella sintassi MOF (Managed Object Format).</span><span class="sxs-lookup"><span data-stu-id="09296-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="09296-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09296-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="09296-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="09296-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="09296-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="09296-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="09296-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="09296-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="09296-109">[in] Normalmente 0.</span><span class="sxs-lookup"><span data-stu-id="09296-109">[in] Normally 0.</span></span> <span data-ttu-id="09296-110">Se `WBEM_FLAG_NO_FLAVORS` viene specificato (o 0x1), i qualificatori vengono inclusi senza informazioni di propagazione o sapore.</span><span class="sxs-lookup"><span data-stu-id="09296-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="09296-111">`pstrObjectText`[fuori] Puntatore a `null` un'immissione in on.</span><span class="sxs-lookup"><span data-stu-id="09296-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="09296-112">Al ritorno, un `BSTR` nuovo allocato che contiene un rendering della sintassi MOF dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="09296-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="09296-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09296-113">Return value</span></span>

<span data-ttu-id="09296-114">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="09296-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="09296-115">Costante</span><span class="sxs-lookup"><span data-stu-id="09296-115">Constant</span></span>  |<span data-ttu-id="09296-116">valore</span><span class="sxs-lookup"><span data-stu-id="09296-116">Value</span></span>  |<span data-ttu-id="09296-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09296-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="09296-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="09296-118">0x80041001</span></span> | <span data-ttu-id="09296-119">C'è stato un fallimento generale.</span><span class="sxs-lookup"><span data-stu-id="09296-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="09296-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="09296-120">0x80041008</span></span> | <span data-ttu-id="09296-121">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="09296-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="09296-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="09296-122">0x80041006</span></span> | <span data-ttu-id="09296-123">Memoria insufficiente per completare l’operazione.</span><span class="sxs-lookup"><span data-stu-id="09296-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="09296-124">0</span><span class="sxs-lookup"><span data-stu-id="09296-124">0</span></span> | <span data-ttu-id="09296-125">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="09296-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="09296-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="09296-126">Remarks</span></span>

<span data-ttu-id="09296-127">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .</span><span class="sxs-lookup"><span data-stu-id="09296-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="09296-128">Il testo MOF restituito non contiene tutte le informazioni sull'oggetto, ma solo informazioni sufficienti per consentire al compilatore MOF di ricreare l'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="09296-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="09296-129">Ad esempio, non sono inclusi qualificatori propagati o proprietà della classe padre.</span><span class="sxs-lookup"><span data-stu-id="09296-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="09296-130">Il seguente algoritmo viene utilizzato per ricostruire il testo dei parametri di un metodo:</span><span class="sxs-lookup"><span data-stu-id="09296-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="09296-131">I parametri vengono risequenziati nell'ordine dei relativi valori di identificazione.</span><span class="sxs-lookup"><span data-stu-id="09296-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="09296-132">I parametri specificati `[in]` `[out]` come e vengono combinati in un unico parametro.</span><span class="sxs-lookup"><span data-stu-id="09296-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="09296-133">`pstrObjectText`deve essere un `null` puntatore a un quando viene chiamata la funzione; non deve puntare a una stringa valida prima della chiamata al metodo, perché il puntatore non verrà deallocato.</span><span class="sxs-lookup"><span data-stu-id="09296-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="09296-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09296-134">Requirements</span></span>  
<span data-ttu-id="09296-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09296-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09296-136">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="09296-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="09296-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="09296-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09296-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09296-138">See also</span></span>

- [<span data-ttu-id="09296-139">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="09296-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
