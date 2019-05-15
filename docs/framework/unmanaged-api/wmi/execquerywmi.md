---
title: Funzione ExecQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecQueryWmi esegue una query per recuperare oggetti.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3db6ddf51b8e83635f594c4716b57551475dc96f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636587"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="0b8c7-103">Funzione ExecQueryWmi</span><span class="sxs-lookup"><span data-stu-id="0b8c7-103">ExecQueryWmi function</span></span>

<span data-ttu-id="0b8c7-104">Esegue una query per il recupero di oggetti.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0b8c7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b8c7-105">Syntax</span></span>

```cpp
HRESULT ExecQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="0b8c7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b8c7-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="0b8c7-107">[in] Una stringa con il linguaggio di query valida supportata dalla gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="0b8c7-108">Deve essere "WQL", l'acronimo di WMI Query Language.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="0b8c7-109">[in] Il testo della query.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-109">[in] The text of the query.</span></span> <span data-ttu-id="0b8c7-110">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="0b8c7-111">[in] Una combinazione di flag che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="0b8c7-112">I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="0b8c7-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="0b8c7-113">Costante</span><span class="sxs-lookup"><span data-stu-id="0b8c7-113">Constant</span></span> | <span data-ttu-id="0b8c7-114">Value</span><span class="sxs-lookup"><span data-stu-id="0b8c7-114">Value</span></span>  | <span data-ttu-id="0b8c7-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b8c7-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="0b8c7-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="0b8c7-116">0x20000</span></span> | <span data-ttu-id="0b8c7-117">Se set, la funzione recupera i qualificatori archiviati nello spazio dei nomi localizzato delle impostazioni locali della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="0b8c7-118">Se non impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="0b8c7-119">0x10</span><span class="sxs-lookup"><span data-stu-id="0b8c7-119">0x10</span></span> | <span data-ttu-id="0b8c7-120">Il flag determina una chiamata semisincrona.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="0b8c7-121">0x20</span><span class="sxs-lookup"><span data-stu-id="0b8c7-121">0x20</span></span> | <span data-ttu-id="0b8c7-122">La funzione restituisce un enumeratore di tipo forward-only.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="0b8c7-123">In genere, gli enumeratori di tipo forward-only sono più veloci e usano meno memoria rispetto a enumeratori convenzionali, ma non consentono chiamate a [Clone](clone.md).</span><span class="sxs-lookup"><span data-stu-id="0b8c7-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="0b8c7-124">0</span><span class="sxs-lookup"><span data-stu-id="0b8c7-124">0</span></span> | <span data-ttu-id="0b8c7-125">WMI consente di mantenere i puntatori agli oggetti nell'enumerazione finché vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="0b8c7-126">0x100</span><span class="sxs-lookup"><span data-stu-id="0b8c7-126">0x100</span></span> | <span data-ttu-id="0b8c7-127">Assicura che qualsiasi gli oggetti restituiti abbiano informazioni sufficienti in essi contenuti in modo che le proprietà di sistema, ad esempio **Path**, **RelPath**, e **server**, non sono `null`.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="0b8c7-128">2</span><span class="sxs-lookup"><span data-stu-id="0b8c7-128">2</span></span> | <span data-ttu-id="0b8c7-129">Questo flag viene utilizzato per la creazione di prototipi.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-129">This flag is used for prototyping.</span></span> <span data-ttu-id="0b8c7-130">Non viene eseguita la query e restituisce invece un oggetto che è simile a un oggetto risultato tipico.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="0b8c7-131">0x200</span><span class="sxs-lookup"><span data-stu-id="0b8c7-131">0x200</span></span> | <span data-ttu-id="0b8c7-132">Accesso al provider per la classe specificata indipendentemente dalla relativa classe padre o in tutte le sottoclassi diretto cause.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="0b8c7-133">I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="0b8c7-134">[in] In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="0b8c7-135">In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istanza che può essere utilizzata dal provider che fornisce le classi richieste.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="0b8c7-136">[out] Se si verifica alcun errore, riceve il puntatore all'enumeratore che consente al chiamante recuperare le istanze nel set di risultati della query.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="0b8c7-137">La query può avere un set di risultati con zero istanze.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="0b8c7-138">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="0b8c7-139">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="0b8c7-140">[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="0b8c7-141">[in] Un puntatore a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto che rappresenta lo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="0b8c7-142">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-142">[in] The user name.</span></span> <span data-ttu-id="0b8c7-143">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="0b8c7-144">[in] La password.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-144">[in] The password.</span></span> <span data-ttu-id="0b8c7-145">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="0b8c7-146">[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-146">[in] The domain name of the user.</span></span> <span data-ttu-id="0b8c7-147">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="0b8c7-148">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0b8c7-148">Return value</span></span>

<span data-ttu-id="0b8c7-149">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="0b8c7-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0b8c7-150">Costante</span><span class="sxs-lookup"><span data-stu-id="0b8c7-150">Constant</span></span>  |<span data-ttu-id="0b8c7-151">Value</span><span class="sxs-lookup"><span data-stu-id="0b8c7-151">Value</span></span>  |<span data-ttu-id="0b8c7-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b8c7-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="0b8c7-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="0b8c7-153">0x80041003</span></span> | <span data-ttu-id="0b8c7-154">L'utente dispone dell'autorizzazione per visualizzare uno o più delle classi che la funzione può restituire.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="0b8c7-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0b8c7-155">0x80041001</span></span> | <span data-ttu-id="0b8c7-156">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0b8c7-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0b8c7-157">0x80041008</span></span> | <span data-ttu-id="0b8c7-158">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="0b8c7-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="0b8c7-159">0x80041017</span></span> | <span data-ttu-id="0b8c7-160">La query era un errore di sintassi.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="0b8c7-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="0b8c7-161">0x80041018</span></span> | <span data-ttu-id="0b8c7-162">Il linguaggio della query richiesta non è supportato.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="0b8c7-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="0b8c7-163">0x8004106c</span></span> | <span data-ttu-id="0b8c7-164">La query è troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0b8c7-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0b8c7-165">0x80041006</span></span> | <span data-ttu-id="0b8c7-166">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="0b8c7-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="0b8c7-167">0x80041033</span></span> | <span data-ttu-id="0b8c7-168">WMI è stato probabilmente arresto e riavvio.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="0b8c7-169">Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="0b8c7-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="0b8c7-170">0x80041015</span></span> | <span data-ttu-id="0b8c7-171">Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="0b8c7-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0b8c7-172">0x80041002</span></span> | <span data-ttu-id="0b8c7-173">La query specifica una classe che non esiste.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0b8c7-174">0</span><span class="sxs-lookup"><span data-stu-id="0b8c7-174">0</span></span> | <span data-ttu-id="0b8c7-175">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0b8c7-176">Note</span><span class="sxs-lookup"><span data-stu-id="0b8c7-176">Remarks</span></span>

<span data-ttu-id="0b8c7-177">Questa funzione esegue il wrapping di una chiamata per il [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) (metodo).</span><span class="sxs-lookup"><span data-stu-id="0b8c7-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="0b8c7-178">Questa funzione elabora la query specificata nel `strQuery` parametro e crea un enumeratore attraverso il quale il chiamante può accedere i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="0b8c7-179">L'enumeratore è un puntatore a un [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interfaccia; le query i risultati sono istanze degli oggetti classe rese disponibili tramite il [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="0b8c7-180">Sono previsti limiti al numero di `AND` e `OR` parole chiave che possono essere usate nelle query WQL.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="0b8c7-181">Un numero elevato di parole chiave WQL utilizzate in una query complessa può provocare WMI restituire il `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) codice di errore come un `HRESULT` valore.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="0b8c7-182">Il limite delle parole chiave WQL dipende complessità della query.</span><span class="sxs-lookup"><span data-stu-id="0b8c7-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="0b8c7-183">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="0b8c7-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b8c7-184">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b8c7-184">Requirements</span></span>

<span data-ttu-id="0b8c7-185">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b8c7-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="0b8c7-186">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0b8c7-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="0b8c7-187">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0b8c7-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0b8c7-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b8c7-188">See also</span></span>

- [<span data-ttu-id="0b8c7-189">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="0b8c7-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
