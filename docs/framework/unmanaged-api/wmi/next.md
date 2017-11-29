---
title: Funzione Next (riferimenti alle API non gestite)
description: "Retireves di funzione successiva la proprietà successiva in un'enumerazione."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Next
helpviewer_keywords: Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c198a9f9507af583f4718c636cd00c9d65a25695
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="next-function"></a><span data-ttu-id="4404a-103">Funzione successiva</span><span class="sxs-lookup"><span data-stu-id="4404a-103">Next function</span></span>
<span data-ttu-id="4404a-104">Recupera la proprietà successiva in un'enumerazione che inizia con una chiamata a [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4404a-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4404a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4404a-105">Syntax</span></span>  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a><span data-ttu-id="4404a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4404a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4404a-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="4404a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4404a-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="4404a-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="4404a-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="4404a-109">[in] Reserved.</span></span> <span data-ttu-id="4404a-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="4404a-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="4404a-111">[out] Un nuovo `BSTR` che contiene il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4404a-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="4404a-112">È possibile impostare questo parametro su `null` se il nome non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4404a-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="4404a-113">[out] Oggetto `VARIANT` riempita con il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4404a-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="4404a-114">È possibile impostare questo parametro su `null` se il valore non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4404a-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="4404a-115">Se la funzione restituisce un codice di errore, il `VARIANT` passato a `pVal` è invariato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="4404a-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="4404a-116">[out] Un puntatore a un `CIMTYPE` variabile (un `LONG` in cui viene inserito il tipo della proprietà).</span><span class="sxs-lookup"><span data-stu-id="4404a-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="4404a-117">Il valore di questa proprietà può essere un `VT_NULL_VARIANT`, nel qual caso è necessario determinare il tipo effettivo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4404a-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="4404a-118">Questo parametro può anche essere `null`.</span><span class="sxs-lookup"><span data-stu-id="4404a-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="4404a-119">[out] `null`, o un valore che riceve le informazioni sull'origine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4404a-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="4404a-120">Vedere la sezione [note] per i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="4404a-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4404a-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4404a-121">Return value</span></span>

<span data-ttu-id="4404a-122">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="4404a-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4404a-123">Costante</span><span class="sxs-lookup"><span data-stu-id="4404a-123">Constant</span></span>  |<span data-ttu-id="4404a-124">Valore</span><span class="sxs-lookup"><span data-stu-id="4404a-124">Value</span></span>  |<span data-ttu-id="4404a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4404a-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="4404a-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="4404a-126">0x80041001</span></span> | <span data-ttu-id="4404a-127">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="4404a-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4404a-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4404a-128">0x80041008</span></span> | <span data-ttu-id="4404a-129">Un parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="4404a-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="4404a-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4404a-130">0x8004101d</span></span> | <span data-ttu-id="4404a-131">Si è verificato alcuna chiamata al [ `BeginEnumeration` ](beginenumeration.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="4404a-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4404a-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4404a-132">0x80041006</span></span> | <span data-ttu-id="4404a-133">Memoria insufficiente è disponibile per avviare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4404a-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="4404a-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="4404a-134">0x80041015</span></span> | <span data-ttu-id="4404a-135">La procedura remota chiamare tra il processo corrente e la gestione di Windows non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="4404a-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4404a-136">0</span><span class="sxs-lookup"><span data-stu-id="4404a-136">0</span></span> | <span data-ttu-id="4404a-137">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="4404a-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="4404a-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="4404a-138">0x40005</span></span> | <span data-ttu-id="4404a-139">Non esistono altre proprietà nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4404a-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="4404a-140">Note</span><span class="sxs-lookup"><span data-stu-id="4404a-140">Remarks</span></span>

<span data-ttu-id="4404a-141">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="4404a-141">This function wraps a call to the [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="4404a-142">Questo metodo restituisce anche le proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="4404a-142">This method also returns system properties.</span></span>

<span data-ttu-id="4404a-143">Se il tipo sottostante della proprietà è un percorso dell'oggetto, una data o ora o un altro tipo speciale, il tipo restituito non contiene informazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="4404a-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="4404a-144">Il chiamante deve esaminare il `CIMTYPE` per la proprietà specificata determinare se la proprietà è un riferimento all'oggetto, una data o ora o un altro tipo speciale.</span><span class="sxs-lookup"><span data-stu-id="4404a-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="4404a-145">Se `plFlavor` non `null`, `LONG` valore riceve le informazioni relative all'origine della proprietà, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4404a-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="4404a-146">Costante</span><span class="sxs-lookup"><span data-stu-id="4404a-146">Constant</span></span>  |<span data-ttu-id="4404a-147">Valore</span><span class="sxs-lookup"><span data-stu-id="4404a-147">Value</span></span>  |<span data-ttu-id="4404a-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4404a-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="4404a-149">0x40</span><span class="sxs-lookup"><span data-stu-id="4404a-149">0x40</span></span> | <span data-ttu-id="4404a-150">La proprietà è una proprietà di sistema standard.</span><span class="sxs-lookup"><span data-stu-id="4404a-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="4404a-151">0x20</span><span class="sxs-lookup"><span data-stu-id="4404a-151">0x20</span></span> | <span data-ttu-id="4404a-152">Per una classe: la proprietà viene ereditata dalla classe padre.</span><span class="sxs-lookup"><span data-stu-id="4404a-152">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="4404a-153">Per un'istanza: la proprietà, mentre ereditata dalla classe padre, non è stata modificata dall'istanza.</span><span class="sxs-lookup"><span data-stu-id="4404a-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="4404a-154">0</span><span class="sxs-lookup"><span data-stu-id="4404a-154">0</span></span> | <span data-ttu-id="4404a-155">Per una classe: la proprietà appartiene alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="4404a-155">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="4404a-156">Per un'istanza: la proprietà viene modificata tramite l'istanza. ovvero, è stato fornito un valore o un qualificatore è stato aggiunto o modificato.</span><span class="sxs-lookup"><span data-stu-id="4404a-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4404a-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4404a-157">Requirements</span></span>  
 <span data-ttu-id="4404a-158">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4404a-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4404a-159">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4404a-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4404a-160">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4404a-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4404a-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4404a-161">See also</span></span>  
[<span data-ttu-id="4404a-162">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="4404a-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
