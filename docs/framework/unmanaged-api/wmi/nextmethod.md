---
title: Funzione NextMethod (riferimenti alle API non gestite)
description: La funzione NextMethod recupera il prossimo metodo in un'enumerazione.
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
ms.openlocfilehash: 4a730947b0c962d801975917cdf752136e7221c4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746484"
---
# <a name="nextmethod-function"></a><span data-ttu-id="3e663-103">NextMethod (funzione)</span><span class="sxs-lookup"><span data-stu-id="3e663-103">NextMethod function</span></span>
<span data-ttu-id="3e663-104">Recupera il prossimo metodo in un'enumerazione che inizia con una chiamata a [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3e663-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3e663-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e663-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="3e663-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3e663-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3e663-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="3e663-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3e663-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="3e663-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="3e663-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="3e663-109">[in] Reserved.</span></span> <span data-ttu-id="3e663-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="3e663-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="3e663-111">[out] Un puntatore che punta a `null` prima della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e663-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="3e663-112">Quando la funzione restituisce, l'indirizzo di un nuovo `BSTR` che contiene il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="3e663-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="3e663-113">[out] Un puntatore che riceve un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene il `in` parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="3e663-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="3e663-114">[out] Un puntatore che riceve un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) che contiene il `out` parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="3e663-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="3e663-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3e663-115">Return value</span></span>

<span data-ttu-id="3e663-116">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="3e663-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3e663-117">Costante</span><span class="sxs-lookup"><span data-stu-id="3e663-117">Constant</span></span>  |<span data-ttu-id="3e663-118">Value</span><span class="sxs-lookup"><span data-stu-id="3e663-118">Value</span></span>  |<span data-ttu-id="3e663-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e663-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="3e663-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="3e663-120">0x8004101d</span></span> | <span data-ttu-id="3e663-121">Si è verificato alcun chiamata per il [ `BeginEnumeration` ](beginenumeration.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="3e663-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3e663-122">0</span><span class="sxs-lookup"><span data-stu-id="3e663-122">0</span></span> | <span data-ttu-id="3e663-123">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3e663-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="3e663-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="3e663-124">0x40005</span></span> | <span data-ttu-id="3e663-125">Non esistono altre proprietà dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3e663-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3e663-126">Note</span><span class="sxs-lookup"><span data-stu-id="3e663-126">Remarks</span></span>

<span data-ttu-id="3e663-127">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3e663-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="3e663-128">Il chiamante avvia la sequenza di enumerazione chiamando il [BeginMethodEnumeration](beginmethodenumeration.md) funzione e quindi chiama la funzione [NextMethod] fino a quando la funzione restituisce `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="3e663-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="3e663-129">Facoltativamente, il chiamante termina la sequenza chiamando [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3e663-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="3e663-130">Il chiamante può terminare l'enumerazione all'inizio chiamando [EndMethodEnumeration](endmethodenumeration.md) in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3e663-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="3e663-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e663-131">Example</span></span>

<span data-ttu-id="3e663-132">Per un esempio di C++, vedere la [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3e663-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e663-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e663-133">Requirements</span></span>  
 <span data-ttu-id="3e663-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e663-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e663-135">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3e663-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3e663-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e663-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e663-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e663-137">See also</span></span>

- [<span data-ttu-id="3e663-138">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="3e663-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
