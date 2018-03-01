---
title: Funzione GetPropertyOrigin (riferimenti alle API Unmnaged)
description: "La funzione GetPropertyOrigin determina la classe in cui viene dichiarata una proprietà."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0a79bfc62ad776cb2bfab2c143d19761d64358bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="ce04b-103">GetPropertyOrigin (funzione)</span><span class="sxs-lookup"><span data-stu-id="ce04b-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="ce04b-104">Determina la classe in cui viene dichiarata una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce04b-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ce04b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce04b-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="ce04b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce04b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ce04b-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ce04b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ce04b-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="ce04b-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="ce04b-109">[in] Il nome della proprietà per l'oggetto classe il cui proprietario è richiesto.</span><span class="sxs-lookup"><span data-stu-id="ce04b-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="ce04b-110">[out] Riceve il nome della classe cui appartiene la proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce04b-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="ce04b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ce04b-111">Return value</span></span>

<span data-ttu-id="ce04b-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ce04b-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ce04b-113">Costante</span><span class="sxs-lookup"><span data-stu-id="ce04b-113">Constant</span></span>  |<span data-ttu-id="ce04b-114">Valore</span><span class="sxs-lookup"><span data-stu-id="ce04b-114">Value</span></span>  |<span data-ttu-id="ce04b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce04b-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ce04b-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ce04b-116">0x80041001</span></span> | <span data-ttu-id="ce04b-117">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="ce04b-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ce04b-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ce04b-118">0x80041002</span></span> | <span data-ttu-id="ce04b-119">La proprietà specificata non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="ce04b-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ce04b-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ce04b-120">0x80041008</span></span> | <span data-ttu-id="ce04b-121">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="ce04b-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ce04b-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ce04b-122">0x80041006</span></span> | <span data-ttu-id="ce04b-123">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ce04b-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ce04b-124">0</span><span class="sxs-lookup"><span data-stu-id="ce04b-124">0</span></span> | <span data-ttu-id="ce04b-125">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ce04b-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ce04b-126">Note</span><span class="sxs-lookup"><span data-stu-id="ce04b-126">Remarks</span></span>

<span data-ttu-id="ce04b-127">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="ce04b-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ce04b-128">Poiché una classe può ereditare proprietà da una o più classi base, gli sviluppatori spesso necessario determinare la proprietà in cui è definito un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="ce04b-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="ce04b-129">Il `pstrClassName` parametro non deve puntare a un oggetto valido `BSTR` prima di chiamare la funzione poiché si tratta di un `out` parametro; questo puntatore non viene deallocato dopo la funzione restituisce.</span><span class="sxs-lookup"><span data-stu-id="ce04b-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce04b-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce04b-130">Requirements</span></span>  
<span data-ttu-id="ce04b-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce04b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce04b-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ce04b-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ce04b-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ce04b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce04b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce04b-134">See also</span></span>  
[<span data-ttu-id="ce04b-135">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ce04b-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
