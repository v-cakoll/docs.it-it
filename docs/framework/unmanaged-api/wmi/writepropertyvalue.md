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
ms.openlocfilehash: 47120ff9de9e6e4802c5aea990841b235cd6c74c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783061"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="ec576-103">WritePropertyValue (funzione)</span><span class="sxs-lookup"><span data-stu-id="ec576-103">WritePropertyValue function</span></span>
<span data-ttu-id="ec576-104">Scrive un numero specificato di byte in una proprietà identificata da un handle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec576-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ec576-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec576-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="ec576-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec576-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ec576-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ec576-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ec576-108">[in] Un puntatore a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) istanza.</span><span class="sxs-lookup"><span data-stu-id="ec576-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="ec576-109">[in] Numero intero che contiene l'handle che identifica questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec576-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="ec576-110">L'handle può essere recuperato chiamando il [GetPropertyHandle](getpropertyhandle.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="ec576-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="ec576-111">[in] Il numero di byte da scrivere per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec576-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="ec576-112">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="ec576-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="ec576-113">[out] Puntatore alla matrice di byte che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="ec576-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="ec576-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ec576-114">Return value</span></span>

<span data-ttu-id="ec576-115">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ec576-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ec576-116">Costante</span><span class="sxs-lookup"><span data-stu-id="ec576-116">Constant</span></span>  |<span data-ttu-id="ec576-117">Valore</span><span class="sxs-lookup"><span data-stu-id="ec576-117">Value</span></span>  |<span data-ttu-id="ec576-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec576-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ec576-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ec576-119">0x80041008</span></span> | <span data-ttu-id="ec576-120">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="ec576-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="ec576-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="ec576-121">0x80041005</span></span> | <span data-ttu-id="ec576-122">Si è verificato un tipo non corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ec576-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ec576-123">0</span><span class="sxs-lookup"><span data-stu-id="ec576-123">0</span></span> | <span data-ttu-id="ec576-124">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ec576-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ec576-125">Note</span><span class="sxs-lookup"><span data-stu-id="ec576-125">Remarks</span></span>

<span data-ttu-id="ec576-126">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ec576-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="ec576-127">Utilizzare questa funzione per impostare una stringa e tutti gli altri non -`DWORD` o non-`QWORD` dei dati.</span><span class="sxs-lookup"><span data-stu-id="ec576-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="ec576-128">Per i valori delle proprietà non stringa `lNumBytes` devono avere la dimensione di correggere i dati del tipo di proprietà specificato.</span><span class="sxs-lookup"><span data-stu-id="ec576-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="ec576-129">Per i valori di proprietà stringa `lNumBytes` deve essere la lunghezza della stringa specificata in byte con la stringa deve essere una lunghezza in byte pari ed essere seguito con un carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="ec576-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="ec576-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec576-130">Requirements</span></span>  
<span data-ttu-id="ec576-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec576-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec576-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ec576-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ec576-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ec576-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec576-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec576-134">See also</span></span>

- [<span data-ttu-id="ec576-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ec576-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
