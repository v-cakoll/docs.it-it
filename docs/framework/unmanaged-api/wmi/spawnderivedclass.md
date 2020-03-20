---
title: Funzione SpawnDerivedClass (riferimenti all'API non gestita)
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
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174849"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="baf34-103">Funzione SpawnDerivedClass</span><span class="sxs-lookup"><span data-stu-id="baf34-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="baf34-104">Crea un nuovo oggetto di classe derivata da un oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="baf34-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="baf34-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="baf34-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="baf34-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="baf34-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="baf34-107">[in] Questo parametro non viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="baf34-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="baf34-108">[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="baf34-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="baf34-109">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="baf34-109">[in] Reserved.</span></span> <span data-ttu-id="baf34-110">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="baf34-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="baf34-111">[fuori] Riceve il puntatore al nuovo oggetto definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="baf34-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="baf34-112">Se si verifica un errore, un nuovo `ppNewClass` oggetto non viene restituito e viene lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="baf34-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="baf34-113">Il suo `null`valore non può essere .</span><span class="sxs-lookup"><span data-stu-id="baf34-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="baf34-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="baf34-114">Return value</span></span>

<span data-ttu-id="baf34-115">I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span><span class="sxs-lookup"><span data-stu-id="baf34-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="baf34-116">Costante</span><span class="sxs-lookup"><span data-stu-id="baf34-116">Constant</span></span>  |<span data-ttu-id="baf34-117">valore</span><span class="sxs-lookup"><span data-stu-id="baf34-117">Value</span></span>  |<span data-ttu-id="baf34-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="baf34-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="baf34-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="baf34-119">0x80041001</span></span> | <span data-ttu-id="baf34-120">C'è stato un fallimento generale.</span><span class="sxs-lookup"><span data-stu-id="baf34-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="baf34-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="baf34-121">0x80041016</span></span> | <span data-ttu-id="baf34-122">È stata richiesta un'operazione non valida, ad esempio la generazione di una classe da un'istanza.</span><span class="sxs-lookup"><span data-stu-id="baf34-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="baf34-123">La classe di origine non è stata completamente definita o registrata con Gestione Windows, pertanto non è consentita una nuova classe derivata.</span><span class="sxs-lookup"><span data-stu-id="baf34-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="baf34-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="baf34-124">0x80041006</span></span> | <span data-ttu-id="baf34-125">Memoria insufficiente per completare l’operazione.</span><span class="sxs-lookup"><span data-stu-id="baf34-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="baf34-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="baf34-126">0x80041008</span></span> | <span data-ttu-id="baf34-127">`ppNewClass` è `null`.</span><span class="sxs-lookup"><span data-stu-id="baf34-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="baf34-128">0</span><span class="sxs-lookup"><span data-stu-id="baf34-128">0</span></span> | <span data-ttu-id="baf34-129">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="baf34-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="baf34-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="baf34-130">Remarks</span></span>

<span data-ttu-id="baf34-131">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="baf34-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="baf34-132">`ptr`deve essere una definizione di classe che diventa la classe padre dell'oggetto generato.</span><span class="sxs-lookup"><span data-stu-id="baf34-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="baf34-133">L'oggetto restituito diventa una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="baf34-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="baf34-134">Il nuovo oggetto `ppNewClass` restituito in diventa automaticamente una sottoclasse dell'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="baf34-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="baf34-135">Questo comportamento non può essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="baf34-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="baf34-136">Non esiste un altro metodo con cui è possibile creare sottoclassi (classi derivate).</span><span class="sxs-lookup"><span data-stu-id="baf34-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="baf34-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="baf34-137">Requirements</span></span>  
 <span data-ttu-id="baf34-138">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf34-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf34-139">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="baf34-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="baf34-140">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="baf34-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf34-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baf34-141">See also</span></span>

- [<span data-ttu-id="baf34-142">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="baf34-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
