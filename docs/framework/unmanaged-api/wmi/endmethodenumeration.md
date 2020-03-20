---
title: EndMethodEnumeration function (Unmanaged API Reference)
description: La funzione EndMethodEnumeration termina una sequenza di enumerazione del metodo.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175005"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="9064d-103">Funzione EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="9064d-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="9064d-104">Termina una sequenza di enumerazione avviata con una chiamata alla [funzione BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="9064d-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9064d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9064d-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="9064d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9064d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9064d-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9064d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9064d-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="9064d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="9064d-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9064d-109">Return value</span></span>

<span data-ttu-id="9064d-110">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="9064d-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9064d-111">Costante</span><span class="sxs-lookup"><span data-stu-id="9064d-111">Constant</span></span>  |<span data-ttu-id="9064d-112">valore</span><span class="sxs-lookup"><span data-stu-id="9064d-112">Value</span></span>  |<span data-ttu-id="9064d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9064d-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="9064d-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="9064d-114">0x8004101d</span></span> | <span data-ttu-id="9064d-115">An internal error occurred.</span><span class="sxs-lookup"><span data-stu-id="9064d-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9064d-116">0</span><span class="sxs-lookup"><span data-stu-id="9064d-116">0</span></span> | <span data-ttu-id="9064d-117">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9064d-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9064d-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9064d-118">Remarks</span></span>

<span data-ttu-id="9064d-119">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) .</span><span class="sxs-lookup"><span data-stu-id="9064d-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="9064d-120">Il chiamante inizia la sequenza di enumerazione utilizzando la funzione `WBEM_S_NO_MORE_DATA` [BeginMethodEnumeration](beginmethodenumeration.md), quindi chiama la funzione [NextMethod](nextmethod.md )finché il metodo non restituisce .</span><span class="sxs-lookup"><span data-stu-id="9064d-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="9064d-121">Facoltativamente, il chiamante completa `EndMethodEnumeration`la sequenza chiamando .</span><span class="sxs-lookup"><span data-stu-id="9064d-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="9064d-122">Il chiamante può terminare `EndMethodEnumeration` l'enumerazione in anticipo chiamando in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="9064d-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="9064d-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9064d-123">Requirements</span></span>  
 <span data-ttu-id="9064d-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9064d-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9064d-125">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9064d-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9064d-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9064d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9064d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9064d-127">See also</span></span>

- [<span data-ttu-id="9064d-128">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="9064d-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
