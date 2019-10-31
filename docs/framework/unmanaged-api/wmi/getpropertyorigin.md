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
ms.openlocfilehash: 6cab3765f0359f5dd18831acaaa1aefce3fe1081
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101856"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="833f3-103">Funzione GetPropertyOrigin</span><span class="sxs-lookup"><span data-stu-id="833f3-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="833f3-104">Determina la classe in cui viene dichiarata una proprietà.</span><span class="sxs-lookup"><span data-stu-id="833f3-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="833f3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="833f3-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="833f3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="833f3-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="833f3-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="833f3-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="833f3-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="833f3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="833f3-109">in Nome della proprietà per l'oggetto di cui viene richiesta la classe proprietaria.</span><span class="sxs-lookup"><span data-stu-id="833f3-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="833f3-110">out Riceve il nome della classe a cui appartiene la proprietà.</span><span class="sxs-lookup"><span data-stu-id="833f3-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="833f3-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="833f3-111">Return value</span></span>

<span data-ttu-id="833f3-112">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="833f3-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="833f3-113">Costante</span><span class="sxs-lookup"><span data-stu-id="833f3-113">Constant</span></span>  |<span data-ttu-id="833f3-114">Value</span><span class="sxs-lookup"><span data-stu-id="833f3-114">Value</span></span>  |<span data-ttu-id="833f3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="833f3-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="833f3-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="833f3-116">0x80041001</span></span> | <span data-ttu-id="833f3-117">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="833f3-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="833f3-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="833f3-118">0x80041002</span></span> | <span data-ttu-id="833f3-119">Impossibile trovare la proprietà specificata.</span><span class="sxs-lookup"><span data-stu-id="833f3-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="833f3-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="833f3-120">0x80041008</span></span> | <span data-ttu-id="833f3-121">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="833f3-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="833f3-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="833f3-122">0x80041006</span></span> | <span data-ttu-id="833f3-123">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="833f3-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="833f3-124">0</span><span class="sxs-lookup"><span data-stu-id="833f3-124">0</span></span> | <span data-ttu-id="833f3-125">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="833f3-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="833f3-126">Note</span><span class="sxs-lookup"><span data-stu-id="833f3-126">Remarks</span></span>

<span data-ttu-id="833f3-127">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) .</span><span class="sxs-lookup"><span data-stu-id="833f3-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="833f3-128">Poiché una classe può ereditare proprietà da una o più classi di base, gli sviluppatori spesso vogliono determinare la proprietà in cui è definito un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="833f3-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="833f3-129">Il parametro `pstrClassName` non deve puntare a una `BSTR` valida prima della chiamata della funzione perché si tratta di un parametro `out`; Questo puntatore non viene deallocato dopo la restituzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="833f3-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="833f3-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="833f3-130">Requirements</span></span>

<span data-ttu-id="833f3-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="833f3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="833f3-132">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="833f3-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="833f3-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="833f3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="833f3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="833f3-134">See also</span></span>

- [<span data-ttu-id="833f3-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="833f3-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
