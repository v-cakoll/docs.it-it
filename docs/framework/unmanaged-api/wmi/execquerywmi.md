---
title: Funzione ExecQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecQueryWmi esegue una query per recuperare gli oggetti.
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
ms.openlocfilehash: b8547d306819e85b838f1160d9912dd43e42f2f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798679"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="41c72-103">Funzione ExecQueryWmi</span><span class="sxs-lookup"><span data-stu-id="41c72-103">ExecQueryWmi function</span></span>

<span data-ttu-id="41c72-104">Esegue una query per il recupero di oggetti.</span><span class="sxs-lookup"><span data-stu-id="41c72-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="41c72-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41c72-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="41c72-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="41c72-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="41c72-107">in Stringa con il linguaggio di query valido supportato da gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="41c72-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="41c72-108">Deve essere "WQL", l'acronimo di WMI Query Language.</span><span class="sxs-lookup"><span data-stu-id="41c72-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="41c72-109">in Testo della query.</span><span class="sxs-lookup"><span data-stu-id="41c72-109">[in] The text of the query.</span></span> <span data-ttu-id="41c72-110">Questo parametro non può `null`essere.</span><span class="sxs-lookup"><span data-stu-id="41c72-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="41c72-111">in Combinazione di flag che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="41c72-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="41c72-112">I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="41c72-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="41c72-113">Costante</span><span class="sxs-lookup"><span data-stu-id="41c72-113">Constant</span></span> | <span data-ttu-id="41c72-114">Value</span><span class="sxs-lookup"><span data-stu-id="41c72-114">Value</span></span>  | <span data-ttu-id="41c72-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41c72-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="41c72-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="41c72-116">0x20000</span></span> | <span data-ttu-id="41c72-117">Se impostata, la funzione recupera i qualificatori modificati archiviati nello spazio dei nomi localizzato delle impostazioni locali della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="41c72-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="41c72-118">Se non è impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato.</span><span class="sxs-lookup"><span data-stu-id="41c72-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="41c72-119">0x10</span><span class="sxs-lookup"><span data-stu-id="41c72-119">0x10</span></span> | <span data-ttu-id="41c72-120">Il flag causa una chiamata semisincrono.</span><span class="sxs-lookup"><span data-stu-id="41c72-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="41c72-121">0x20</span><span class="sxs-lookup"><span data-stu-id="41c72-121">0x20</span></span> | <span data-ttu-id="41c72-122">La funzione restituisce un enumeratore di sola trasmissione.</span><span class="sxs-lookup"><span data-stu-id="41c72-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="41c72-123">In genere, gli enumeratori di sola trasmissione sono più veloci e utilizzano meno memoria rispetto agli enumeratori convenzionali, ma non consentono le chiamate da [clonare](clone.md).</span><span class="sxs-lookup"><span data-stu-id="41c72-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="41c72-124">0</span><span class="sxs-lookup"><span data-stu-id="41c72-124">0</span></span> | <span data-ttu-id="41c72-125">WMI mantiene i puntatori agli oggetti nell'enumerazione fino a quando non vengono rilasciati.</span><span class="sxs-lookup"><span data-stu-id="41c72-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="41c72-126">0x100</span><span class="sxs-lookup"><span data-stu-id="41c72-126">0x100</span></span> | <span data-ttu-id="41c72-127">Garantisce che tutti gli oggetti restituiti dispongano di informazioni sufficienti in modo che le proprietà di sistema, ad esempio **__PATH**, **__RELPATH**e **__SERVER**, non `null`lo siano.</span><span class="sxs-lookup"><span data-stu-id="41c72-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="41c72-128">2</span><span class="sxs-lookup"><span data-stu-id="41c72-128">2</span></span> | <span data-ttu-id="41c72-129">Questo flag viene usato per la realizzazione di prototipi.</span><span class="sxs-lookup"><span data-stu-id="41c72-129">This flag is used for prototyping.</span></span> <span data-ttu-id="41c72-130">Non esegue la query e restituisce invece un oggetto simile a un oggetto risultato tipico.</span><span class="sxs-lookup"><span data-stu-id="41c72-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="41c72-131">0x200</span><span class="sxs-lookup"><span data-stu-id="41c72-131">0x200</span></span> | <span data-ttu-id="41c72-132">Causa l'accesso diretto al provider per la classe specificata senza considerare la relativa classe padre o qualsiasi sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="41c72-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="41c72-133">I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="41c72-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="41c72-134">in In genere, questo valore `null`è.</span><span class="sxs-lookup"><span data-stu-id="41c72-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="41c72-135">In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le classi richieste.</span><span class="sxs-lookup"><span data-stu-id="41c72-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="41c72-136">out Se non si verificano errori, riceve il puntatore all'enumeratore che consente al chiamante di recuperare le istanze nel set di risultati della query.</span><span class="sxs-lookup"><span data-stu-id="41c72-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="41c72-137">La query può avere un set di risultati con zero istanze.</span><span class="sxs-lookup"><span data-stu-id="41c72-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="41c72-138">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="41c72-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="41c72-139">in Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="41c72-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="41c72-140">in Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="41c72-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="41c72-141">in Puntatore a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) che rappresenta lo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="41c72-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="41c72-142">in Nome utente.</span><span class="sxs-lookup"><span data-stu-id="41c72-142">[in] The user name.</span></span> <span data-ttu-id="41c72-143">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="41c72-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="41c72-144">in Password.</span><span class="sxs-lookup"><span data-stu-id="41c72-144">[in] The password.</span></span> <span data-ttu-id="41c72-145">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="41c72-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="41c72-146">in Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="41c72-146">[in] The domain name of the user.</span></span> <span data-ttu-id="41c72-147">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="41c72-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="41c72-148">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="41c72-148">Return value</span></span>

<span data-ttu-id="41c72-149">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="41c72-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="41c72-150">Costante</span><span class="sxs-lookup"><span data-stu-id="41c72-150">Constant</span></span>  |<span data-ttu-id="41c72-151">Value</span><span class="sxs-lookup"><span data-stu-id="41c72-151">Value</span></span>  |<span data-ttu-id="41c72-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41c72-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="41c72-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="41c72-153">0x80041003</span></span> | <span data-ttu-id="41c72-154">L'utente non dispone delle autorizzazioni necessarie per visualizzare una o più classi che la funzione può restituire.</span><span class="sxs-lookup"><span data-stu-id="41c72-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="41c72-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="41c72-155">0x80041001</span></span> | <span data-ttu-id="41c72-156">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="41c72-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="41c72-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="41c72-157">0x80041008</span></span> | <span data-ttu-id="41c72-158">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="41c72-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="41c72-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="41c72-159">0x80041017</span></span> | <span data-ttu-id="41c72-160">Errore di sintassi della query.</span><span class="sxs-lookup"><span data-stu-id="41c72-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="41c72-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="41c72-161">0x80041018</span></span> | <span data-ttu-id="41c72-162">Il linguaggio di query richiesto non è supportato.</span><span class="sxs-lookup"><span data-stu-id="41c72-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="41c72-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="41c72-163">0x8004106c</span></span> | <span data-ttu-id="41c72-164">La query è troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="41c72-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="41c72-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="41c72-165">0x80041006</span></span> | <span data-ttu-id="41c72-166">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="41c72-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="41c72-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="41c72-167">0x80041033</span></span> | <span data-ttu-id="41c72-168">WMI è stato probabilmente interrotto e riavviato.</span><span class="sxs-lookup"><span data-stu-id="41c72-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="41c72-169">Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="41c72-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="41c72-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="41c72-170">0x80041015</span></span> | <span data-ttu-id="41c72-171">Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="41c72-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="41c72-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="41c72-172">0x80041002</span></span> | <span data-ttu-id="41c72-173">La query specifica una classe che non esiste.</span><span class="sxs-lookup"><span data-stu-id="41c72-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="41c72-174">0</span><span class="sxs-lookup"><span data-stu-id="41c72-174">0</span></span> | <span data-ttu-id="41c72-175">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="41c72-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="41c72-176">Note</span><span class="sxs-lookup"><span data-stu-id="41c72-176">Remarks</span></span>

<span data-ttu-id="41c72-177">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) .</span><span class="sxs-lookup"><span data-stu-id="41c72-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="41c72-178">Questa funzione elabora la query specificata nel `strQuery` parametro e crea un enumeratore tramite il quale il chiamante può accedere ai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="41c72-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="41c72-179">L'enumeratore è un puntatore a un'interfaccia [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) . i risultati della query sono istanze di oggetti della classe resi disponibili tramite l'interfaccia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="41c72-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="41c72-180">Sono previsti limiti al numero di `AND` parole chiave e `OR` che è possibile utilizzare nelle query WQL.</span><span class="sxs-lookup"><span data-stu-id="41c72-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="41c72-181">Un numero elevato di parole chiave WQL utilizzate in una query complessa può causare la restituzione del `WBEM_E_QUOTA_VIOLATION` codice di errore (o 0x8004106c) di WMI `HRESULT` come valore.</span><span class="sxs-lookup"><span data-stu-id="41c72-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="41c72-182">Il limite di parole chiave WQL dipende dalla complessità della query.</span><span class="sxs-lookup"><span data-stu-id="41c72-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="41c72-183">Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="41c72-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="41c72-184">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41c72-184">Requirements</span></span>

<span data-ttu-id="41c72-185">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41c72-185">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="41c72-186">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="41c72-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="41c72-187">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41c72-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="41c72-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41c72-188">See also</span></span>

- [<span data-ttu-id="41c72-189">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="41c72-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
