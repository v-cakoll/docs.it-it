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
ms.openlocfilehash: 0d2af1b41f47a3906c0e573c104847aa3ff36cf8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158431"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="c8666-103">InheritsFrom (funzione)</span><span class="sxs-lookup"><span data-stu-id="c8666-103">InheritsFrom function</span></span>
<span data-ttu-id="c8666-104">Determina se la classe o l'istanza corrente deriva da una classe padre specificata.</span><span class="sxs-lookup"><span data-stu-id="c8666-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c8666-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8666-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="c8666-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8666-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c8666-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="c8666-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c8666-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="c8666-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="c8666-109">[in] Il nome della classe.</span><span class="sxs-lookup"><span data-stu-id="c8666-109">[in] The name of the class.</span></span> <span data-ttu-id="c8666-110">`wszAncestor` deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="c8666-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c8666-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8666-111">Return value</span></span>

<span data-ttu-id="c8666-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="c8666-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c8666-113">Costante</span><span class="sxs-lookup"><span data-stu-id="c8666-113">Constant</span></span>  |<span data-ttu-id="c8666-114">Value</span><span class="sxs-lookup"><span data-stu-id="c8666-114">Value</span></span>  |<span data-ttu-id="c8666-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8666-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c8666-116">0</span><span class="sxs-lookup"><span data-stu-id="c8666-116">0</span></span> | <span data-ttu-id="c8666-117">L'oggetto corrente eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="c8666-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="c8666-118">1</span><span class="sxs-lookup"><span data-stu-id="c8666-118">1</span></span> | <span data-ttu-id="c8666-119">L'oggetto corrente non eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="c8666-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c8666-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c8666-120">0x80041008</span></span> | <span data-ttu-id="c8666-121">`wszAncestor` è `null`.</span><span class="sxs-lookup"><span data-stu-id="c8666-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c8666-122">Note</span><span class="sxs-lookup"><span data-stu-id="c8666-122">Remarks</span></span>

<span data-ttu-id="c8666-123">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c8666-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c8666-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8666-124">Requirements</span></span>  
 <span data-ttu-id="c8666-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8666-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8666-126">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c8666-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c8666-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c8666-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8666-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8666-128">See also</span></span>

- [<span data-ttu-id="c8666-129">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c8666-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
