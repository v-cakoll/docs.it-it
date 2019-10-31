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
ms.openlocfilehash: f72e6b1c356077a94b141e40d6efe485e77e7a9e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120186"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="ada50-103">SpawnDerivedClass (funzione)</span><span class="sxs-lookup"><span data-stu-id="ada50-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="ada50-104">Crea un nuovo oggetto di classe derivata da un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="ada50-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ada50-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ada50-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="ada50-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ada50-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ada50-107">in Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ada50-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ada50-108">in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="ada50-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="ada50-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="ada50-109">[in] Reserved.</span></span> <span data-ttu-id="ada50-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="ada50-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="ada50-111">out Riceve il puntatore al nuovo oggetto definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="ada50-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="ada50-112">Se si verifica un errore, non viene restituito un nuovo oggetto e `ppNewClass` viene lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="ada50-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="ada50-113">Il valore non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="ada50-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ada50-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ada50-114">Return value</span></span>

<span data-ttu-id="ada50-115">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ada50-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ada50-116">Costante</span><span class="sxs-lookup"><span data-stu-id="ada50-116">Constant</span></span>  |<span data-ttu-id="ada50-117">Value</span><span class="sxs-lookup"><span data-stu-id="ada50-117">Value</span></span>  |<span data-ttu-id="ada50-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ada50-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ada50-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ada50-119">0x80041001</span></span> | <span data-ttu-id="ada50-120">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="ada50-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="ada50-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="ada50-121">0x80041016</span></span> | <span data-ttu-id="ada50-122">È stata richiesta un'operazione non valida, ad esempio la generazione di una classe da un'istanza.</span><span class="sxs-lookup"><span data-stu-id="ada50-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="ada50-123">La classe di origine non è stata definita completamente o è stata registrata con la gestione di Windows, pertanto non è consentita una nuova classe derivata.</span><span class="sxs-lookup"><span data-stu-id="ada50-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ada50-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ada50-124">0x80041006</span></span> | <span data-ttu-id="ada50-125">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="ada50-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ada50-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ada50-126">0x80041008</span></span> | <span data-ttu-id="ada50-127">`ppNewClass` è `null`.</span><span class="sxs-lookup"><span data-stu-id="ada50-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ada50-128">0</span><span class="sxs-lookup"><span data-stu-id="ada50-128">0</span></span> | <span data-ttu-id="ada50-129">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ada50-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ada50-130">Note</span><span class="sxs-lookup"><span data-stu-id="ada50-130">Remarks</span></span>

<span data-ttu-id="ada50-131">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="ada50-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="ada50-132">`ptr` deve essere una definizione di classe che diventa la classe padre dell'oggetto generato.</span><span class="sxs-lookup"><span data-stu-id="ada50-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="ada50-133">L'oggetto restituito diventa una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="ada50-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="ada50-134">Il nuovo oggetto restituito in `ppNewClass` diventa automaticamente una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="ada50-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="ada50-135">Non è possibile eseguire l'override di questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="ada50-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="ada50-136">Non esiste un altro metodo con cui è possibile creare sottoclassi (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="ada50-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="ada50-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ada50-137">Requirements</span></span>  
 <span data-ttu-id="ada50-138">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ada50-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ada50-139">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ada50-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ada50-140">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ada50-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada50-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ada50-141">See also</span></span>

- [<span data-ttu-id="ada50-142">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ada50-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
