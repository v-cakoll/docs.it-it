---
title: Funzione GetQualifierSet (riferimenti alle API non gestite)
description: La funzione GetQualifierSet recupera il qualificatore impostato per una classe o istanza.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetQualifierSet
helpviewer_keywords: GetQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 15d384003f3a18124a07d83a8308f4b8a5c6a31b
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getqualifierset-function"></a><span data-ttu-id="e0f0a-103">GetQualifierSet (funzione)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-103">GetQualifierSet function</span></span>
<span data-ttu-id="e0f0a-104">Recupera il qualificatore impostato per un'istanza della classe o una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e0f0a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0f0a-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="e0f0a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0f0a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e0f0a-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e0f0a-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="e0f0a-109">[out] Riceve il puntatore a interfaccia che consente l'accesso per i qualificatori dell'oggetto di classe.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="e0f0a-110">Il parametro `ppQualSet` non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="e0f0a-111">Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore viene lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="e0f0a-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e0f0a-112">Return value</span></span>

<span data-ttu-id="e0f0a-113">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="e0f0a-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e0f0a-114">Costante</span><span class="sxs-lookup"><span data-stu-id="e0f0a-114">Constant</span></span>  |<span data-ttu-id="e0f0a-115">Valore</span><span class="sxs-lookup"><span data-stu-id="e0f0a-115">Value</span></span>  |<span data-ttu-id="e0f0a-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0f0a-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e0f0a-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e0f0a-117">0x80041001</span></span> | <span data-ttu-id="e0f0a-118">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e0f0a-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e0f0a-119">0x80041002</span></span> | <span data-ttu-id="e0f0a-120">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e0f0a-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e0f0a-121">0x80041006</span></span> | <span data-ttu-id="e0f0a-122">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e0f0a-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e0f0a-123">0x80041008</span></span> | <span data-ttu-id="e0f0a-124">È un parametro `null`.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e0f0a-125">0</span><span class="sxs-lookup"><span data-stu-id="e0f0a-125">0</span></span> | <span data-ttu-id="e0f0a-126">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e0f0a-127">Note</span><span class="sxs-lookup"><span data-stu-id="e0f0a-127">Remarks</span></span>

<span data-ttu-id="e0f0a-128">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="e0f0a-129">Il [IWbemQualifierSet puntatore](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-129">The [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="e0f0a-130">Tali qualificatori aggiunti, modificati o eliminati vengono applicati per l'intera definizione di classe o istanza.</span><span class="sxs-lookup"><span data-stu-id="e0f0a-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0f0a-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0f0a-131">Requirements</span></span>  
<span data-ttu-id="e0f0a-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0f0a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0f0a-133">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e0f0a-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e0f0a-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e0f0a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f0a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0f0a-135">See also</span></span>  
[<span data-ttu-id="e0f0a-136">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="e0f0a-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
