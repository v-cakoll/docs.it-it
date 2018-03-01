---
title: Funzione ExecNotificationQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecNotificationQueryWmi esegue una query per la ricezione di eventi.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6dd0926d2262f8d0aa125b86755017a65a95a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="a51c3-103">ExecNotificationQueryWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="a51c3-103">ExecNotificationQueryWmi function</span></span>
<span data-ttu-id="a51c3-104">Esegue una query per la ricezione di eventi.</span><span class="sxs-lookup"><span data-stu-id="a51c3-104">Executes a query to receive events.</span></span> <span data-ttu-id="a51c3-105">La chiamata restituisce immediatamente e il chiamante può eseguire il polling dell'enumeratore restituito per gli eventi appena arrivano.</span><span class="sxs-lookup"><span data-stu-id="a51c3-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="a51c3-106">Il rilascio dell'enumeratore restituito Annulla la query.</span><span class="sxs-lookup"><span data-stu-id="a51c3-106">Releasing the returned enumerator cancels the query.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a51c3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a51c3-107">Syntax</span></span>  
  
```  
HRESULT ExecNotificationQueryWmi (
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

## <a name="parameters"></a><span data-ttu-id="a51c3-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="a51c3-108">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="a51c3-109">[in] Una stringa con il linguaggio di query valida supportata dalla gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a51c3-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="a51c3-110">Deve essere "WQL", l'acronimo di WMI Query Language.</span><span class="sxs-lookup"><span data-stu-id="a51c3-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="a51c3-111">[in] Il testo della query.</span><span class="sxs-lookup"><span data-stu-id="a51c3-111">[in] The text of the query.</span></span> <span data-ttu-id="a51c3-112">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="a51c3-112">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="a51c3-113">[in] Una combinazione dei flag di due seguenti che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="a51c3-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="a51c3-114">Questi valori sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="a51c3-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> 

| <span data-ttu-id="a51c3-115">Costante</span><span class="sxs-lookup"><span data-stu-id="a51c3-115">Constant</span></span> | <span data-ttu-id="a51c3-116">Valore</span><span class="sxs-lookup"><span data-stu-id="a51c3-116">Value</span></span>  | <span data-ttu-id="a51c3-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a51c3-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="a51c3-118">0x10</span><span class="sxs-lookup"><span data-stu-id="a51c3-118">0x10</span></span> | <span data-ttu-id="a51c3-119">Il flag determina una chiamata semisincrona.</span><span class="sxs-lookup"><span data-stu-id="a51c3-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="a51c3-120">Se questo flag non è impostato, la chiamata ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="a51c3-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="a51c3-121">Questo avviene perché gli eventi vengono ricevuti in modo continuo, ovvero che l'utente deve eseguire il polling dell'enumeratore restituito.</span><span class="sxs-lookup"><span data-stu-id="a51c3-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="a51c3-122">Questa chiamata di blocco in modo indefinito che rende impossibile.</span><span class="sxs-lookup"><span data-stu-id="a51c3-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="a51c3-123">0x20</span><span class="sxs-lookup"><span data-stu-id="a51c3-123">0x20</span></span> | <span data-ttu-id="a51c3-124">La funzione restituisce un enumeratore forward-only.</span><span class="sxs-lookup"><span data-stu-id="a51c3-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="a51c3-125">In genere, gli enumeratori forward-only sono più veloci e utilizzano meno memoria convenzionali enumeratori, ma non consentono le chiamate a [Clone](clone.md).</span><span class="sxs-lookup"><span data-stu-id="a51c3-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`  
<span data-ttu-id="a51c3-126">[in] In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="a51c3-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="a51c3-127">In caso contrario, è un puntatore a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) istanza che può essere utilizzato dal provider che fornisce gli eventi di richiesti.</span><span class="sxs-lookup"><span data-stu-id="a51c3-127">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested events.</span></span> 

`ppEnum`  
<span data-ttu-id="a51c3-128">[out] Se si verifica alcun errore, riceve il puntatore a un enumeratore che consente al chiamante di recuperare le istanze nel set di risultati della query.</span><span class="sxs-lookup"><span data-stu-id="a51c3-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="a51c3-129">Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="a51c3-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="a51c3-130">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a51c3-130">[in] The authorization level.</span></span>

<span data-ttu-id="a51c3-131">`impLevel`[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="a51c3-131">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="a51c3-132">[in] Un puntatore a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto che rappresenta lo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="a51c3-132">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="a51c3-133">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="a51c3-133">[in] The user name.</span></span> <span data-ttu-id="a51c3-134">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="a51c3-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="a51c3-135">[in] La password.</span><span class="sxs-lookup"><span data-stu-id="a51c3-135">[in] The password.</span></span> <span data-ttu-id="a51c3-136">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="a51c3-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="a51c3-137">[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a51c3-137">[in] The domain name of the user.</span></span> <span data-ttu-id="a51c3-138">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="a51c3-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="a51c3-139">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a51c3-139">Return value</span></span>

<span data-ttu-id="a51c3-140">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="a51c3-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a51c3-141">Costante</span><span class="sxs-lookup"><span data-stu-id="a51c3-141">Constant</span></span>  |<span data-ttu-id="a51c3-142">Valore</span><span class="sxs-lookup"><span data-stu-id="a51c3-142">Value</span></span>  |<span data-ttu-id="a51c3-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a51c3-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="a51c3-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="a51c3-144">0x80041003</span></span> | <span data-ttu-id="a51c3-145">L'utente non dispone dell'autorizzazione per visualizzare uno o più classi che la funzione può restituire.</span><span class="sxs-lookup"><span data-stu-id="a51c3-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="a51c3-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a51c3-146">0x80041001</span></span> | <span data-ttu-id="a51c3-147">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="a51c3-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a51c3-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a51c3-148">0x80041008</span></span> | <span data-ttu-id="a51c3-149">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="a51c3-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="a51c3-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="a51c3-150">0x80041010</span></span> | <span data-ttu-id="a51c3-151">La query specifica una classe che non esiste.</span><span class="sxs-lookup"><span data-stu-id="a51c3-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="a51c3-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="a51c3-152">0x80042002</span></span> | <span data-ttu-id="a51c3-153">È stata richiesta una quantità eccessiva precisione nel recapito dei messaggi di eventi.</span><span class="sxs-lookup"><span data-stu-id="a51c3-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="a51c3-154">Una maggiore tolleranza di polling deve essere specificata.</span><span class="sxs-lookup"><span data-stu-id="a51c3-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="a51c3-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="a51c3-155">0x80042001</span></span> | <span data-ttu-id="a51c3-156">Requess la query in cui è possono fornire più informazioni di gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a51c3-156">The query requess more information than Windows Management can provide.</span></span> <span data-ttu-id="a51c3-157">Questo `HRESULT` viene restituito quando una query di eventi determina una richiesta per eseguire il polling di tutti gli oggetti in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a51c3-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="a51c3-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="a51c3-158">0x80041017</span></span> | <span data-ttu-id="a51c3-159">La query contiene un errore di sintassi.</span><span class="sxs-lookup"><span data-stu-id="a51c3-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="a51c3-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="a51c3-160">0x80041018</span></span> | <span data-ttu-id="a51c3-161">Il linguaggio di query richiesta non è supportato.</span><span class="sxs-lookup"><span data-stu-id="a51c3-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="a51c3-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="a51c3-162">0x8004106c</span></span> | <span data-ttu-id="a51c3-163">La query è troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="a51c3-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a51c3-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a51c3-164">0x80041006</span></span> | <span data-ttu-id="a51c3-165">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a51c3-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="a51c3-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="a51c3-166">0x80041033</span></span> | <span data-ttu-id="a51c3-167">WMI è stato probabilmente arrestato e riavviarlo.</span><span class="sxs-lookup"><span data-stu-id="a51c3-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="a51c3-168">Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente.</span><span class="sxs-lookup"><span data-stu-id="a51c3-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="a51c3-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="a51c3-169">0x80041015</span></span> | <span data-ttu-id="a51c3-170">Il collegamento remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="a51c3-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="a51c3-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="a51c3-171">0x80041058</span></span> | <span data-ttu-id="a51c3-172">Impossibile analizzare la query.</span><span class="sxs-lookup"><span data-stu-id="a51c3-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="a51c3-173">0</span><span class="sxs-lookup"><span data-stu-id="a51c3-173">0</span></span> | <span data-ttu-id="a51c3-174">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a51c3-174">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a51c3-175">Note</span><span class="sxs-lookup"><span data-stu-id="a51c3-175">Remarks</span></span>

<span data-ttu-id="a51c3-176">Questa funzione esegue il wrapping di una chiamata al [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="a51c3-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a51c3-177">Dopo la funzione restituisce, il chiamante passa periodicamente restituito `ppEnum` dell'oggetto per il [Avanti](next.md) funzione per verificare se tutti gli eventi sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="a51c3-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="a51c3-178">Vi sono limiti al numero di `AND` e `OR` parole chiave che possono essere utilizzate nelle query WQL.</span><span class="sxs-lookup"><span data-stu-id="a51c3-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="a51c3-179">Un numero elevato di parole chiave WQL utilizzate in una query complessa può provocare WMI restituire il `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) il codice di errore come un `HRESULT` valore.</span><span class="sxs-lookup"><span data-stu-id="a51c3-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="a51c3-180">Il limite di parole chiave WQL dipende la complessità della query.</span><span class="sxs-lookup"><span data-stu-id="a51c3-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="a51c3-181">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="a51c3-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="a51c3-182">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a51c3-182">Requirements</span></span>  
 <span data-ttu-id="a51c3-183">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a51c3-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a51c3-184">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a51c3-184">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a51c3-185">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a51c3-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51c3-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a51c3-186">See also</span></span>  
[<span data-ttu-id="a51c3-187">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="a51c3-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
