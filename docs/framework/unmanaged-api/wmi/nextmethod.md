---
title: NextMethod (riferimento alle API non gestite)
description: La funzione NextMethod recupera il metodo successivo in un'enumerazione.
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
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174927"
---
# <a name="nextmethod-function"></a><span data-ttu-id="ac5a3-103">Funzione NextMethod</span><span class="sxs-lookup"><span data-stu-id="ac5a3-103">NextMethod function</span></span>
<span data-ttu-id="ac5a3-104">Recupera il metodo successivo in un'enumerazione che inizia con una chiamata a [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ac5a3-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ac5a3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac5a3-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="ac5a3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac5a3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ac5a3-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ac5a3-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="ac5a3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="ac5a3-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-109">[in] Reserved.</span></span> <span data-ttu-id="ac5a3-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="ac5a3-111">[fuori] Puntatore a `null` cui punta prima della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="ac5a3-112">Quando la funzione restituisce, `BSTR` l'indirizzo di un nuovo che contiene il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="ac5a3-113">[fuori] Puntatore che riceve un puntatore a un oggetto `in` [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="ac5a3-114">[fuori] Puntatore che riceve un puntatore a un oggetto `out` [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene i parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="ac5a3-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac5a3-115">Return value</span></span>

<span data-ttu-id="ac5a3-116">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="ac5a3-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ac5a3-117">Costante</span><span class="sxs-lookup"><span data-stu-id="ac5a3-117">Constant</span></span>  |<span data-ttu-id="ac5a3-118">valore</span><span class="sxs-lookup"><span data-stu-id="ac5a3-118">Value</span></span>  |<span data-ttu-id="ac5a3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac5a3-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="ac5a3-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ac5a3-120">0x8004101d</span></span> | <span data-ttu-id="ac5a3-121">Non è stata [`BeginEnumeration`](beginenumeration.md) chiamata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ac5a3-122">0</span><span class="sxs-lookup"><span data-stu-id="ac5a3-122">0</span></span> | <span data-ttu-id="ac5a3-123">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="ac5a3-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="ac5a3-124">0x40005</span></span> | <span data-ttu-id="ac5a3-125">Non sono presenti altre proprietà nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ac5a3-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ac5a3-126">Remarks</span></span>

<span data-ttu-id="ac5a3-127">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="ac5a3-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="ac5a3-128">Il chiamante inizia la sequenza di enumerazione chiamando la funzione [BeginMethodEnumeration](beginmethodenumeration.md) `WBEM_S_NO_MORE_DATA`, quindi chiama la funzione [NextMethod] finché la funzione non restituisce .</span><span class="sxs-lookup"><span data-stu-id="ac5a3-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="ac5a3-129">Facoltativamente, il chiamante completa la sequenza chiamando [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ac5a3-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="ac5a3-130">Il chiamante può terminare l'enumerazione in anticipo chiamando [EndMethodEnumeration](endmethodenumeration.md) in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ac5a3-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="ac5a3-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac5a3-131">Example</span></span>

<span data-ttu-id="ac5a3-132">Per un esempio in C, vedere il metodo [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="ac5a3-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac5a3-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac5a3-133">Requirements</span></span>  
 <span data-ttu-id="ac5a3-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac5a3-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac5a3-135">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ac5a3-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ac5a3-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ac5a3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5a3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac5a3-137">See also</span></span>

- [<span data-ttu-id="ac5a3-138">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ac5a3-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
