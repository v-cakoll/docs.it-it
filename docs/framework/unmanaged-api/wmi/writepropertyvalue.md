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
ms.openlocfilehash: f02fb3877d55e9f47384b281573202712c29c606
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107297"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="b234b-103">WritePropertyValue (funzione)</span><span class="sxs-lookup"><span data-stu-id="b234b-103">WritePropertyValue function</span></span>
<span data-ttu-id="b234b-104">Scrive un numero specificato di byte in una proprietà identificata da un handle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="b234b-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b234b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b234b-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="b234b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b234b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b234b-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="b234b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b234b-108">in Puntatore a un'istanza di [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .</span><span class="sxs-lookup"><span data-stu-id="b234b-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="b234b-109">in Intero contenente l'handle che identifica questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="b234b-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="b234b-110">È possibile recuperare l'handle chiamando la funzione [GetPropertyHandle](getpropertyhandle.md) .</span><span class="sxs-lookup"><span data-stu-id="b234b-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="b234b-111">in Numero di byte scritti nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="b234b-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="b234b-112">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="b234b-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="b234b-113">out Puntatore alla matrice di byte che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="b234b-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="b234b-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b234b-114">Return value</span></span>

<span data-ttu-id="b234b-115">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="b234b-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b234b-116">Costante</span><span class="sxs-lookup"><span data-stu-id="b234b-116">Constant</span></span>  |<span data-ttu-id="b234b-117">Value</span><span class="sxs-lookup"><span data-stu-id="b234b-117">Value</span></span>  |<span data-ttu-id="b234b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b234b-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b234b-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b234b-119">0x80041008</span></span> | <span data-ttu-id="b234b-120">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="b234b-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="b234b-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="b234b-121">0x80041005</span></span> | <span data-ttu-id="b234b-122">Si è verificata una mancata corrispondenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="b234b-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b234b-123">0</span><span class="sxs-lookup"><span data-stu-id="b234b-123">0</span></span> | <span data-ttu-id="b234b-124">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b234b-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b234b-125">Note</span><span class="sxs-lookup"><span data-stu-id="b234b-125">Remarks</span></span>

<span data-ttu-id="b234b-126">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) .</span><span class="sxs-lookup"><span data-stu-id="b234b-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="b234b-127">Usare questa funzione per impostare la stringa e tutti gli altri dati non`DWORD` o non`QWORD`.</span><span class="sxs-lookup"><span data-stu-id="b234b-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="b234b-128">Per i valori di proprietà non stringa, `lNumBytes` deve essere la dimensione dei dati corretta del tipo di proprietà specificato.</span><span class="sxs-lookup"><span data-stu-id="b234b-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="b234b-129">Per i valori delle proprietà di stringa, `lNumBytes` deve essere la lunghezza della stringa specificata in byte e la stringa stessa deve avere una lunghezza pari in byte e essere seguita da un carattere di terminazione null.</span><span class="sxs-lookup"><span data-stu-id="b234b-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="b234b-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b234b-130">Requirements</span></span>  
<span data-ttu-id="b234b-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b234b-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b234b-132">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="b234b-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b234b-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b234b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b234b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b234b-134">See also</span></span>

- [<span data-ttu-id="b234b-135">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b234b-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
