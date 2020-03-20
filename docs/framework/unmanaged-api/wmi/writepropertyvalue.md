---
title: WritePropertyValue function (Unmanaged API Reference)
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174836"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="6b060-103">Funzione WritePropertyValue</span><span class="sxs-lookup"><span data-stu-id="6b060-103">WritePropertyValue function</span></span>
<span data-ttu-id="6b060-104">Scrive un numero specificato di byte in una proprietà identificata da un handle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="6b060-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6b060-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b060-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a><span data-ttu-id="6b060-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b060-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6b060-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6b060-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6b060-108">[in] Puntatore a un'istanza di [IWbemObjectAccess.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)</span><span class="sxs-lookup"><span data-stu-id="6b060-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="6b060-109">[in] Intero che contiene l'handle che identifica questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="6b060-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="6b060-110">L'handle può essere recuperato chiamando il [GetPropertyHandle](getpropertyhandle.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="6b060-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>

`lNumBytes`  
<span data-ttu-id="6b060-111">[in] Numero di byte scritti nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="6b060-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="6b060-112">Vedere la sezione [Osservazioni](#remarks) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="6b060-112">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="6b060-113">`pHandle`[fuori] Puntatore alla matrice di byte che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="6b060-113">`pHandle` [out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="6b060-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6b060-114">Return value</span></span>

<span data-ttu-id="6b060-115">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="6b060-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6b060-116">Costante</span><span class="sxs-lookup"><span data-stu-id="6b060-116">Constant</span></span>  |<span data-ttu-id="6b060-117">valore</span><span class="sxs-lookup"><span data-stu-id="6b060-117">Value</span></span>  |<span data-ttu-id="6b060-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b060-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6b060-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6b060-119">0x80041008</span></span> | <span data-ttu-id="6b060-120">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="6b060-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="6b060-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="6b060-121">0x80041005</span></span> | <span data-ttu-id="6b060-122">Si è verificata un'incongruenza di tipo.</span><span class="sxs-lookup"><span data-stu-id="6b060-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6b060-123">0</span><span class="sxs-lookup"><span data-stu-id="6b060-123">0</span></span> | <span data-ttu-id="6b060-124">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6b060-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6b060-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6b060-125">Remarks</span></span>

<span data-ttu-id="6b060-126">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) .</span><span class="sxs-lookup"><span data-stu-id="6b060-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="6b060-127">Utilizzare questa funzione per impostare`DWORD` la stringa`QWORD` e tutti gli altri dati non o non.</span><span class="sxs-lookup"><span data-stu-id="6b060-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="6b060-128">Per i valori `lNumBytes` di proprietà non stringa, deve essere la dimensione dei dati corretta del tipo di proprietà specificato.</span><span class="sxs-lookup"><span data-stu-id="6b060-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="6b060-129">Per i valori `lNumBytes` di proprietà stringa, deve essere la lunghezza della stringa specificata in byte e la stringa stessa deve essere di lunghezza pari in byte ed essere seguita con un carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="6b060-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b060-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b060-130">Requirements</span></span>  
<span data-ttu-id="6b060-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b060-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b060-132">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6b060-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6b060-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6b060-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b060-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b060-134">See also</span></span>

- [<span data-ttu-id="6b060-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="6b060-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
