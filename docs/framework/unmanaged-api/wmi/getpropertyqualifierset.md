---
title: Funzione GetPropertyQualifierSet (riferimenti alle API non gestite)
description: La funzione GetPropertyQualifierSet recupera il qualificatore di impostazione per una proprietà.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2951733211737f06cd737b20bd1537277be1be1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461477"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="da5ef-103">GetPropertyQualifierSet (funzione)</span><span class="sxs-lookup"><span data-stu-id="da5ef-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="da5ef-104">Recupera il qualificatore impostato per una particolare proprietà.</span><span class="sxs-lookup"><span data-stu-id="da5ef-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="da5ef-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da5ef-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="da5ef-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="da5ef-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="da5ef-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="da5ef-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="da5ef-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="da5ef-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="da5ef-109">[in] Il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="da5ef-109">[in] The property  name.</span></span> <span data-ttu-id="da5ef-110">`wszProperty` deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="da5ef-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="da5ef-111">[out] Riceve il puntatore a interfaccia che consente l'accesso per i qualificatori della proprietà.</span><span class="sxs-lookup"><span data-stu-id="da5ef-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="da5ef-112">Il parametro `ppQualSet` non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="da5ef-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="da5ef-113">Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore è impostato in modo che punti a `null`.</span><span class="sxs-lookup"><span data-stu-id="da5ef-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="da5ef-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da5ef-114">Return value</span></span>

<span data-ttu-id="da5ef-115">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="da5ef-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="da5ef-116">Costante</span><span class="sxs-lookup"><span data-stu-id="da5ef-116">Constant</span></span>  |<span data-ttu-id="da5ef-117">Valore</span><span class="sxs-lookup"><span data-stu-id="da5ef-117">Value</span></span>  |<span data-ttu-id="da5ef-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da5ef-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="da5ef-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="da5ef-119">0x80041001</span></span> | <span data-ttu-id="da5ef-120">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="da5ef-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="da5ef-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="da5ef-121">0x80041002</span></span> | <span data-ttu-id="da5ef-122">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="da5ef-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="da5ef-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="da5ef-123">0x80041006</span></span> | <span data-ttu-id="da5ef-124">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="da5ef-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="da5ef-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="da5ef-125">0x80041008</span></span> | <span data-ttu-id="da5ef-126">È un parametro `null`.</span><span class="sxs-lookup"><span data-stu-id="da5ef-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="da5ef-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="da5ef-127">0x80041030</span></span> | <span data-ttu-id="da5ef-128">La funzione tenta di ottenere i qualificatori di una proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="da5ef-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="da5ef-129">0</span><span class="sxs-lookup"><span data-stu-id="da5ef-129">0</span></span> | <span data-ttu-id="da5ef-130">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="da5ef-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="da5ef-131">Note</span><span class="sxs-lookup"><span data-stu-id="da5ef-131">Remarks</span></span>

<span data-ttu-id="da5ef-132">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="da5ef-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="da5ef-133">Una chiamata a questa funzione è supportata solo se l'oggetto corrente è una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="da5ef-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="da5ef-134">Modifica di metodo non è disponibile per [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters che puntano a istanze CIM.</span><span class="sxs-lookup"><span data-stu-id="da5ef-134">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="da5ef-135">Poiché ogni metodo può avere un proprio qualificatori, il [IWbemQualifierSet puntatore](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.</span><span class="sxs-lookup"><span data-stu-id="da5ef-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="da5ef-136">Poiché le proprietà di sistema non dispongono di alcun qualificatori, la funzione restituisce `WBEM_E_SYSTEM_PROPERTY` se si tenta di ottenere un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) puntatore per una proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="da5ef-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="da5ef-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da5ef-137">Requirements</span></span>  
<span data-ttu-id="da5ef-138">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da5ef-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da5ef-139">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="da5ef-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="da5ef-140">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da5ef-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5ef-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da5ef-141">See also</span></span>  
[<span data-ttu-id="da5ef-142">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="da5ef-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
