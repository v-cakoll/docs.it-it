---
title: Funzione ExecNotificationQueryWmi (riferimenti alle API non gestite)
description: La funzione ExecNotificationQueryWmi esegue una query per ricevere eventi.
ms.date: 11/06/2017
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
ms.openlocfilehash: 3d8a7683eef52a5e91bf7aa84d5aa7db7dbdac8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130446"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="45f7c-103">Funzione ExecNotificationQueryWmi</span><span class="sxs-lookup"><span data-stu-id="45f7c-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="45f7c-104">Esegue una query per la ricezione di eventi.</span><span class="sxs-lookup"><span data-stu-id="45f7c-104">Executes a query to receive events.</span></span> <span data-ttu-id="45f7c-105">La chiamata restituisce immediatamente un risultato e il chiamante può eseguire il polling dell'enumeratore restituito per gli eventi man mano che arrivano.</span><span class="sxs-lookup"><span data-stu-id="45f7c-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="45f7c-106">Se si rilascia l'enumeratore restituito, la query viene annullata.</span><span class="sxs-lookup"><span data-stu-id="45f7c-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="45f7c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45f7c-107">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="45f7c-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="45f7c-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="45f7c-109">in Stringa con il linguaggio di query valido supportato da gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="45f7c-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="45f7c-110">Deve essere "WQL", l'acronimo di WMI Query Language.</span><span class="sxs-lookup"><span data-stu-id="45f7c-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="45f7c-111">in Testo della query.</span><span class="sxs-lookup"><span data-stu-id="45f7c-111">[in] The text of the query.</span></span> <span data-ttu-id="45f7c-112">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="45f7c-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="45f7c-113">in Combinazione dei due flag seguenti che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="45f7c-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="45f7c-114">Questi valori vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="45f7c-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="45f7c-115">Costante</span><span class="sxs-lookup"><span data-stu-id="45f7c-115">Constant</span></span> | <span data-ttu-id="45f7c-116">Value</span><span class="sxs-lookup"><span data-stu-id="45f7c-116">Value</span></span>  | <span data-ttu-id="45f7c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45f7c-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="45f7c-118">0x10</span><span class="sxs-lookup"><span data-stu-id="45f7c-118">0x10</span></span> | <span data-ttu-id="45f7c-119">Il flag causa una chiamata semisincrono.</span><span class="sxs-lookup"><span data-stu-id="45f7c-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="45f7c-120">Se questo flag non è impostato, la chiamata ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="45f7c-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="45f7c-121">Poiché gli eventi vengono ricevuti continuamente, il che significa che l'utente deve eseguire il polling dell'enumeratore restituito.</span><span class="sxs-lookup"><span data-stu-id="45f7c-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="45f7c-122">Bloccando la chiamata in modo indefinito, l'operazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="45f7c-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="45f7c-123">0x20</span><span class="sxs-lookup"><span data-stu-id="45f7c-123">0x20</span></span> | <span data-ttu-id="45f7c-124">La funzione restituisce un enumeratore di sola trasmissione.</span><span class="sxs-lookup"><span data-stu-id="45f7c-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="45f7c-125">In genere, gli enumeratori di sola trasmissione sono più veloci e utilizzano meno memoria rispetto agli enumeratori convenzionali, ma non consentono le chiamate da [clonare](clone.md).</span><span class="sxs-lookup"><span data-stu-id="45f7c-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="45f7c-126">in In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="45f7c-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="45f7c-127">In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce gli eventi richiesti.</span><span class="sxs-lookup"><span data-stu-id="45f7c-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="45f7c-128">out Se non si verificano errori, riceve il puntatore all'enumeratore che consente al chiamante di recuperare le istanze nel set di risultati della query.</span><span class="sxs-lookup"><span data-stu-id="45f7c-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="45f7c-129">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="45f7c-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="45f7c-130">in Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="45f7c-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="45f7c-131">in Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="45f7c-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="45f7c-132">in Puntatore a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) che rappresenta lo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="45f7c-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="45f7c-133">in Nome utente.</span><span class="sxs-lookup"><span data-stu-id="45f7c-133">[in] The user name.</span></span> <span data-ttu-id="45f7c-134">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="45f7c-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="45f7c-135">in Password.</span><span class="sxs-lookup"><span data-stu-id="45f7c-135">[in] The password.</span></span> <span data-ttu-id="45f7c-136">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="45f7c-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="45f7c-137">in Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="45f7c-137">[in] The domain name of the user.</span></span> <span data-ttu-id="45f7c-138">Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="45f7c-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="45f7c-139">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45f7c-139">Return value</span></span>

<span data-ttu-id="45f7c-140">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="45f7c-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="45f7c-141">Costante</span><span class="sxs-lookup"><span data-stu-id="45f7c-141">Constant</span></span>  |<span data-ttu-id="45f7c-142">Value</span><span class="sxs-lookup"><span data-stu-id="45f7c-142">Value</span></span>  |<span data-ttu-id="45f7c-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45f7c-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="45f7c-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="45f7c-144">0x80041003</span></span> | <span data-ttu-id="45f7c-145">L'utente non dispone delle autorizzazioni necessarie per visualizzare una o più classi che la funzione può restituire.</span><span class="sxs-lookup"><span data-stu-id="45f7c-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="45f7c-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="45f7c-146">0x80041001</span></span> | <span data-ttu-id="45f7c-147">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="45f7c-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="45f7c-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="45f7c-148">0x80041008</span></span> | <span data-ttu-id="45f7c-149">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="45f7c-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="45f7c-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="45f7c-150">0x80041010</span></span> | <span data-ttu-id="45f7c-151">La query specifica una classe che non esiste.</span><span class="sxs-lookup"><span data-stu-id="45f7c-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="45f7c-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="45f7c-152">0x80042002</span></span> | <span data-ttu-id="45f7c-153">È stata richiesta una quantità eccessiva di precisione nel recapito degli eventi.</span><span class="sxs-lookup"><span data-stu-id="45f7c-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="45f7c-154">È necessario specificare una maggiore tolleranza di polling.</span><span class="sxs-lookup"><span data-stu-id="45f7c-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="45f7c-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="45f7c-155">0x80042001</span></span> | <span data-ttu-id="45f7c-156">La query richiede più informazioni di quelle che possono essere fornite da gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="45f7c-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="45f7c-157">Questa `HRESULT` viene restituita quando una query di evento restituisce una richiesta di eseguire il polling di tutti gli oggetti in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="45f7c-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="45f7c-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="45f7c-158">0x80041017</span></span> | <span data-ttu-id="45f7c-159">Errore di sintassi della query.</span><span class="sxs-lookup"><span data-stu-id="45f7c-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="45f7c-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="45f7c-160">0x80041018</span></span> | <span data-ttu-id="45f7c-161">Il linguaggio di query richiesto non è supportato.</span><span class="sxs-lookup"><span data-stu-id="45f7c-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="45f7c-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="45f7c-162">0x8004106c</span></span> | <span data-ttu-id="45f7c-163">La query è troppo complessa.</span><span class="sxs-lookup"><span data-stu-id="45f7c-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="45f7c-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="45f7c-164">0x80041006</span></span> | <span data-ttu-id="45f7c-165">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="45f7c-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="45f7c-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="45f7c-166">0x80041033</span></span> | <span data-ttu-id="45f7c-167">WMI è stato probabilmente interrotto e riavviato.</span><span class="sxs-lookup"><span data-stu-id="45f7c-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="45f7c-168">Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="45f7c-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="45f7c-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="45f7c-169">0x80041015</span></span> | <span data-ttu-id="45f7c-170">Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="45f7c-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="45f7c-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="45f7c-171">0x80041058</span></span> | <span data-ttu-id="45f7c-172">Impossibile analizzare la query.</span><span class="sxs-lookup"><span data-stu-id="45f7c-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="45f7c-173">0</span><span class="sxs-lookup"><span data-stu-id="45f7c-173">0</span></span> | <span data-ttu-id="45f7c-174">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="45f7c-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="45f7c-175">Note</span><span class="sxs-lookup"><span data-stu-id="45f7c-175">Remarks</span></span>

<span data-ttu-id="45f7c-176">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) .</span><span class="sxs-lookup"><span data-stu-id="45f7c-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="45f7c-177">Dopo la restituzione della funzione, il chiamante passa periodicamente l'oggetto `ppEnum` restituito alla funzione [successiva](next.md) per verificare se sono disponibili eventi.</span><span class="sxs-lookup"><span data-stu-id="45f7c-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="45f7c-178">Sono previsti limiti per il numero di parole chiave `AND` e `OR` che possono essere utilizzate nelle query WQL.</span><span class="sxs-lookup"><span data-stu-id="45f7c-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="45f7c-179">Un numero elevato di parole chiave WQL utilizzate in una query complessa può causare la restituzione da parte di WMI del codice di errore `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) come valore `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="45f7c-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="45f7c-180">Il limite di parole chiave WQL dipende dalla complessità della query.</span><span class="sxs-lookup"><span data-stu-id="45f7c-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="45f7c-181">Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="45f7c-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="45f7c-182">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45f7c-182">Requirements</span></span>

<span data-ttu-id="45f7c-183">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45f7c-183">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="45f7c-184">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="45f7c-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="45f7c-185">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45f7c-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="45f7c-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45f7c-186">See also</span></span>

- [<span data-ttu-id="45f7c-187">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="45f7c-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
