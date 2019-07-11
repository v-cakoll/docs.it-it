---
title: Funzione SpawnDerivedClass (riferimenti alle API non gestite)
description: La funzione SpawnDerivedClass crea un nuovo oggetto che deriva da un oggetto.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f05f349699b28262c1628cadc6e9a0fb0a3459c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783095"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="d1b96-103">SpawnDerivedClass (funzione)</span><span class="sxs-lookup"><span data-stu-id="d1b96-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="d1b96-104">Crea un nuovo oggetto di classe derivata da un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="d1b96-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d1b96-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1b96-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="d1b96-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d1b96-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d1b96-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="d1b96-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d1b96-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="d1b96-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="d1b96-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="d1b96-109">[in] Reserved.</span></span> <span data-ttu-id="d1b96-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="d1b96-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="d1b96-111">[out] Riceve il puntatore al nuovo oggetto di definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="d1b96-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="d1b96-112">Se si verifica un errore, non è un nuovo oggetto restituito, e `ppNewClass` è invariata a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d1b96-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="d1b96-113">Il valore non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="d1b96-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="d1b96-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d1b96-114">Return value</span></span>

<span data-ttu-id="d1b96-115">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="d1b96-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d1b96-116">Costante</span><span class="sxs-lookup"><span data-stu-id="d1b96-116">Constant</span></span>  |<span data-ttu-id="d1b96-117">Value</span><span class="sxs-lookup"><span data-stu-id="d1b96-117">Value</span></span>  |<span data-ttu-id="d1b96-118">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d1b96-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="d1b96-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d1b96-119">0x80041001</span></span> | <span data-ttu-id="d1b96-120">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="d1b96-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="d1b96-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="d1b96-121">0x80041016</span></span> | <span data-ttu-id="d1b96-122">È stata richiesta un'operazione non è valida, come la generazione di una classe da un'istanza.</span><span class="sxs-lookup"><span data-stu-id="d1b96-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="d1b96-123">La classe di origine non completamente definita o registrata con la gestione di Windows, in modo che non è consentita una nuova classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d1b96-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d1b96-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d1b96-124">0x80041006</span></span> | <span data-ttu-id="d1b96-125">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d1b96-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d1b96-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d1b96-126">0x80041008</span></span> | <span data-ttu-id="d1b96-127">`ppNewClass` è `null`.</span><span class="sxs-lookup"><span data-stu-id="d1b96-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d1b96-128">0</span><span class="sxs-lookup"><span data-stu-id="d1b96-128">0</span></span> | <span data-ttu-id="d1b96-129">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d1b96-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d1b96-130">Note</span><span class="sxs-lookup"><span data-stu-id="d1b96-130">Remarks</span></span>

<span data-ttu-id="d1b96-131">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d1b96-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="d1b96-132">`ptr` deve essere una definizione di classe che diventa la classe padre dell'oggetto generato.</span><span class="sxs-lookup"><span data-stu-id="d1b96-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="d1b96-133">L'oggetto restituito diventa una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="d1b96-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="d1b96-134">Il nuovo oggetto restituito in `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="d1b96-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="d1b96-135">Impossibile eseguire l'override di questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="d1b96-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="d1b96-136">Non vi è alcun altro metodo per cui è possono creare sottoclassi (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="d1b96-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1b96-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d1b96-137">Requirements</span></span>  
 <span data-ttu-id="d1b96-138">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1b96-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1b96-139">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d1b96-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d1b96-140">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d1b96-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b96-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1b96-141">See also</span></span>

- [<span data-ttu-id="d1b96-142">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="d1b96-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
