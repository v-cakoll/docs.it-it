---
title: Funzione GetMethodOrigin (riferimenti alle API non gestite)
description: La funzione GetMethodOrigin determina la classe in cui viene dichiarato un metodo.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodOrigin
helpviewer_keywords: GetMethodOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7982ef2f272173e89434b64a4c296a2ce963594e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="1e049-103">GetMethodOrigin (funzione)</span><span class="sxs-lookup"><span data-stu-id="1e049-103">GetMethodOrigin function</span></span>
<span data-ttu-id="1e049-104">Determina la classe in cui viene dichiarato un metodo.</span><span class="sxs-lookup"><span data-stu-id="1e049-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1e049-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e049-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="1e049-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e049-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1e049-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="1e049-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1e049-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="1e049-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="1e049-109">[in] Il nome del metodo per l'oggetto è richiesta la cui classe proprietaria.</span><span class="sxs-lookup"><span data-stu-id="1e049-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="1e049-110">[out] Riceve il nome della classe cui appartiene il metodo.</span><span class="sxs-lookup"><span data-stu-id="1e049-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="1e049-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e049-111">Return value</span></span>

<span data-ttu-id="1e049-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1e049-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1e049-113">Costante</span><span class="sxs-lookup"><span data-stu-id="1e049-113">Constant</span></span>  |<span data-ttu-id="1e049-114">Valore</span><span class="sxs-lookup"><span data-stu-id="1e049-114">Value</span></span>  |<span data-ttu-id="1e049-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e049-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1e049-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1e049-116">0x80041002</span></span> | <span data-ttu-id="1e049-117">Il metodo specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="1e049-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1e049-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1e049-118">0x80041008</span></span> | <span data-ttu-id="1e049-119">Uno o più parametri non vengono.</span><span class="sxs-lookup"><span data-stu-id="1e049-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1e049-120">0</span><span class="sxs-lookup"><span data-stu-id="1e049-120">0</span></span> | <span data-ttu-id="1e049-121">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1e049-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1e049-122">Note</span><span class="sxs-lookup"><span data-stu-id="1e049-122">Remarks</span></span>

<span data-ttu-id="1e049-123">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="1e049-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1e049-124">Poiché una classe può ereditare metodi da una o più classi base, gli sviluppatori spesso necessario determinare la classe in cui è definito un metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="1e049-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="1e049-125">Il `pstrClassName` parametro non deve puntare a un oggetto valido `BSTR` prima di chiamare la funzione poiché si tratta di un `out` parametro; questo puntatore non viene deallocato dopo la funzione restituisce.</span><span class="sxs-lookup"><span data-stu-id="1e049-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e049-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e049-126">Requirements</span></span>  
<span data-ttu-id="1e049-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e049-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e049-128">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1e049-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1e049-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1e049-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e049-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e049-130">See also</span></span>  
[<span data-ttu-id="1e049-131">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1e049-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
