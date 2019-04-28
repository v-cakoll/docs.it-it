---
title: Funzione GetMethodOrigin (riferimenti alle API non gestite)
description: La funzione GetMethodOrigin determina la classe in cui viene dichiarato un metodo.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193caa894b8697a65e8821c01a63dde9cc5b5ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608944"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="e0713-103">Funzione GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="e0713-103">GetMethodOrigin function</span></span>
<span data-ttu-id="e0713-104">Determina la classe in cui viene dichiarato un metodo.</span><span class="sxs-lookup"><span data-stu-id="e0713-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e0713-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0713-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="e0713-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0713-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e0713-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="e0713-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e0713-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="e0713-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="e0713-109">[in] Il nome del metodo per l'oggetto la cui classe proprietaria è richiesto.</span><span class="sxs-lookup"><span data-stu-id="e0713-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="e0713-110">[out] Riceve il nome della classe cui appartiene il metodo.</span><span class="sxs-lookup"><span data-stu-id="e0713-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="e0713-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e0713-111">Return value</span></span>

<span data-ttu-id="e0713-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="e0713-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e0713-113">Costante</span><span class="sxs-lookup"><span data-stu-id="e0713-113">Constant</span></span>  |<span data-ttu-id="e0713-114">Value</span><span class="sxs-lookup"><span data-stu-id="e0713-114">Value</span></span>  |<span data-ttu-id="e0713-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0713-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e0713-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e0713-116">0x80041002</span></span> | <span data-ttu-id="e0713-117">Il metodo specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="e0713-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e0713-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e0713-118">0x80041008</span></span> | <span data-ttu-id="e0713-119">Uno o più parametri non vengono.</span><span class="sxs-lookup"><span data-stu-id="e0713-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e0713-120">0</span><span class="sxs-lookup"><span data-stu-id="e0713-120">0</span></span> | <span data-ttu-id="e0713-121">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e0713-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e0713-122">Note</span><span class="sxs-lookup"><span data-stu-id="e0713-122">Remarks</span></span>

<span data-ttu-id="e0713-123">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="e0713-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="e0713-124">Poiché una classe può ereditare i metodi da una o più classi base, gli sviluppatori spesso vogliono determinare la classe in cui è definito un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="e0713-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="e0713-125">Il `pstrClassName` parametro non deve puntare a un valore valido `BSTR` prima di chiamare la funzione poiché si tratta di un `out` parametro; questo puntatore non viene deallocato dopo la funzione restituisce.</span><span class="sxs-lookup"><span data-stu-id="e0713-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0713-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0713-126">Requirements</span></span>  
<span data-ttu-id="e0713-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0713-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0713-128">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e0713-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e0713-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e0713-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0713-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0713-130">See also</span></span>

- [<span data-ttu-id="e0713-131">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="e0713-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
