---
title: Get (funzione) (riferimenti alle API non gestite)
description: La funzione Get recupera il valore della proprietà specificato.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f837a526879f80177bc9979e1d7671edfcd8d4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460148"
---
# <a name="get-function"></a><span data-ttu-id="977fc-103">Get (funzione)</span><span class="sxs-lookup"><span data-stu-id="977fc-103">Get function</span></span>
<span data-ttu-id="977fc-104">Recupera il valore della proprietà specificata, se presente.</span><span class="sxs-lookup"><span data-stu-id="977fc-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="977fc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="977fc-105">Syntax</span></span>  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="977fc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="977fc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="977fc-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="977fc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="977fc-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="977fc-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="977fc-109">[in] Il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="977fc-109">[in] The name of the property.</span></span>

<span data-ttu-id="977fc-110">`lFlags` [in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="977fc-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="977fc-111">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="977fc-111">This parameter must be 0.</span></span>

<span data-ttu-id="977fc-112">`pVal` [out] Se la funzione restituisce correttamente, contiene il valore di `wszName` proprietà.</span><span class="sxs-lookup"><span data-stu-id="977fc-112">`pVal` [out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="977fc-113">Il `pval` argomento è assegnato il tipo corretto e il valore per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="977fc-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

<span data-ttu-id="977fc-114">`pvtType` [out] Se la funzione restituisce correttamente, contiene un [costante di tipo CIM](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) che indica il tipo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="977fc-114">`pvtType` [out] If the function returns successfully, contains a [CIM-type constant](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) that indicates the property type.</span></span> <span data-ttu-id="977fc-115">Il valore può anche essere `null`.</span><span class="sxs-lookup"><span data-stu-id="977fc-115">Its value can also be `null`.</span></span> 

<span data-ttu-id="977fc-116">`plFlavor` [out] Se la funzione restituisce correttamente, riceve informazioni relative all'origine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="977fc-116">`plFlavor` [out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="977fc-117">Il valore può essere `null`, o una delle seguenti costanti WBEM_FLAVOR_TYPE definite nel *WbemCli.h* file di intestazione:</span><span class="sxs-lookup"><span data-stu-id="977fc-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="977fc-118">Costante</span><span class="sxs-lookup"><span data-stu-id="977fc-118">Constant</span></span>  |<span data-ttu-id="977fc-119">Valore</span><span class="sxs-lookup"><span data-stu-id="977fc-119">Value</span></span>  |<span data-ttu-id="977fc-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="977fc-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="977fc-121">0x40</span><span class="sxs-lookup"><span data-stu-id="977fc-121">0x40</span></span> | <span data-ttu-id="977fc-122">La proprietà è una proprietà di sistema standard.</span><span class="sxs-lookup"><span data-stu-id="977fc-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="977fc-123">0x20</span><span class="sxs-lookup"><span data-stu-id="977fc-123">0x20</span></span> | <span data-ttu-id="977fc-124">Per una classe: la proprietà viene ereditata dalla classe padre.</span><span class="sxs-lookup"><span data-stu-id="977fc-124">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="977fc-125">Per un'istanza: la proprietà, mentre ereditata dalla classe padre, non è stata modificata dall'istanza.</span><span class="sxs-lookup"><span data-stu-id="977fc-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="977fc-126">0</span><span class="sxs-lookup"><span data-stu-id="977fc-126">0</span></span> | <span data-ttu-id="977fc-127">Per una classe: la proprietà appartiene alla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="977fc-127">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="977fc-128">Per un'istanza: la proprietà viene modificata tramite l'istanza. ovvero, è stato fornito un valore o un qualificatore è stato aggiunto o modificato.</span><span class="sxs-lookup"><span data-stu-id="977fc-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="977fc-129">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="977fc-129">Return value</span></span>

<span data-ttu-id="977fc-130">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="977fc-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="977fc-131">Costante</span><span class="sxs-lookup"><span data-stu-id="977fc-131">Constant</span></span>  |<span data-ttu-id="977fc-132">Valore</span><span class="sxs-lookup"><span data-stu-id="977fc-132">Value</span></span>  |<span data-ttu-id="977fc-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="977fc-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="977fc-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="977fc-134">0x80041001</span></span> | <span data-ttu-id="977fc-135">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="977fc-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="977fc-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="977fc-136">0x80041008</span></span> | <span data-ttu-id="977fc-137">Uno o più parametri non vengono.</span><span class="sxs-lookup"><span data-stu-id="977fc-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="977fc-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="977fc-138">0x80041002</span></span> | <span data-ttu-id="977fc-139">La proprietà specificata non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="977fc-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="977fc-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="977fc-140">0x80041006</span></span> | <span data-ttu-id="977fc-141">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="977fc-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="977fc-142">0</span><span class="sxs-lookup"><span data-stu-id="977fc-142">0</span></span> | <span data-ttu-id="977fc-143">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="977fc-143">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="977fc-144">Note</span><span class="sxs-lookup"><span data-stu-id="977fc-144">Remarks</span></span>

<span data-ttu-id="977fc-145">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="977fc-145">This function wraps a call to the [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="977fc-146">Il `Get` funzione può restituire anche le proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="977fc-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="977fc-147">Il `pVal` argomento è assegnato il tipo corretto e il valore per il qualificatore e il modello COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) (funzione)</span><span class="sxs-lookup"><span data-stu-id="977fc-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) function</span></span>

## <a name="requirements"></a><span data-ttu-id="977fc-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="977fc-148">Requirements</span></span>  
 <span data-ttu-id="977fc-149">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="977fc-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="977fc-150">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="977fc-150">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="977fc-151">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="977fc-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="977fc-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="977fc-152">See also</span></span>  
[<span data-ttu-id="977fc-153">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="977fc-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
