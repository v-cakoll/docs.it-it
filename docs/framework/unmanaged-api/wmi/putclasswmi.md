---
title: Funzione PutClassWmi (riferimenti alle API non gestite)
description: La funzione PutClassWmi crea una nuova classe o ne aggiorna uno esistente.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de08662a825a84f19a40863cf73481d89364ebd0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43733703"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="5df33-103">PutClassWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="5df33-103">PutClassWmi function</span></span>
<span data-ttu-id="5df33-104">Crea una nuova classe o ne aggiorna una esistente.</span><span class="sxs-lookup"><span data-stu-id="5df33-104">Creates a new class or updates an existing one.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5df33-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5df33-105">Syntax</span></span>  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="5df33-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5df33-106">Parameters</span></span>

`pObject`    
<span data-ttu-id="5df33-107">[in] Puntatore a una definizione di classe valido.</span><span class="sxs-lookup"><span data-stu-id="5df33-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="5df33-108">Deve essere inizializzata correttamente con tutti i valori proprietà obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5df33-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`   
<span data-ttu-id="5df33-109">[in] Una combinazione di flag che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="5df33-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="5df33-110">I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="5df33-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="5df33-111">Costante</span><span class="sxs-lookup"><span data-stu-id="5df33-111">Constant</span></span>  |<span data-ttu-id="5df33-112">Valore</span><span class="sxs-lookup"><span data-stu-id="5df33-112">Value</span></span>  |<span data-ttu-id="5df33-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5df33-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="5df33-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="5df33-114">0x20000</span></span> | <span data-ttu-id="5df33-115">Se set, WMI non archivia i qualificatori con la versione modificata.</span><span class="sxs-lookup"><span data-stu-id="5df33-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> </br> <span data-ttu-id="5df33-116">Se non impostato, si presuppone che non viene localizzato con questo oggetto e tutti i qualificatori vengono storedwith questa istanza.</span><span class="sxs-lookup"><span data-stu-id="5df33-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="5df33-117">0</span><span class="sxs-lookup"><span data-stu-id="5df33-117">0</span></span> | <span data-ttu-id="5df33-118">Creare la classe se non esiste o di sovrascriverlo se esiste già.</span><span class="sxs-lookup"><span data-stu-id="5df33-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="5df33-119">1</span><span class="sxs-lookup"><span data-stu-id="5df33-119">1</span></span> | <span data-ttu-id="5df33-120">Aggiornare la classe.</span><span class="sxs-lookup"><span data-stu-id="5df33-120">Update the class.</span></span> <span data-ttu-id="5df33-121">La classe deve esistere per la chiamata abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5df33-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="5df33-122">2</span><span class="sxs-lookup"><span data-stu-id="5df33-122">2</span></span> | <span data-ttu-id="5df33-123">Creare la classe.</span><span class="sxs-lookup"><span data-stu-id="5df33-123">Create the class.</span></span> <span data-ttu-id="5df33-124">La chiamata ha esito negativo se la classe esiste già.</span><span class="sxs-lookup"><span data-stu-id="5df33-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="5df33-125">0x10</span><span class="sxs-lookup"><span data-stu-id="5df33-125">0x10</span></span> | <span data-ttu-id="5df33-126">Il flag determina una chiamata semisincrona.</span><span class="sxs-lookup"><span data-stu-id="5df33-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="5df33-127">0x10000.</span><span class="sxs-lookup"><span data-stu-id="5df33-127">0x10000</span></span> | <span data-ttu-id="5df33-128">Push provider devono specificare questo flag quando si chiama `PutClassWmi` per indicare che questa classe è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="5df33-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="5df33-129">0</span><span class="sxs-lookup"><span data-stu-id="5df33-129">0</span></span> | <span data-ttu-id="5df33-130">Consente a una classe da aggiornare se sono presenti nessuna classe derivata e nessuna istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="5df33-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="5df33-131">Consente inoltre aggiornamenti in tutti i casi se la modifica è qualificatori irrilevanti, ad esempio il qualificatore di descrizione.</span><span class="sxs-lookup"><span data-stu-id="5df33-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="5df33-132">Se la classe dispone di istanze o le modifiche sono per qualificatori importanti, l'aggiornamento ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5df33-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="5df33-133">0x20</span><span class="sxs-lookup"><span data-stu-id="5df33-133">0x20</span></span> | <span data-ttu-id="5df33-134">Consente gli aggiornamenti delle classi anche se sono presenti le classi figlio, purché la modifica non generi conflitti con le classi figlio.</span><span class="sxs-lookup"><span data-stu-id="5df33-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="5df33-135">Ad esempio, questo flag consente una nuova proprietà da aggiungere alla classe di base che non è stata citata in precedenza in una qualsiasi delle classi figlio.</span><span class="sxs-lookup"><span data-stu-id="5df33-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="5df33-136">Se la classe dispone di istanze, l'aggiornamento ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5df33-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="5df33-137">0x40</span><span class="sxs-lookup"><span data-stu-id="5df33-137">0x40</span></span> | <span data-ttu-id="5df33-138">forza gli aggiornamenti delle classi quando sono presenti le classi figlio in conflitto.</span><span class="sxs-lookup"><span data-stu-id="5df33-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="5df33-139">Ad esempio, questo flag impone un aggiornamento se un qualificatore di classe è definito in una classe figlio e la classe di base tenta di aggiungere lo stesso qualificatore che entra in conflitto con graduazione uno esistente.</span><span class="sxs-lookup"><span data-stu-id="5df33-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with thte existing one.</span></span> <span data-ttu-id="5df33-140">In modalità di forza, tis conflitto viene risolto eliminando il qualificatore in conflitto nella classe figlio.</span><span class="sxs-lookup"><span data-stu-id="5df33-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`  
<span data-ttu-id="5df33-141">[in] In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="5df33-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="5df33-142">In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istanza che può essere utilizzata dal provider che fornisce le classi richieste.</span><span class="sxs-lookup"><span data-stu-id="5df33-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="5df33-143">[out] Se `null`, questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="5df33-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="5df33-144">Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la funzione restituisce immediatamente il `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="5df33-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="5df33-145">Il `ppCallResult` parametro riceve un puntatore a una nuova [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) oggetto.</span><span class="sxs-lookup"><span data-stu-id="5df33-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="5df33-146">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5df33-146">Return value</span></span>

<span data-ttu-id="5df33-147">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="5df33-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5df33-148">Costante</span><span class="sxs-lookup"><span data-stu-id="5df33-148">Constant</span></span>  |<span data-ttu-id="5df33-149">Valore</span><span class="sxs-lookup"><span data-stu-id="5df33-149">Value</span></span>  |<span data-ttu-id="5df33-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5df33-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="5df33-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="5df33-151">0x80041003</span></span> | <span data-ttu-id="5df33-152">L'utente dispone dell'autorizzazione per creare o modificare le classi.</span><span class="sxs-lookup"><span data-stu-id="5df33-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="5df33-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5df33-153">0x80041001</span></span> | <span data-ttu-id="5df33-154">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="5df33-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="5df33-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="5df33-155">0x80041010</span></span> | <span data-ttu-id="5df33-156">La classe specificata non è valida.</span><span class="sxs-lookup"><span data-stu-id="5df33-156">The specified class is not valid.</span></span> <span data-ttu-id="5df33-157">In genere, ciò indica che `pObject` specifica un oggetto istanza.</span><span class="sxs-lookup"><span data-stu-id="5df33-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5df33-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5df33-158">0x80041008</span></span> | <span data-ttu-id="5df33-159">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="5df33-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="5df33-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="5df33-160">0x80041016</span></span> | <span data-ttu-id="5df33-161">Il nome della classe specificata non è valido.</span><span class="sxs-lookup"><span data-stu-id="5df33-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="5df33-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="5df33-162">0x80041025</span></span> | <span data-ttu-id="5df33-163">È stato effettuato un tentativo per apportare una modifica che avrebbe reso invalida una sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="5df33-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="5df33-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="5df33-164">0x80041019</span></span> | <span data-ttu-id="5df33-165">Il `WBEM_FLAG_CREATE_ONLY` flag è stato specificato, ma la classe esiste già.</span><span class="sxs-lookup"><span data-stu-id="5df33-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="5df33-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5df33-166">0x80041002</span></span> | <span data-ttu-id="5df33-167">`WBEM_FLAG_UPDATE_ONLY` è stato specificato `lFlags`, la classe non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="5df33-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="5df33-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="5df33-168">0x80041020</span></span> | <span data-ttu-id="5df33-169">Le proprietà necessarie per le classi non di tutto configurate.</span><span class="sxs-lookup"><span data-stu-id="5df33-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5df33-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5df33-170">0x80041006</span></span> | <span data-ttu-id="5df33-171">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5df33-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="5df33-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="5df33-172">0x80041033</span></span> | <span data-ttu-id="5df33-173">WMI è stato probabilmente arresto e riavvio.</span><span class="sxs-lookup"><span data-stu-id="5df33-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="5df33-174">Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente.</span><span class="sxs-lookup"><span data-stu-id="5df33-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="5df33-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="5df33-175">0x80041015</span></span> | <span data-ttu-id="5df33-176">Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="5df33-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5df33-177">0</span><span class="sxs-lookup"><span data-stu-id="5df33-177">0</span></span> | <span data-ttu-id="5df33-178">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5df33-178">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5df33-179">Note</span><span class="sxs-lookup"><span data-stu-id="5df33-179">Remarks</span></span>

<span data-ttu-id="5df33-180">Questa funzione esegue il wrapping di una chiamata per il [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) (metodo).</span><span class="sxs-lookup"><span data-stu-id="5df33-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="5df33-181">L'utente non può creare classi con nomi che iniziano o terminano con chacater un carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="5df33-181">The user may not create classes with names that begin or end with an underscore chacater</span></span>

<span data-ttu-id="5df33-182">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="5df33-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="5df33-183">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5df33-183">Requirements</span></span>  
 <span data-ttu-id="5df33-184">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5df33-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5df33-185">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5df33-185">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5df33-186">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5df33-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df33-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5df33-187">See also</span></span>  
[<span data-ttu-id="5df33-188">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="5df33-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
