---
title: InheritsFrom function (Unmanaged API Reference)
description: La funzione InheritsFrom determina se una classe o un'istanza deriva da una particolare classe padre.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c735c01c45beda8a1ba988a5c580e6b04ae46312
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174940"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="120ae-103">Funzione InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="120ae-103">InheritsFrom function</span></span>
<span data-ttu-id="120ae-104">Determina se la classe o l'istanza corrente deriva da una classe padre specificata.</span><span class="sxs-lookup"><span data-stu-id="120ae-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="120ae-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="120ae-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a><span data-ttu-id="120ae-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="120ae-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="120ae-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="120ae-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="120ae-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="120ae-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="120ae-109">[in] Nome della classe.</span><span class="sxs-lookup"><span data-stu-id="120ae-109">[in] The name of the class.</span></span> <span data-ttu-id="120ae-110">`wszAncestor`deve puntare a `LPCWSTR`un valore valido .</span><span class="sxs-lookup"><span data-stu-id="120ae-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="120ae-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="120ae-111">Return value</span></span>

<span data-ttu-id="120ae-112">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="120ae-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="120ae-113">Costante</span><span class="sxs-lookup"><span data-stu-id="120ae-113">Constant</span></span>  |<span data-ttu-id="120ae-114">valore</span><span class="sxs-lookup"><span data-stu-id="120ae-114">Value</span></span>  |<span data-ttu-id="120ae-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="120ae-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="120ae-116">0</span><span class="sxs-lookup"><span data-stu-id="120ae-116">0</span></span> | <span data-ttu-id="120ae-117">L'oggetto corrente `wszAncestor`eredita da .</span><span class="sxs-lookup"><span data-stu-id="120ae-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="120ae-118">1</span><span class="sxs-lookup"><span data-stu-id="120ae-118">1</span></span> | <span data-ttu-id="120ae-119">L'oggetto corrente non `wszAncestor`eredita da .</span><span class="sxs-lookup"><span data-stu-id="120ae-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="120ae-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="120ae-120">0x80041008</span></span> | <span data-ttu-id="120ae-121">`wszAncestor` è `null`.</span><span class="sxs-lookup"><span data-stu-id="120ae-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="120ae-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="120ae-122">Remarks</span></span>

<span data-ttu-id="120ae-123">Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .</span><span class="sxs-lookup"><span data-stu-id="120ae-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="120ae-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="120ae-124">Requirements</span></span>  
 <span data-ttu-id="120ae-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120ae-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120ae-126">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="120ae-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="120ae-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="120ae-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120ae-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="120ae-128">See also</span></span>

- [<span data-ttu-id="120ae-129">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="120ae-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
