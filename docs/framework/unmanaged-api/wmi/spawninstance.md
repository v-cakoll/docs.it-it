---
title: Funzione SpawnInstance (riferimenti alle API non gestite)
description: La funzione SpawnInstance crea una nuova istanza della classe.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnInstance
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnInstance
helpviewer_keywords: SpawnInstance function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 65050772e2f933583506b6612c32c6060f1d20df
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="spawninstance-function"></a><span data-ttu-id="28b4d-103">Funzione SpawnInstance</span><span class="sxs-lookup"><span data-stu-id="28b4d-103">SpawnInstance function</span></span>
<span data-ttu-id="28b4d-104">Crea una nuova istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="28b4d-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="28b4d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28b4d-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="28b4d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="28b4d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="28b4d-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="28b4d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="28b4d-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="28b4d-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="28b4d-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="28b4d-109">[in] Reserved.</span></span> <span data-ttu-id="28b4d-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="28b4d-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="28b4d-111">[out] Riceve il puntatore a una nuova istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="28b4d-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="28b4d-112">Se si verifica un errore, non è un nuovo oggetto restituito, e `ppNewInstance` è invariato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="28b4d-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="28b4d-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="28b4d-113">Return value</span></span>

<span data-ttu-id="28b4d-114">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="28b4d-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="28b4d-115">Costante</span><span class="sxs-lookup"><span data-stu-id="28b4d-115">Constant</span></span>  |<span data-ttu-id="28b4d-116">Valore</span><span class="sxs-lookup"><span data-stu-id="28b4d-116">Value</span></span>  |<span data-ttu-id="28b4d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28b4d-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="28b4d-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="28b4d-118">0x80041020</span></span> | <span data-ttu-id="28b4d-119">`ptr`non è una definizione di classe valido e non può generare nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="28b4d-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="28b4d-120">È incompleto o non è stato registrato con WMI chiamando [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="28b4d-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="28b4d-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="28b4d-121">0x80041006</span></span> | <span data-ttu-id="28b4d-122">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="28b4d-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="28b4d-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="28b4d-123">0x80041008</span></span> | <span data-ttu-id="28b4d-124">`ppNewClass` è `null`.</span><span class="sxs-lookup"><span data-stu-id="28b4d-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="28b4d-125">0</span><span class="sxs-lookup"><span data-stu-id="28b4d-125">0</span></span> | <span data-ttu-id="28b4d-126">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="28b4d-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="28b4d-127">Note</span><span class="sxs-lookup"><span data-stu-id="28b4d-127">Remarks</span></span>

<span data-ttu-id="28b4d-128">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject:: SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="28b4d-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="28b4d-129">`ptr`deve essere una definizione di classe ottenuta dalla gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="28b4d-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="28b4d-130">Si noti che la generazione di un'istanza da un'istanza è supportata ma l'istanza restituita è vuota. È quindi possibile utilizzare la definizione di classe per creare nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="28b4d-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="28b4d-131">Una chiamata al [PutInstanceWmi](putinstancewmi.md) è la funzione se si prevede di scrivere l'istanza di gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="28b4d-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="28b4d-132">Il nuovo oggetto restituito `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="28b4d-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="28b4d-133">Impossibile eseguire l'override di questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="28b4d-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="28b4d-134">Non vi è alcun altro metodo per cui è possono creare le sottoclassi (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="28b4d-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="28b4d-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28b4d-135">Requirements</span></span>  
 <span data-ttu-id="28b4d-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28b4d-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28b4d-137">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="28b4d-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="28b4d-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="28b4d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b4d-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28b4d-139">See also</span></span>  
[<span data-ttu-id="28b4d-140">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="28b4d-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
