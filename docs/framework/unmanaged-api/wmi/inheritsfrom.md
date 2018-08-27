---
title: Funzione InheritsFrom (riferimenti alle API non gestite)
description: La funzione InheritsFrom determina se una classe o istanza deriva da una classe padre specifica.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4784e22d5a3eec031fbee00441958a62d66b52df
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930922"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="dae83-103">InheritsFrom (funzione)</span><span class="sxs-lookup"><span data-stu-id="dae83-103">InheritsFrom function</span></span>
<span data-ttu-id="dae83-104">Determina se l'istanza o la classe corrente deriva da una classe padre specificata.</span><span class="sxs-lookup"><span data-stu-id="dae83-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="dae83-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dae83-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="dae83-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="dae83-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="dae83-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="dae83-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="dae83-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="dae83-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="dae83-109">[in] Il nome della classe.</span><span class="sxs-lookup"><span data-stu-id="dae83-109">[in] The name of the class.</span></span> <span data-ttu-id="dae83-110">`wszAncestor` deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="dae83-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="dae83-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dae83-111">Return value</span></span>

<span data-ttu-id="dae83-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="dae83-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dae83-113">Costante</span><span class="sxs-lookup"><span data-stu-id="dae83-113">Constant</span></span>  |<span data-ttu-id="dae83-114">Valore</span><span class="sxs-lookup"><span data-stu-id="dae83-114">Value</span></span>  |<span data-ttu-id="dae83-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dae83-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="dae83-116">0</span><span class="sxs-lookup"><span data-stu-id="dae83-116">0</span></span> | <span data-ttu-id="dae83-117">L'oggetto corrente eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="dae83-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="dae83-118">1</span><span class="sxs-lookup"><span data-stu-id="dae83-118">1</span></span> | <span data-ttu-id="dae83-119">L'oggetto corrente non eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="dae83-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="dae83-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="dae83-120">0x80041008</span></span> | <span data-ttu-id="dae83-121">`wszAncestor` è `null`.</span><span class="sxs-lookup"><span data-stu-id="dae83-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="dae83-122">Note</span><span class="sxs-lookup"><span data-stu-id="dae83-122">Remarks</span></span>

<span data-ttu-id="dae83-123">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) (metodo).</span><span class="sxs-lookup"><span data-stu-id="dae83-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dae83-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dae83-124">Requirements</span></span>  
 <span data-ttu-id="dae83-125">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dae83-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dae83-126">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="dae83-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="dae83-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dae83-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae83-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dae83-128">See also</span></span>  
[<span data-ttu-id="dae83-129">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="dae83-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
