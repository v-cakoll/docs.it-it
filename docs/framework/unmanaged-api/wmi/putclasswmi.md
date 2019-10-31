---
title: Funzione PutClassWmi (riferimenti alle API non gestite)
description: La funzione PutClassWmi crea una nuova classe o ne aggiorna una esistente.
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
ms.openlocfilehash: 95a5e1f6339bde9dfe5c5ad9f989fc06e10fa7f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101785"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="cbe1a-103">PutClassWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="cbe1a-103">PutClassWmi function</span></span>

<span data-ttu-id="cbe1a-104">Crea una nuova classe o ne aggiorna una esistente.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cbe1a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbe1a-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="cbe1a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbe1a-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="cbe1a-107">in Puntatore a una definizione di classe valida.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="cbe1a-108">Deve essere inizializzata correttamente con tutti i valori di proprietà richiesti.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="cbe1a-109">in Combinazione di flag che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="cbe1a-110">I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="cbe1a-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cbe1a-111">Costante</span><span class="sxs-lookup"><span data-stu-id="cbe1a-111">Constant</span></span>  |<span data-ttu-id="cbe1a-112">Value</span><span class="sxs-lookup"><span data-stu-id="cbe1a-112">Value</span></span>  |<span data-ttu-id="cbe1a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbe1a-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="cbe1a-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="cbe1a-114">0x20000</span></span> | <span data-ttu-id="cbe1a-115">Se impostato, WMI non archivia alcun qualificatore con la versione modificata.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="cbe1a-116">Se non è impostato, si presuppone che l'oggetto non sia localizzato e che tutti i qualificatori siano archiviati con questa istanza.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="cbe1a-117">0</span><span class="sxs-lookup"><span data-stu-id="cbe1a-117">0</span></span> | <span data-ttu-id="cbe1a-118">Creare la classe se non esiste oppure sovrascriverla se esiste già.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="cbe1a-119">1</span><span class="sxs-lookup"><span data-stu-id="cbe1a-119">1</span></span> | <span data-ttu-id="cbe1a-120">Aggiornare la classe.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-120">Update the class.</span></span> <span data-ttu-id="cbe1a-121">La classe deve esistere affinché la chiamata abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="cbe1a-122">2</span><span class="sxs-lookup"><span data-stu-id="cbe1a-122">2</span></span> | <span data-ttu-id="cbe1a-123">Creare la classe.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-123">Create the class.</span></span> <span data-ttu-id="cbe1a-124">La chiamata ha esito negativo se la classe esiste già.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="cbe1a-125">0x10</span><span class="sxs-lookup"><span data-stu-id="cbe1a-125">0x10</span></span> | <span data-ttu-id="cbe1a-126">Il flag causa una chiamata semisincrono.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="cbe1a-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="cbe1a-127">0x10000</span></span> | <span data-ttu-id="cbe1a-128">I provider di push devono specificare questo flag quando si chiama `PutClassWmi` per indicare che questa classe è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="cbe1a-129">0</span><span class="sxs-lookup"><span data-stu-id="cbe1a-129">0</span></span> | <span data-ttu-id="cbe1a-130">Consente di aggiornare una classe se non sono presenti classi derivate e nessuna istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="cbe1a-131">Consente inoltre gli aggiornamenti in tutti i casi in cui la modifica riguarda solo i qualificatori non importanti, ad esempio il qualificatore della descrizione.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="cbe1a-132">Se la classe dispone di istanze o modifiche per i qualificatori importanti, l'aggiornamento avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="cbe1a-133">0x20</span><span class="sxs-lookup"><span data-stu-id="cbe1a-133">0x20</span></span> | <span data-ttu-id="cbe1a-134">Consente di aggiornare le classi anche se sono presenti classi figlio purché la modifica non causi conflitti con le classi figlio.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="cbe1a-135">Questo flag, ad esempio, consente di aggiungere una nuova proprietà alla classe di base che non è stata citata in precedenza in nessuna delle classi figlio.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="cbe1a-136">Se la classe dispone di istanze, l'aggiornamento avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="cbe1a-137">0x40</span><span class="sxs-lookup"><span data-stu-id="cbe1a-137">0x40</span></span> | <span data-ttu-id="cbe1a-138">forza gli aggiornamenti delle classi quando esistono classi figlio in conflitto.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="cbe1a-139">Questo flag, ad esempio, impone un aggiornamento se un qualificatore di classe è definito in una classe figlio e la classe di base tenta di aggiungere lo stesso qualificatore che è in conflitto con quello esistente.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="cbe1a-140">In modalità Force il conflitto TIS viene risolto eliminando il qualificatore in conflitto nella classe figlio.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="cbe1a-141">in In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="cbe1a-142">In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le classi richieste.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="cbe1a-143">out Se `null`, questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="cbe1a-144">Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la funzione viene restituita immediatamente con `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="cbe1a-145">Il parametro `ppCallResult` riceve un puntatore a un nuovo oggetto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .</span><span class="sxs-lookup"><span data-stu-id="cbe1a-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="cbe1a-146">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cbe1a-146">Return value</span></span>

<span data-ttu-id="cbe1a-147">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="cbe1a-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cbe1a-148">Costante</span><span class="sxs-lookup"><span data-stu-id="cbe1a-148">Constant</span></span>  |<span data-ttu-id="cbe1a-149">Value</span><span class="sxs-lookup"><span data-stu-id="cbe1a-149">Value</span></span>  |<span data-ttu-id="cbe1a-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbe1a-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="cbe1a-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="cbe1a-151">0x80041003</span></span> | <span data-ttu-id="cbe1a-152">L'utente non dispone delle autorizzazioni necessarie per creare o modificare le classi.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="cbe1a-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cbe1a-153">0x80041001</span></span> | <span data-ttu-id="cbe1a-154">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="cbe1a-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="cbe1a-155">0x80041010</span></span> | <span data-ttu-id="cbe1a-156">La classe specificata non è valida.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-156">The specified class is not valid.</span></span> <span data-ttu-id="cbe1a-157">In genere, ciò indica che `pObject` specifica un oggetto istanza.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cbe1a-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cbe1a-158">0x80041008</span></span> | <span data-ttu-id="cbe1a-159">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="cbe1a-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="cbe1a-160">0x80041016</span></span> | <span data-ttu-id="cbe1a-161">Il nome della classe specificato non è valido.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="cbe1a-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="cbe1a-162">0x80041025</span></span> | <span data-ttu-id="cbe1a-163">È stato effettuato un tentativo di apportare una modifica che invalida una sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="cbe1a-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="cbe1a-164">0x80041019</span></span> | <span data-ttu-id="cbe1a-165">Il flag di `WBEM_FLAG_CREATE_ONLY` è stato specificato, ma la classe esiste già.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="cbe1a-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="cbe1a-166">0x80041002</span></span> | <span data-ttu-id="cbe1a-167">`WBEM_FLAG_UPDATE_ONLY` è stato specificato in `lFlags`e la classe non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="cbe1a-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="cbe1a-168">0x80041020</span></span> | <span data-ttu-id="cbe1a-169">Le proprietà obbligatorie per le classi non sono state impostate.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cbe1a-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cbe1a-170">0x80041006</span></span> | <span data-ttu-id="cbe1a-171">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="cbe1a-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="cbe1a-172">0x80041033</span></span> | <span data-ttu-id="cbe1a-173">WMI è stato probabilmente interrotto e riavviato.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="cbe1a-174">Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="cbe1a-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="cbe1a-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="cbe1a-175">0x80041015</span></span> | <span data-ttu-id="cbe1a-176">Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cbe1a-177">0</span><span class="sxs-lookup"><span data-stu-id="cbe1a-177">0</span></span> | <span data-ttu-id="cbe1a-178">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="cbe1a-179">Note</span><span class="sxs-lookup"><span data-stu-id="cbe1a-179">Remarks</span></span>

<span data-ttu-id="cbe1a-180">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices::P utclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) .</span><span class="sxs-lookup"><span data-stu-id="cbe1a-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="cbe1a-181">L'utente non può creare classi con nomi che iniziano o terminano con un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="cbe1a-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="cbe1a-182">Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="cbe1a-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="cbe1a-183">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbe1a-183">Requirements</span></span>

<span data-ttu-id="cbe1a-184">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbe1a-184">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="cbe1a-185">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="cbe1a-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="cbe1a-186">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe1a-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cbe1a-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbe1a-187">See also</span></span>

- [<span data-ttu-id="cbe1a-188">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="cbe1a-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
