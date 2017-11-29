---
title: Funzione GetObjectText (riferimenti alle API non gestite)
description: La funzione GetObjectText restituisce a seguito del rendering testuale di un oggetto in sintassi MOF.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetObjectText
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetObjectText
helpviewer_keywords: GetObjectText function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 27e25a7ab7131f5b1c995c9367de6fe5a6fae592
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getobjecttext-function"></a><span data-ttu-id="77924-103">Funzione GetObjectText</span><span class="sxs-lookup"><span data-stu-id="77924-103">GetObjectText function</span></span>
<span data-ttu-id="77924-104">Restituisce un rendering testuale dell'oggetto nella sintassi del formato MOF (Managed Object).</span><span class="sxs-lookup"><span data-stu-id="77924-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="77924-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77924-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="77924-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="77924-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="77924-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="77924-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="77924-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="77924-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="77924-109">[in] In genere 0.</span><span class="sxs-lookup"><span data-stu-id="77924-109">[in] Normally 0.</span></span> <span data-ttu-id="77924-110">Se `WBEM_FLAG_NO_FLAVORS` (o 0x1) viene specificato, qualificatori sono inclusi senza informazioni di propagazione o la versione.</span><span class="sxs-lookup"><span data-stu-id="77924-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="77924-111">[out] Un puntatore a un `null` in ingresso.</span><span class="sxs-lookup"><span data-stu-id="77924-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="77924-112">Restituzione, appena allocato `BSTR` che contiene un rendering di sintassi MOF dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="77924-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="77924-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="77924-113">Return value</span></span>

<span data-ttu-id="77924-114">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="77924-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="77924-115">Costante</span><span class="sxs-lookup"><span data-stu-id="77924-115">Constant</span></span>  |<span data-ttu-id="77924-116">Valore</span><span class="sxs-lookup"><span data-stu-id="77924-116">Value</span></span>  |<span data-ttu-id="77924-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77924-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="77924-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="77924-118">0x80041001</span></span> | <span data-ttu-id="77924-119">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="77924-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="77924-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="77924-120">0x80041008</span></span> | <span data-ttu-id="77924-121">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="77924-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="77924-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="77924-122">0x80041006</span></span> | <span data-ttu-id="77924-123">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="77924-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="77924-124">0</span><span class="sxs-lookup"><span data-stu-id="77924-124">0</span></span> | <span data-ttu-id="77924-125">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="77924-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="77924-126">Note</span><span class="sxs-lookup"><span data-stu-id="77924-126">Remarks</span></span>

<span data-ttu-id="77924-127">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="77924-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="77924-128">Il testo MOF restituito non contiene tutte le informazioni sull'oggetto, ma solo le informazioni sufficienti per il file MOF essere in grado di ricreare l'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="77924-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="77924-129">Ad esempio, non sono incluse propagati qualificatori o una proprietà della classe padre.</span><span class="sxs-lookup"><span data-stu-id="77924-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="77924-130">Per ricostruire il testo dei parametri di un metodo, viene utilizzato l'algoritmo seguente:</span><span class="sxs-lookup"><span data-stu-id="77924-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="77924-131">I parametri sono resequenced nell'ordine dei valori dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="77924-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="77924-132">I parametri vengono specificati come `[in]` e `[out]` vengono combinati in un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="77924-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="77924-133">`pstrObjectText`deve essere un puntatore a un `null` quando viene chiamata la funzione non deve puntare a una stringa valida prima della chiamata al metodo, in quanto il puntatore non verrà deallocato.</span><span class="sxs-lookup"><span data-stu-id="77924-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="77924-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77924-134">Requirements</span></span>  
<span data-ttu-id="77924-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77924-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77924-136">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="77924-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="77924-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="77924-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77924-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77924-138">See also</span></span>  
[<span data-ttu-id="77924-139">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="77924-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
