---
title: Funzione Next (riferimenti alle API non gestite)
description: Retireves di funzione successiva la proprietà successiva in un'enumerazione.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c6e39c1bc4c2860e400e2708e588416eb5769bd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971884"
---
# <a name="next-function"></a><span data-ttu-id="b227e-103">Funzione successiva</span><span class="sxs-lookup"><span data-stu-id="b227e-103">Next function</span></span>
<span data-ttu-id="b227e-104">Recupera la proprietà successiva in un'enumerazione che inizia con una chiamata a [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b227e-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b227e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b227e-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="b227e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b227e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b227e-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b227e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b227e-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="b227e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="b227e-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="b227e-109">[in] Reserved.</span></span> <span data-ttu-id="b227e-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="b227e-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="b227e-111">[out] Un nuovo `BSTR` che contiene il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b227e-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="b227e-112">È possibile impostare questo parametro su `null` se il nome non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b227e-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="b227e-113">[out] Oggetto `VARIANT` riempita con il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b227e-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="b227e-114">È possibile impostare questo parametro su `null` se il valore non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b227e-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="b227e-115">Se la funzione restituisce un codice di errore, il `VARIANT` passato a `pVal` è invariata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="b227e-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="b227e-116">[out] Un puntatore a un `CIMTYPE` variabile (un `LONG` in cui viene inserito il tipo della proprietà).</span><span class="sxs-lookup"><span data-stu-id="b227e-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="b227e-117">Il valore di questa proprietà può essere un `VT_NULL_VARIANT`, nel qual caso è necessario determinare il tipo effettivo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b227e-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="b227e-118">Questo parametro può anche essere `null`.</span><span class="sxs-lookup"><span data-stu-id="b227e-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="b227e-119">[out] `null`, o un valore che riceve informazioni sull'origine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b227e-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="b227e-120">Vedere la sezione [note] per i valori possibili.</span><span class="sxs-lookup"><span data-stu-id="b227e-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="b227e-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b227e-121">Return value</span></span>

<span data-ttu-id="b227e-122">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="b227e-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b227e-123">Costante</span><span class="sxs-lookup"><span data-stu-id="b227e-123">Constant</span></span>  |<span data-ttu-id="b227e-124">Valore</span><span class="sxs-lookup"><span data-stu-id="b227e-124">Value</span></span>  |<span data-ttu-id="b227e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b227e-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="b227e-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b227e-126">0x80041001</span></span> | <span data-ttu-id="b227e-127">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="b227e-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b227e-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b227e-128">0x80041008</span></span> | <span data-ttu-id="b227e-129">Un parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="b227e-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="b227e-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="b227e-130">0x8004101d</span></span> | <span data-ttu-id="b227e-131">Si è verificato alcun chiamata per il [ `BeginEnumeration` ](beginenumeration.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="b227e-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b227e-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b227e-132">0x80041006</span></span> | <span data-ttu-id="b227e-133">Memoria insufficiente è disponibile per iniziare una nuova enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b227e-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="b227e-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="b227e-134">0x80041015</span></span> | <span data-ttu-id="b227e-135">La procedura remota chiamare sono corrispondenti del processo corrente e la gestione di Windows non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b227e-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b227e-136">0</span><span class="sxs-lookup"><span data-stu-id="b227e-136">0</span></span> | <span data-ttu-id="b227e-137">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b227e-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="b227e-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="b227e-138">0x40005</span></span> | <span data-ttu-id="b227e-139">Non esistono altre proprietà dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b227e-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b227e-140">Note</span><span class="sxs-lookup"><span data-stu-id="b227e-140">Remarks</span></span>

<span data-ttu-id="b227e-141">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b227e-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="b227e-142">Questo metodo restituisce anche le proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="b227e-142">This method also returns system properties.</span></span>

<span data-ttu-id="b227e-143">Se il tipo sottostante della proprietà è un percorso dell'oggetto, una data o ora o un altro tipo speciale, il tipo restituito non contiene informazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="b227e-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="b227e-144">Il chiamante deve esaminare la `CIMTYPE` per la proprietà specificata determinare se la proprietà è un riferimento all'oggetto, una data o ora o un altro tipo speciale.</span><span class="sxs-lookup"><span data-stu-id="b227e-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="b227e-145">Se `plFlavor` non è `null`, il `LONG` valore riceve informazioni relative all'origine della proprietà, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b227e-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="b227e-146">Costante</span><span class="sxs-lookup"><span data-stu-id="b227e-146">Constant</span></span>  |<span data-ttu-id="b227e-147">Value</span><span class="sxs-lookup"><span data-stu-id="b227e-147">Value</span></span>  |<span data-ttu-id="b227e-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b227e-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="b227e-149">0x40</span><span class="sxs-lookup"><span data-stu-id="b227e-149">0x40</span></span> | <span data-ttu-id="b227e-150">La proprietà è una proprietà di sistema standard.</span><span class="sxs-lookup"><span data-stu-id="b227e-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="b227e-151">0x20</span><span class="sxs-lookup"><span data-stu-id="b227e-151">0x20</span></span> | <span data-ttu-id="b227e-152">Per una classe: La proprietà viene ereditata dalla classe padre.</span><span class="sxs-lookup"><span data-stu-id="b227e-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="b227e-153">Per un'istanza: La proprietà, mentre ereditata dalla classe padre, non modificata dall'istanza.</span><span class="sxs-lookup"><span data-stu-id="b227e-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="b227e-154">0</span><span class="sxs-lookup"><span data-stu-id="b227e-154">0</span></span> | <span data-ttu-id="b227e-155">Per una classe: La proprietà appartiene alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="b227e-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="b227e-156">Per un'istanza: La proprietà viene modificata tramite l'istanza. vale a dire, è stato fornito un valore o un qualificatore è stato aggiunto o modificato.</span><span class="sxs-lookup"><span data-stu-id="b227e-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="b227e-157">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b227e-157">Requirements</span></span>  
 <span data-ttu-id="b227e-158">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b227e-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b227e-159">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b227e-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b227e-160">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b227e-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b227e-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b227e-161">See also</span></span>
- [<span data-ttu-id="b227e-162">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b227e-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
