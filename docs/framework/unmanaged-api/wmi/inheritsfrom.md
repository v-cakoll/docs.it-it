---
title: Funzione InheritsFrom (riferimenti alle API non gestite)
description: La funzione InheritsFrom determina se una classe o un'istanza deriva da una classe padre specifica.
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
ms.openlocfilehash: 0c32c54ec56ea0fe4f4039ca6438a91338edbadb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798446"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="ebced-103">InheritsFrom (funzione)</span><span class="sxs-lookup"><span data-stu-id="ebced-103">InheritsFrom function</span></span>
<span data-ttu-id="ebced-104">Determina se la classe o l'istanza corrente deriva da una classe padre specificata.</span><span class="sxs-lookup"><span data-stu-id="ebced-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ebced-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebced-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="ebced-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ebced-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ebced-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ebced-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ebced-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="ebced-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="ebced-109">in Nome della classe.</span><span class="sxs-lookup"><span data-stu-id="ebced-109">[in] The name of the class.</span></span> <span data-ttu-id="ebced-110">`wszAncestor`deve puntare a un oggetto `LPCWSTR`valido.</span><span class="sxs-lookup"><span data-stu-id="ebced-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ebced-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ebced-111">Return value</span></span>

<span data-ttu-id="ebced-112">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ebced-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ebced-113">Costante</span><span class="sxs-lookup"><span data-stu-id="ebced-113">Constant</span></span>  |<span data-ttu-id="ebced-114">Valore</span><span class="sxs-lookup"><span data-stu-id="ebced-114">Value</span></span>  |<span data-ttu-id="ebced-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ebced-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ebced-116">0</span><span class="sxs-lookup"><span data-stu-id="ebced-116">0</span></span> | <span data-ttu-id="ebced-117">L'oggetto corrente eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="ebced-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="ebced-118">1</span><span class="sxs-lookup"><span data-stu-id="ebced-118">1</span></span> | <span data-ttu-id="ebced-119">L'oggetto corrente non eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="ebced-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ebced-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ebced-120">0x80041008</span></span> | <span data-ttu-id="ebced-121">`wszAncestor` è `null`.</span><span class="sxs-lookup"><span data-stu-id="ebced-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ebced-122">Note</span><span class="sxs-lookup"><span data-stu-id="ebced-122">Remarks</span></span>

<span data-ttu-id="ebced-123">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .</span><span class="sxs-lookup"><span data-stu-id="ebced-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebced-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebced-124">Requirements</span></span>  
 <span data-ttu-id="ebced-125">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebced-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebced-126">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ebced-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ebced-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ebced-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebced-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebced-128">See also</span></span>

- [<span data-ttu-id="ebced-129">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ebced-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
