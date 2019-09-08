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
ms.openlocfilehash: 529905bd9286520a8e09479bfc95ef0b614f53e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798215"
---
# <a name="spawninstance-function"></a><span data-ttu-id="f30e7-103">SpawnInstance (funzione)</span><span class="sxs-lookup"><span data-stu-id="f30e7-103">SpawnInstance function</span></span>
<span data-ttu-id="f30e7-104">Crea una nuova istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="f30e7-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f30e7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f30e7-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="f30e7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f30e7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f30e7-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="f30e7-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f30e7-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="f30e7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f30e7-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="f30e7-109">[in] Reserved.</span></span> <span data-ttu-id="f30e7-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="f30e7-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="f30e7-111">out Riceve il puntatore alla nuova istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="f30e7-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="f30e7-112">Se si verifica un errore, non viene restituito un nuovo oggetto e `ppNewInstance` viene lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="f30e7-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="f30e7-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f30e7-113">Return value</span></span>

<span data-ttu-id="f30e7-114">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="f30e7-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f30e7-115">Costante</span><span class="sxs-lookup"><span data-stu-id="f30e7-115">Constant</span></span>  |<span data-ttu-id="f30e7-116">Value</span><span class="sxs-lookup"><span data-stu-id="f30e7-116">Value</span></span>  |<span data-ttu-id="f30e7-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f30e7-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="f30e7-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="f30e7-118">0x80041020</span></span> | <span data-ttu-id="f30e7-119">`ptr`non è una definizione di classe valida e non può generare nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="f30e7-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="f30e7-120">È incompleto o non è stato registrato con gestione Windows chiamando [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="f30e7-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f30e7-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f30e7-121">0x80041006</span></span> | <span data-ttu-id="f30e7-122">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="f30e7-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f30e7-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f30e7-123">0x80041008</span></span> | <span data-ttu-id="f30e7-124">`ppNewClass` è `null`.</span><span class="sxs-lookup"><span data-stu-id="f30e7-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f30e7-125">0</span><span class="sxs-lookup"><span data-stu-id="f30e7-125">0</span></span> | <span data-ttu-id="f30e7-126">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="f30e7-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f30e7-127">Note</span><span class="sxs-lookup"><span data-stu-id="f30e7-127">Remarks</span></span>

<span data-ttu-id="f30e7-128">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) .</span><span class="sxs-lookup"><span data-stu-id="f30e7-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="f30e7-129">`ptr`deve essere una definizione di classe ottenuta dalla gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="f30e7-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="f30e7-130">Si noti che la generazione di un'istanza da un'istanza è supportata, ma l'istanza restituita è vuota. Usare quindi questa definizione di classe per creare nuove istanze.</span><span class="sxs-lookup"><span data-stu-id="f30e7-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="f30e7-131">Una chiamata alla funzione [PutInstanceWmi](putinstancewmi.md) è obbligatoria se si intende scrivere l'istanza di in gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="f30e7-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="f30e7-132">Il nuovo oggetto restituito in `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="f30e7-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="f30e7-133">Non è possibile eseguire l'override di questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="f30e7-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="f30e7-134">Non esiste un altro metodo con cui è possibile creare sottoclassi (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="f30e7-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="f30e7-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f30e7-135">Requirements</span></span>  
 <span data-ttu-id="f30e7-136">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f30e7-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f30e7-137">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f30e7-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f30e7-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f30e7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30e7-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f30e7-139">See also</span></span>

- [<span data-ttu-id="f30e7-140">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="f30e7-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
