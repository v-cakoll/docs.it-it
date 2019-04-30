---
title: Funzione WritePropertyValue (riferimenti alle API non gestite)
description: La funzione WritePropertyValue scrive byte in una proprietà.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98103367f497b18f9b8fbd61a37abf9816b8356
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040404"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="7a209-103">WritePropertyValue (funzione)</span><span class="sxs-lookup"><span data-stu-id="7a209-103">WritePropertyValue function</span></span>
<span data-ttu-id="7a209-104">Scrive un numero specificato di byte in una proprietà identificata da un handle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a209-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="7a209-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a209-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="7a209-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a209-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7a209-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="7a209-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7a209-108">[in] Un puntatore a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) istanza.</span><span class="sxs-lookup"><span data-stu-id="7a209-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="7a209-109">[in] Numero intero che contiene l'handle che identifica questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a209-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="7a209-110">L'handle può essere recuperato chiamando il [GetPropertyHandle](getpropertyhandle.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="7a209-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="7a209-111">[in] Il numero di byte da scrivere per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a209-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="7a209-112">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="7a209-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="7a209-113">[out] Puntatore alla matrice di byte che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="7a209-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="7a209-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7a209-114">Return value</span></span>

<span data-ttu-id="7a209-115">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="7a209-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7a209-116">Costante</span><span class="sxs-lookup"><span data-stu-id="7a209-116">Constant</span></span>  |<span data-ttu-id="7a209-117">Value</span><span class="sxs-lookup"><span data-stu-id="7a209-117">Value</span></span>  |<span data-ttu-id="7a209-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a209-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7a209-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7a209-119">0x80041008</span></span> | <span data-ttu-id="7a209-120">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="7a209-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="7a209-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="7a209-121">0x80041005</span></span> | <span data-ttu-id="7a209-122">Si è verificato un tipo non corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7a209-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7a209-123">0</span><span class="sxs-lookup"><span data-stu-id="7a209-123">0</span></span> | <span data-ttu-id="7a209-124">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="7a209-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7a209-125">Note</span><span class="sxs-lookup"><span data-stu-id="7a209-125">Remarks</span></span>

<span data-ttu-id="7a209-126">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) (metodo).</span><span class="sxs-lookup"><span data-stu-id="7a209-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="7a209-127">Utilizzare questa funzione per impostare una stringa e tutti gli altri non -`DWORD` o non-`QWORD` dei dati.</span><span class="sxs-lookup"><span data-stu-id="7a209-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="7a209-128">Per i valori delle proprietà non stringa `lNumBytes` devono avere la dimensione di correggere i dati del tipo di proprietà specificato.</span><span class="sxs-lookup"><span data-stu-id="7a209-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="7a209-129">Per i valori di proprietà stringa `lNumBytes` deve essere la lunghezza della stringa specificata in byte con la stringa deve essere una lunghezza in byte pari ed essere seguito con un carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="7a209-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a209-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a209-130">Requirements</span></span>  
<span data-ttu-id="7a209-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a209-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a209-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7a209-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7a209-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7a209-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a209-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a209-134">See also</span></span>

- [<span data-ttu-id="7a209-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="7a209-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
