---
title: Funzione SpawnInstance (riferimenti alle API non gestite)
description: La funzione SpawnInstance crea una nuova istanza di una classe.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74eb098ee68f57477c8b9115db2bce60919f0b12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580213"
---
# <a name="spawninstance-function"></a><span data-ttu-id="f4a16-103">SpawnInstance (funzione)</span><span class="sxs-lookup"><span data-stu-id="f4a16-103">SpawnInstance function</span></span>
<span data-ttu-id="f4a16-104">Crea una nuova istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="f4a16-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f4a16-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4a16-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="f4a16-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4a16-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f4a16-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="f4a16-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f4a16-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="f4a16-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f4a16-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="f4a16-109">[in] Reserved.</span></span> <span data-ttu-id="f4a16-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="f4a16-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="f4a16-111">[out] Riceve il puntatore alla nuova istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="f4a16-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="f4a16-112">Se si verifica un errore, non è un nuovo oggetto restituito, e `ppNewInstance` è invariata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="f4a16-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="f4a16-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f4a16-113">Return value</span></span>

<span data-ttu-id="f4a16-114">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="f4a16-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f4a16-115">Costante</span><span class="sxs-lookup"><span data-stu-id="f4a16-115">Constant</span></span>  |<span data-ttu-id="f4a16-116">Value</span><span class="sxs-lookup"><span data-stu-id="f4a16-116">Value</span></span>  |<span data-ttu-id="f4a16-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4a16-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="f4a16-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="f4a16-118">0x80041020</span></span> | <span data-ttu-id="f4a16-119">`ptr` non è una definizione di classe valido e non è possibile distribuire le nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="f4a16-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="f4a16-120">È incompleto o non è stato registrato con la gestione di Windows tramite una chiamata [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="f4a16-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f4a16-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f4a16-121">0x80041006</span></span> | <span data-ttu-id="f4a16-122">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f4a16-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f4a16-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f4a16-123">0x80041008</span></span> | <span data-ttu-id="f4a16-124">`ppNewClass` è `null`.</span><span class="sxs-lookup"><span data-stu-id="f4a16-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f4a16-125">0</span><span class="sxs-lookup"><span data-stu-id="f4a16-125">0</span></span> | <span data-ttu-id="f4a16-126">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f4a16-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f4a16-127">Note</span><span class="sxs-lookup"><span data-stu-id="f4a16-127">Remarks</span></span>

<span data-ttu-id="f4a16-128">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) (metodo).</span><span class="sxs-lookup"><span data-stu-id="f4a16-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="f4a16-129">`ptr` deve essere una definizione di classe ottenuta dalla gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="f4a16-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="f4a16-130">Si noti che la generazione di un'istanza da un'istanza è supportata ma l'istanza restituita è vuota. È quindi possibile usare questa definizione di classe per creare nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="f4a16-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="f4a16-131">Una chiamata per il [PutInstanceWmi](putinstancewmi.md) funzione è obbligatorio se si prevede di scrivere l'istanza di gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="f4a16-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="f4a16-132">Il nuovo oggetto restituito in `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f4a16-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="f4a16-133">Impossibile eseguire l'override di questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="f4a16-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="f4a16-134">Non vi è alcun altro metodo per cui è possono creare sottoclassi (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="f4a16-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4a16-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4a16-135">Requirements</span></span>  
 <span data-ttu-id="f4a16-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4a16-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a16-137">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f4a16-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f4a16-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a16-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a16-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4a16-139">See also</span></span>
- [<span data-ttu-id="f4a16-140">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f4a16-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
