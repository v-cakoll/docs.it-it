---
title: Funzione clone (riferimenti alle API non gestite)
description: "La funzione Clone restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Clone
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Clone
helpviewer_keywords: Clone function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df6a089f66ddd6f8f9a2d5677dd8dd6917fcb719
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="clone-function"></a><span data-ttu-id="197bc-103">Clone (funzione)</span><span class="sxs-lookup"><span data-stu-id="197bc-103">Clone function</span></span>
<span data-ttu-id="197bc-104">Restituisce un nuovo oggetto che è un clone completo dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="197bc-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="197bc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="197bc-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="197bc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="197bc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="197bc-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="197bc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="197bc-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="197bc-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppCopy`  
<span data-ttu-id="197bc-109">[out] Un nuovo oggetto di un completamento unico di `ptr`.</span><span class="sxs-lookup"><span data-stu-id="197bc-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="197bc-110">Questo argomento non può essere `null` se riceve la copia dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="197bc-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="197bc-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="197bc-111">Return value</span></span>

<span data-ttu-id="197bc-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="197bc-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="197bc-113">Costante</span><span class="sxs-lookup"><span data-stu-id="197bc-113">Constant</span></span>  |<span data-ttu-id="197bc-114">Valore</span><span class="sxs-lookup"><span data-stu-id="197bc-114">Value</span></span>  |<span data-ttu-id="197bc-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="197bc-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="197bc-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="197bc-116">0x80041001</span></span> | <span data-ttu-id="197bc-117">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="197bc-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="197bc-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="197bc-118">0x80041008</span></span> | <span data-ttu-id="197bc-119">`null`è stato specificato come parametro, e non è consentito in questo caso.</span><span class="sxs-lookup"><span data-stu-id="197bc-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="197bc-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="197bc-120">0x80041006</span></span> | <span data-ttu-id="197bc-121">Memoria insufficiente è disponibile per clonare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="197bc-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="197bc-122">0</span><span class="sxs-lookup"><span data-stu-id="197bc-122">0</span></span> | <span data-ttu-id="197bc-123">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="197bc-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="197bc-124">Note</span><span class="sxs-lookup"><span data-stu-id="197bc-124">Remarks</span></span>

<span data-ttu-id="197bc-125">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="197bc-125">This function wraps a call to the [IWbemClassObject::Clone](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="197bc-126">L'oggetto clonato è un oggetto COM che presenta un conteggio dei riferimenti di 1.</span><span class="sxs-lookup"><span data-stu-id="197bc-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="197bc-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="197bc-127">Requirements</span></span>  
 <span data-ttu-id="197bc-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="197bc-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="197bc-129">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="197bc-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="197bc-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="197bc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="197bc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="197bc-131">See also</span></span>  
[<span data-ttu-id="197bc-132">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="197bc-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
