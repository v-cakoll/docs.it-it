---
title: Funzione GetPropertyOrigin (riferimenti alle API non gestite)
description: La funzione GetPropertyOrigin determina la classe in cui viene dichiarata una proprietà.
ms.date: 11/06/2017
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
ms.openlocfilehash: 42e5cd6ee438b33fd07fd7c3242cc3c2a6513dd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723257"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="a416b-103">Funzione GetPropertyOrigin</span><span class="sxs-lookup"><span data-stu-id="a416b-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="a416b-104">Determina la classe in cui viene dichiarata una proprietà.</span><span class="sxs-lookup"><span data-stu-id="a416b-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a416b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a416b-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="a416b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a416b-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="a416b-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="a416b-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="a416b-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="a416b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="a416b-109">[in] Il nome della proprietà per l'oggetto la cui classe proprietaria viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="a416b-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="a416b-110">[out] Riceve il nome della classe cui appartiene la proprietà.</span><span class="sxs-lookup"><span data-stu-id="a416b-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="a416b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a416b-111">Return value</span></span>

<span data-ttu-id="a416b-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="a416b-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a416b-113">Costante</span><span class="sxs-lookup"><span data-stu-id="a416b-113">Constant</span></span>  |<span data-ttu-id="a416b-114">Value</span><span class="sxs-lookup"><span data-stu-id="a416b-114">Value</span></span>  |<span data-ttu-id="a416b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a416b-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="a416b-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a416b-116">0x80041001</span></span> | <span data-ttu-id="a416b-117">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="a416b-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a416b-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a416b-118">0x80041002</span></span> | <span data-ttu-id="a416b-119">La proprietà specificata non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="a416b-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a416b-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a416b-120">0x80041008</span></span> | <span data-ttu-id="a416b-121">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="a416b-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a416b-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a416b-122">0x80041006</span></span> | <span data-ttu-id="a416b-123">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a416b-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a416b-124">0</span><span class="sxs-lookup"><span data-stu-id="a416b-124">0</span></span> | <span data-ttu-id="a416b-125">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a416b-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="a416b-126">Note</span><span class="sxs-lookup"><span data-stu-id="a416b-126">Remarks</span></span>

<span data-ttu-id="a416b-127">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a416b-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="a416b-128">Poiché una classe può ereditare le proprietà da uno o più classi base, gli sviluppatori spesso vogliono determinare la proprietà in cui è definito un metodo specifico.</span><span class="sxs-lookup"><span data-stu-id="a416b-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="a416b-129">Il `pstrClassName` parametro non deve puntare a un valore valido `BSTR` prima di chiamare la funzione poiché si tratta di un `out` parametro; questo puntatore non viene deallocato dopo la funzione restituisce.</span><span class="sxs-lookup"><span data-stu-id="a416b-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="a416b-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a416b-130">Requirements</span></span>

<span data-ttu-id="a416b-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a416b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a416b-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a416b-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="a416b-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a416b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a416b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a416b-134">See also</span></span>

- [<span data-ttu-id="a416b-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="a416b-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)