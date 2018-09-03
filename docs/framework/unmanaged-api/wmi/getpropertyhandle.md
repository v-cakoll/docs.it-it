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
ms.openlocfilehash: 94171b0708c97eb7510e916e451ed03645d706f3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43469882"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="23b73-103">GetPropertyHandle (funzione)</span><span class="sxs-lookup"><span data-stu-id="23b73-103">GetPropertyHandle function</span></span>
<span data-ttu-id="23b73-104">Restituisce un handle univoco che identifica una proprietà.</span><span class="sxs-lookup"><span data-stu-id="23b73-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="23b73-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23b73-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="23b73-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="23b73-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="23b73-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="23b73-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="23b73-108">[in] Un puntatore a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) istanza.</span><span class="sxs-lookup"><span data-stu-id="23b73-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="23b73-109">[in] Stringa con terminazione null di characaters con codifica UTF16 che contiene il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23b73-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="23b73-110">[out] Un puntatore a un [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) membro di enumerazione che rappresenta il tipo CIM della proprietà.</span><span class="sxs-lookup"><span data-stu-id="23b73-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="23b73-111">[out] Un puntatore a un integer contenente l'handle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="23b73-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="23b73-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23b73-112">Return value</span></span>

<span data-ttu-id="23b73-113">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="23b73-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="23b73-114">Costante</span><span class="sxs-lookup"><span data-stu-id="23b73-114">Constant</span></span>  |<span data-ttu-id="23b73-115">Valore</span><span class="sxs-lookup"><span data-stu-id="23b73-115">Value</span></span>  |<span data-ttu-id="23b73-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23b73-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="23b73-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="23b73-117">0x80041002</span></span> | <span data-ttu-id="23b73-118">Il nome della proprietà specificata non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="23b73-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="23b73-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="23b73-119">0x80041008</span></span> | <span data-ttu-id="23b73-120">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="23b73-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="23b73-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="23b73-121">0x8004100c</span></span> | <span data-ttu-id="23b73-122">La proprietà richiesta è di tipo vengono `CIM_OBJECT` o `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="23b73-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="23b73-123">0</span><span class="sxs-lookup"><span data-stu-id="23b73-123">0</span></span> | <span data-ttu-id="23b73-124">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="23b73-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="23b73-125">Note</span><span class="sxs-lookup"><span data-stu-id="23b73-125">Remarks</span></span>

<span data-ttu-id="23b73-126">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) (metodo).</span><span class="sxs-lookup"><span data-stu-id="23b73-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="23b73-127">È possibile usare questo handle per identificare le proprietà quando si usa [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) metodi per leggere o scrivere i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="23b73-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="23b73-128">Gli handle possono essere recuperati per le proprietà di tutti i tipi di dati diverso da `CIM_OBJECT` e `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="23b73-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="23b73-129">Restituito lavoro handle per tutte le istanze di una classe.</span><span class="sxs-lookup"><span data-stu-id="23b73-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="23b73-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23b73-130">Requirements</span></span>  
<span data-ttu-id="23b73-131">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23b73-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23b73-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="23b73-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="23b73-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="23b73-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b73-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b73-134">See also</span></span>  
[<span data-ttu-id="23b73-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="23b73-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
