---
title: Funzione GetObjectText (riferimenti alle API non gestite)
description: La funzione GetObjectText restituisce a seguito del rendering testuale di un oggetto in sintassi MOF.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b47dc73bb9da71b0c8593aa5758179327d7572d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getobjecttext-function"></a><span data-ttu-id="99215-103">Funzione GetObjectText</span><span class="sxs-lookup"><span data-stu-id="99215-103">GetObjectText function</span></span>
<span data-ttu-id="99215-104">Restituisce un rendering testuale dell'oggetto nella sintassi del formato MOF (Managed Object).</span><span class="sxs-lookup"><span data-stu-id="99215-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="99215-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99215-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="99215-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="99215-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="99215-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="99215-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="99215-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="99215-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="99215-109">[in] In genere 0.</span><span class="sxs-lookup"><span data-stu-id="99215-109">[in] Normally 0.</span></span> <span data-ttu-id="99215-110">Se `WBEM_FLAG_NO_FLAVORS` (o 0x1) viene specificato, qualificatori sono inclusi senza informazioni di propagazione o la versione.</span><span class="sxs-lookup"><span data-stu-id="99215-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="99215-111">[out] Un puntatore a un `null` in ingresso.</span><span class="sxs-lookup"><span data-stu-id="99215-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="99215-112">Restituzione, appena allocato `BSTR` che contiene un rendering di sintassi MOF dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="99215-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="99215-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="99215-113">Return value</span></span>

<span data-ttu-id="99215-114">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="99215-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="99215-115">Costante</span><span class="sxs-lookup"><span data-stu-id="99215-115">Constant</span></span>  |<span data-ttu-id="99215-116">Valore</span><span class="sxs-lookup"><span data-stu-id="99215-116">Value</span></span>  |<span data-ttu-id="99215-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99215-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="99215-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="99215-118">0x80041001</span></span> | <span data-ttu-id="99215-119">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="99215-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="99215-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="99215-120">0x80041008</span></span> | <span data-ttu-id="99215-121">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="99215-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="99215-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="99215-122">0x80041006</span></span> | <span data-ttu-id="99215-123">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="99215-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="99215-124">0</span><span class="sxs-lookup"><span data-stu-id="99215-124">0</span></span> | <span data-ttu-id="99215-125">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="99215-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="99215-126">Note</span><span class="sxs-lookup"><span data-stu-id="99215-126">Remarks</span></span>

<span data-ttu-id="99215-127">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="99215-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="99215-128">Il testo MOF restituito non contiene tutte le informazioni sull'oggetto, ma solo le informazioni sufficienti per il file MOF essere in grado di ricreare l'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="99215-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="99215-129">Ad esempio, non sono incluse propagati qualificatori o una proprietà della classe padre.</span><span class="sxs-lookup"><span data-stu-id="99215-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="99215-130">Per ricostruire il testo dei parametri di un metodo, viene utilizzato l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="99215-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="99215-131">I parametri sono resequenced nell'ordine dei valori dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="99215-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="99215-132">I parametri vengono specificati come `[in]` e `[out]` vengono combinati in un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="99215-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="99215-133">`pstrObjectText`deve essere un puntatore a un `null` quando viene chiamata la funzione non deve puntare a una stringa valida prima della chiamata al metodo, in quanto il puntatore non verrà deallocato.</span><span class="sxs-lookup"><span data-stu-id="99215-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="99215-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99215-134">Requirements</span></span>  
<span data-ttu-id="99215-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99215-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99215-136">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="99215-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="99215-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="99215-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99215-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99215-138">See also</span></span>  
[<span data-ttu-id="99215-139">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="99215-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
