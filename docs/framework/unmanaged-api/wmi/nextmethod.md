---
title: Funzione NextMethod (riferimenti alle API non gestite)
description: La funzione NextMethod Recupera il metodo successivo in un'enumerazione.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee743a4499824bea723043d5a2c7d57d7cbd7106
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798430"
---
# <a name="nextmethod-function"></a><span data-ttu-id="dccb6-103">NextMethod (funzione)</span><span class="sxs-lookup"><span data-stu-id="dccb6-103">NextMethod function</span></span>
<span data-ttu-id="dccb6-104">Recupera il metodo successivo in un'enumerazione che inizia con una chiamata a [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="dccb6-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="dccb6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dccb6-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="dccb6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="dccb6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="dccb6-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="dccb6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="dccb6-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="dccb6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="dccb6-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="dccb6-109">[in] Reserved.</span></span> <span data-ttu-id="dccb6-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="dccb6-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="dccb6-111">out Puntatore che punta a `null` prima della chiamata.</span><span class="sxs-lookup"><span data-stu-id="dccb6-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="dccb6-112">Quando la funzione restituisce, l'indirizzo di un nuovo `BSTR` oggetto che contiene il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="dccb6-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="dccb6-113">out Puntatore che riceve un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i `in` parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="dccb6-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="dccb6-114">out Puntatore che riceve un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i `out` parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="dccb6-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="dccb6-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dccb6-115">Return value</span></span>

<span data-ttu-id="dccb6-116">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="dccb6-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dccb6-117">Costante</span><span class="sxs-lookup"><span data-stu-id="dccb6-117">Constant</span></span>  |<span data-ttu-id="dccb6-118">Valore</span><span class="sxs-lookup"><span data-stu-id="dccb6-118">Value</span></span>  |<span data-ttu-id="dccb6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dccb6-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="dccb6-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="dccb6-120">0x8004101d</span></span> | <span data-ttu-id="dccb6-121">Nessuna chiamata alla [`BeginEnumeration`](beginenumeration.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="dccb6-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="dccb6-122">0</span><span class="sxs-lookup"><span data-stu-id="dccb6-122">0</span></span> | <span data-ttu-id="dccb6-123">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="dccb6-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="dccb6-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="dccb6-124">0x40005</span></span> | <span data-ttu-id="dccb6-125">Non sono presenti altre proprietà nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="dccb6-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="dccb6-126">Note</span><span class="sxs-lookup"><span data-stu-id="dccb6-126">Remarks</span></span>

<span data-ttu-id="dccb6-127">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="dccb6-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="dccb6-128">Il chiamante avvia la sequenza di enumerazione chiamando la funzione [BeginMethodEnumeration](beginmethodenumeration.md) e quindi chiama la funzione [NextMethod] finché la funzione non restituisce `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="dccb6-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="dccb6-129">Facoltativamente, il chiamante completa la sequenza chiamando [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="dccb6-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="dccb6-130">Il chiamante può terminare l'enumerazione prima chiamando [EndMethodEnumeration](endmethodenumeration.md) in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="dccb6-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="dccb6-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="dccb6-131">Example</span></span>

<span data-ttu-id="dccb6-132">Per un C++ esempio, vedere il metodo [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="dccb6-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dccb6-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dccb6-133">Requirements</span></span>  
 <span data-ttu-id="dccb6-134">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dccb6-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dccb6-135">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="dccb6-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="dccb6-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dccb6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccb6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dccb6-137">See also</span></span>

- [<span data-ttu-id="dccb6-138">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="dccb6-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
