---
title: Funzione GetPropertyHandle (riferimenti alle API non gestite)
description: La funzione GetPropertyHandle restituisce un handle univoco che identifica una proprietà.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5af003f0295e0b403727f9af6b03ab81c4b8bccb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101865"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="64fee-103">Funzione GetPropertyHandle</span><span class="sxs-lookup"><span data-stu-id="64fee-103">GetPropertyHandle function</span></span>

<span data-ttu-id="64fee-104">Restituisce un handle univoco che identifica una proprietà.</span><span class="sxs-lookup"><span data-stu-id="64fee-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="64fee-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64fee-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="64fee-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="64fee-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="64fee-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="64fee-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="64fee-108">in Puntatore a un'istanza di [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .</span><span class="sxs-lookup"><span data-stu-id="64fee-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="64fee-109">in Stringa con terminazione null di caratteri con codifica UTF16 che contiene il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="64fee-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="64fee-110">out Puntatore a un membro di enumerazione [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) che rappresenta il tipo CIM della proprietà.</span><span class="sxs-lookup"><span data-stu-id="64fee-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="64fee-111">out Puntatore a un Integer contenente l'handle della proprietà.</span><span class="sxs-lookup"><span data-stu-id="64fee-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="64fee-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="64fee-112">Return value</span></span>

<span data-ttu-id="64fee-113">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="64fee-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="64fee-114">Costante</span><span class="sxs-lookup"><span data-stu-id="64fee-114">Constant</span></span>  |<span data-ttu-id="64fee-115">Value</span><span class="sxs-lookup"><span data-stu-id="64fee-115">Value</span></span>  |<span data-ttu-id="64fee-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64fee-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="64fee-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="64fee-117">0x80041002</span></span> | <span data-ttu-id="64fee-118">Il nome di proprietà specificato non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="64fee-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="64fee-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="64fee-119">0x80041008</span></span> | <span data-ttu-id="64fee-120">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="64fee-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="64fee-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="64fee-121">0x8004100c</span></span> | <span data-ttu-id="64fee-122">La proprietà richiesta è di tipo `CIM_OBJECT` o `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="64fee-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="64fee-123">0</span><span class="sxs-lookup"><span data-stu-id="64fee-123">0</span></span> | <span data-ttu-id="64fee-124">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="64fee-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="64fee-125">Note</span><span class="sxs-lookup"><span data-stu-id="64fee-125">Remarks</span></span>

<span data-ttu-id="64fee-126">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) .</span><span class="sxs-lookup"><span data-stu-id="64fee-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="64fee-127">È possibile utilizzare questo handle per identificare le proprietà quando si utilizzano i metodi [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) per leggere o scrivere i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="64fee-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="64fee-128">È possibile recuperare gli handle per le proprietà di tutti i tipi di dati diversi da `CIM_OBJECT` e `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="64fee-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="64fee-129">Gli handle restituiti funzionano in tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="64fee-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="64fee-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64fee-130">Requirements</span></span>

<span data-ttu-id="64fee-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64fee-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="64fee-132">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="64fee-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="64fee-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="64fee-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="64fee-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64fee-134">See also</span></span>

- [<span data-ttu-id="64fee-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="64fee-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
