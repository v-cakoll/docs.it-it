---
title: Funzione GetPropertyHandle (riferimenti alle API non gestite)
description: La funzione GetPropertyHandle restituisce un handle univoco che una proprietà di identità.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2383003012ce1f6adffe0ad78ab614323840496f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200415"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="96203-103">GetPropertyHandle (funzione)</span><span class="sxs-lookup"><span data-stu-id="96203-103">GetPropertyHandle function</span></span>
<span data-ttu-id="96203-104">Restituisce un handle univoco che identifica una proprietà.</span><span class="sxs-lookup"><span data-stu-id="96203-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="96203-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96203-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="96203-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="96203-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="96203-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="96203-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="96203-108">[in] Un puntatore a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) istanza.</span><span class="sxs-lookup"><span data-stu-id="96203-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="96203-109">[in] Stringa con terminazione null di characaters con codifica UTF16 che contiene il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="96203-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="96203-110">[out] Un puntatore a un [ `CIMTYPE` ](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) membro di enumerazione che rappresenta il tipo CIM della proprietà.</span><span class="sxs-lookup"><span data-stu-id="96203-110">[out] A pointer to a [`CIMTYPE`](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="96203-111">[out] Un puntatore a un integer contenente l'handle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="96203-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="96203-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="96203-112">Return value</span></span>

<span data-ttu-id="96203-113">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="96203-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="96203-114">Costante</span><span class="sxs-lookup"><span data-stu-id="96203-114">Constant</span></span>  |<span data-ttu-id="96203-115">Valore</span><span class="sxs-lookup"><span data-stu-id="96203-115">Value</span></span>  |<span data-ttu-id="96203-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96203-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="96203-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="96203-117">0x80041002</span></span> | <span data-ttu-id="96203-118">Il nome della proprietà specificata non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="96203-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="96203-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="96203-119">0x80041008</span></span> | <span data-ttu-id="96203-120">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="96203-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="96203-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="96203-121">0x8004100c</span></span> | <span data-ttu-id="96203-122">La proprietà richiesta è di tipo vengono `CIM_OBJECT` o `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="96203-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="96203-123">0</span><span class="sxs-lookup"><span data-stu-id="96203-123">0</span></span> | <span data-ttu-id="96203-124">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="96203-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="96203-125">Note</span><span class="sxs-lookup"><span data-stu-id="96203-125">Remarks</span></span>

<span data-ttu-id="96203-126">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) (metodo).</span><span class="sxs-lookup"><span data-stu-id="96203-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="96203-127">È possibile usare questo handle per identificare le proprietà quando si usa [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) metodi per leggere o scrivere i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="96203-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="96203-128">Gli handle possono essere recuperati per le proprietà di tutti i tipi di dati diverso da `CIM_OBJECT` e `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="96203-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="96203-129">Restituito lavoro handle per tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="96203-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="96203-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96203-130">Requirements</span></span>  
<span data-ttu-id="96203-131">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96203-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96203-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="96203-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="96203-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="96203-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96203-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96203-134">See also</span></span>  
[<span data-ttu-id="96203-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="96203-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
