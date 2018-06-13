---
title: Funzione InheritsFrom (riferimenti alle API non gestite)
description: La funzione InheritsFrom determina se una classe o istanza deriva da una classe particolare padre.
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
ms.openlocfilehash: 87a1c1ee44d3b192747bd785f538c0332300ff50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461415"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="cd819-103">InheritsFrom (funzione)</span><span class="sxs-lookup"><span data-stu-id="cd819-103">InheritsFrom function</span></span>
<span data-ttu-id="cd819-104">Determina se la classe o istanza corrente deriva da una classe padre specificata.</span><span class="sxs-lookup"><span data-stu-id="cd819-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="cd819-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd819-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="cd819-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd819-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="cd819-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="cd819-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="cd819-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="cd819-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="cd819-109">[in] Il nome della classe.</span><span class="sxs-lookup"><span data-stu-id="cd819-109">[in] The name of the class.</span></span> <span data-ttu-id="cd819-110">`wszAncestor` deve puntare a un valore valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="cd819-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="cd819-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cd819-111">Return value</span></span>

<span data-ttu-id="cd819-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="cd819-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cd819-113">Costante</span><span class="sxs-lookup"><span data-stu-id="cd819-113">Constant</span></span>  |<span data-ttu-id="cd819-114">Valore</span><span class="sxs-lookup"><span data-stu-id="cd819-114">Value</span></span>  |<span data-ttu-id="cd819-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd819-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cd819-116">0</span><span class="sxs-lookup"><span data-stu-id="cd819-116">0</span></span> | <span data-ttu-id="cd819-117">L'oggetto corrente eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="cd819-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="cd819-118">1</span><span class="sxs-lookup"><span data-stu-id="cd819-118">1</span></span> | <span data-ttu-id="cd819-119">L'oggetto corrente non eredita da `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="cd819-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cd819-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cd819-120">0x80041008</span></span> | <span data-ttu-id="cd819-121">`wszAncestor` è `null`.</span><span class="sxs-lookup"><span data-stu-id="cd819-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="cd819-122">Note</span><span class="sxs-lookup"><span data-stu-id="cd819-122">Remarks</span></span>

<span data-ttu-id="cd819-123">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="cd819-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd819-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd819-124">Requirements</span></span>  
 <span data-ttu-id="cd819-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd819-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd819-126">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cd819-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="cd819-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cd819-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd819-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd819-128">See also</span></span>  
[<span data-ttu-id="cd819-129">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="cd819-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
