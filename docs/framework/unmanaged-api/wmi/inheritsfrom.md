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
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222107"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="5d6c4-103">InheritsFrom (funzione)</span><span class="sxs-lookup"><span data-stu-id="5d6c4-103">InheritsFrom function</span></span>
<span data-ttu-id="5d6c4-104">Determina se la classe o l'istanza corrente deriva da una classe padre specificata.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5d6c4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d6c4-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="5d6c4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d6c4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5d6c4-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5d6c4-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="5d6c4-109">[in] Il nome della classe.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-109">[in] The name of the class.</span></span> <span data-ttu-id="5d6c4-110">`wszAncestor` deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5d6c4-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5d6c4-111">Return value</span></span>

<span data-ttu-id="5d6c4-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="5d6c4-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5d6c4-113">Costante</span><span class="sxs-lookup"><span data-stu-id="5d6c4-113">Constant</span></span>  |<span data-ttu-id="5d6c4-114">Valore</span><span class="sxs-lookup"><span data-stu-id="5d6c4-114">Value</span></span>  |<span data-ttu-id="5d6c4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d6c4-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5d6c4-116">0</span><span class="sxs-lookup"><span data-stu-id="5d6c4-116">0</span></span> | <span data-ttu-id="5d6c4-117">L'oggetto corrente eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="5d6c4-118">1</span><span class="sxs-lookup"><span data-stu-id="5d6c4-118">1</span></span> | <span data-ttu-id="5d6c4-119">L'oggetto corrente non eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5d6c4-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5d6c4-120">0x80041008</span></span> | <span data-ttu-id="5d6c4-121">`wszAncestor` è `null`.</span><span class="sxs-lookup"><span data-stu-id="5d6c4-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="5d6c4-122">Note</span><span class="sxs-lookup"><span data-stu-id="5d6c4-122">Remarks</span></span>

<span data-ttu-id="5d6c4-123">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) (metodo).</span><span class="sxs-lookup"><span data-stu-id="5d6c4-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d6c4-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d6c4-124">Requirements</span></span>  
 <span data-ttu-id="5d6c4-125">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d6c4-126">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5d6c4-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5d6c4-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d6c4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6c4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d6c4-128">See also</span></span>  
[<span data-ttu-id="5d6c4-129">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="5d6c4-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
