---
title: Funzione SpawnDerivedClass (riferimenti alle API non gestite)
description: La funzione SpawnDerivedClass crea un nuovo oggetto che deriva da un oggetto.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnDerivedClass
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnDerivedClass
helpviewer_keywords: SpawnDerivedClass function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16f9a762c87e1e181202739b70cd978a80864f04
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="94289-103">SpawnDerivedClass (funzione)</span><span class="sxs-lookup"><span data-stu-id="94289-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="94289-104">Crea un oggetto appena derivata da un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="94289-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="94289-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94289-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="94289-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="94289-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="94289-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="94289-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="94289-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="94289-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="94289-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="94289-109">[in] Reserved.</span></span> <span data-ttu-id="94289-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="94289-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="94289-111">[out] Riceve il puntatore al nuovo oggetto di definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="94289-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="94289-112">Se si verifica un errore, non è un nuovo oggetto restituito, e `ppNewClass` è invariato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="94289-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="94289-113">Il valore non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="94289-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="94289-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="94289-114">Return value</span></span>

<span data-ttu-id="94289-115">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="94289-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="94289-116">Costante</span><span class="sxs-lookup"><span data-stu-id="94289-116">Constant</span></span>  |<span data-ttu-id="94289-117">Valore</span><span class="sxs-lookup"><span data-stu-id="94289-117">Value</span></span>  |<span data-ttu-id="94289-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94289-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="94289-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="94289-119">0x80041001</span></span> | <span data-ttu-id="94289-120">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="94289-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="94289-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="94289-121">0x80041016</span></span> | <span data-ttu-id="94289-122">Un'operazione non valida, ad esempio l'installazione di una classe da un'istanza, è stato richiesto.</span><span class="sxs-lookup"><span data-stu-id="94289-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="94289-123">La classe di origine non è completamente definita o registrata con gestione di Windows, pertanto non è consentita una nuova classe derivata.</span><span class="sxs-lookup"><span data-stu-id="94289-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="94289-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="94289-124">0x80041006</span></span> | <span data-ttu-id="94289-125">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="94289-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="94289-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="94289-126">0x80041008</span></span> | <span data-ttu-id="94289-127">`ppNewClass` è `null`.</span><span class="sxs-lookup"><span data-stu-id="94289-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="94289-128">0</span><span class="sxs-lookup"><span data-stu-id="94289-128">0</span></span> | <span data-ttu-id="94289-129">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="94289-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="94289-130">Note</span><span class="sxs-lookup"><span data-stu-id="94289-130">Remarks</span></span>

<span data-ttu-id="94289-131">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="94289-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="94289-132">`ptr`deve essere una definizione di classe che diventa la classe padre dell'oggetto generato.</span><span class="sxs-lookup"><span data-stu-id="94289-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="94289-133">L'oggetto restituito diventa una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="94289-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="94289-134">Il nuovo oggetto restituito `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="94289-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="94289-135">Impossibile eseguire l'override di questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="94289-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="94289-136">Non vi è alcun altro metodo per cui è possono creare le sottoclassi (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="94289-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="94289-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94289-137">Requirements</span></span>  
 <span data-ttu-id="94289-138">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94289-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94289-139">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="94289-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="94289-140">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="94289-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94289-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94289-141">See also</span></span>  
[<span data-ttu-id="94289-142">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="94289-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
