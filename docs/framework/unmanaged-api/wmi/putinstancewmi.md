---
title: Funzione PutInstanceWmi (riferimenti alle API non gestite)
description: La funzione PutInstanceWmi crea o aggiorna un'istanza di una classe esistente.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798378"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="713eb-103">PutInstanceWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="713eb-103">PutInstanceWmi function</span></span>

<span data-ttu-id="713eb-104">Crea o aggiorna un'istanza di una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="713eb-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="713eb-105">L'istanza viene scritta nel repository WMI.</span><span class="sxs-lookup"><span data-stu-id="713eb-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="713eb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="713eb-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="713eb-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="713eb-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="713eb-108">in Puntatore all'istanza da scrivere.</span><span class="sxs-lookup"><span data-stu-id="713eb-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="713eb-109">in Combinazione di flag che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="713eb-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="713eb-110">I valori seguenti vengono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="713eb-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="713eb-111">Costante</span><span class="sxs-lookup"><span data-stu-id="713eb-111">Constant</span></span>  |<span data-ttu-id="713eb-112">Value</span><span class="sxs-lookup"><span data-stu-id="713eb-112">Value</span></span>  |<span data-ttu-id="713eb-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="713eb-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="713eb-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="713eb-114">0x20000</span></span> | <span data-ttu-id="713eb-115">Se impostato, WMI non archivia alcun qualificatore con la **versione modificata** .</span><span class="sxs-lookup"><span data-stu-id="713eb-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="713eb-116">Se non è impostato, si presuppone che l'oggetto non sia localizzato e che tutti i qualificatori siano archiviati con questa istanza.</span><span class="sxs-lookup"><span data-stu-id="713eb-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="713eb-117">0</span><span class="sxs-lookup"><span data-stu-id="713eb-117">0</span></span> | <span data-ttu-id="713eb-118">Creare l'istanza, se non esiste, oppure sovrascriverla se esiste già.</span><span class="sxs-lookup"><span data-stu-id="713eb-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="713eb-119">1</span><span class="sxs-lookup"><span data-stu-id="713eb-119">1</span></span> | <span data-ttu-id="713eb-120">Aggiornare l'istanza di.</span><span class="sxs-lookup"><span data-stu-id="713eb-120">Update the instance.</span></span> <span data-ttu-id="713eb-121">L'istanza deve esistere affinché la chiamata abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="713eb-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="713eb-122">2</span><span class="sxs-lookup"><span data-stu-id="713eb-122">2</span></span> | <span data-ttu-id="713eb-123">Creare l'istanza di.</span><span class="sxs-lookup"><span data-stu-id="713eb-123">Create the instance.</span></span> <span data-ttu-id="713eb-124">La chiamata ha esito negativo se l'istanza esiste già.</span><span class="sxs-lookup"><span data-stu-id="713eb-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="713eb-125">0x10</span><span class="sxs-lookup"><span data-stu-id="713eb-125">0x10</span></span> | <span data-ttu-id="713eb-126">Il flag causa una chiamata semisincrono.</span><span class="sxs-lookup"><span data-stu-id="713eb-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="713eb-127">in In genere, questo valore `null`è.</span><span class="sxs-lookup"><span data-stu-id="713eb-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="713eb-128">In caso contrario, è un puntatore a un'istanza di [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) che può essere usata dal provider che fornisce le classi richieste.</span><span class="sxs-lookup"><span data-stu-id="713eb-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="713eb-129">out Se `null`, questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="713eb-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="713eb-130">Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY` ,`WBEM_S_NO_ERROR`la funzione restituisce immediatamente.</span><span class="sxs-lookup"><span data-stu-id="713eb-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="713eb-131">Il `ppCallResult` parametro riceve un puntatore a un nuovo oggetto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .</span><span class="sxs-lookup"><span data-stu-id="713eb-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="713eb-132">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="713eb-132">Return value</span></span>

<span data-ttu-id="713eb-133">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="713eb-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="713eb-134">Costante</span><span class="sxs-lookup"><span data-stu-id="713eb-134">Constant</span></span>  |<span data-ttu-id="713eb-135">Value</span><span class="sxs-lookup"><span data-stu-id="713eb-135">Value</span></span>  |<span data-ttu-id="713eb-136">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="713eb-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="713eb-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="713eb-137">0x80041003</span></span> | <span data-ttu-id="713eb-138">L'utente non dispone delle autorizzazioni necessarie per aggiornare un'istanza della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="713eb-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="713eb-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="713eb-139">0x80041001</span></span> | <span data-ttu-id="713eb-140">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="713eb-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="713eb-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="713eb-141">0x80041010</span></span> | <span data-ttu-id="713eb-142">La classe che supporta questa istanza non è valida.</span><span class="sxs-lookup"><span data-stu-id="713eb-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="713eb-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="713eb-143">0x80041028</span></span> | <span data-ttu-id="713eb-144">è `null` stato specificato un oggetto per una proprietà che `null`non può essere, ad esempio uno contrassegnato da un qualificatore **NOT_NULL** o **indicizzato** .</span><span class="sxs-lookup"><span data-stu-id="713eb-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="713eb-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="713eb-145">0x8004100f</span></span> | <span data-ttu-id="713eb-146">L'istanza specificata non è valida.</span><span class="sxs-lookup"><span data-stu-id="713eb-146">The specified instance is not valid.</span></span> <span data-ttu-id="713eb-147">(Ad esempio, la `PutInstanceWmi` chiamata a con una classe restituisce questo valore).</span><span class="sxs-lookup"><span data-stu-id="713eb-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="713eb-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="713eb-148">0x80041008</span></span> | <span data-ttu-id="713eb-149">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="713eb-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="713eb-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="713eb-150">0x80041019</span></span> | <span data-ttu-id="713eb-151">Il `WBEM_FLAG_CREATE_ONLY` flag è stato specificato, ma l'istanza esiste già.</span><span class="sxs-lookup"><span data-stu-id="713eb-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="713eb-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="713eb-152">0x80041002</span></span> | <span data-ttu-id="713eb-153">`WBEM_FLAG_UPDATE_ONLY`è stato specificato `lFlags`in, ma l'istanza non esiste.</span><span class="sxs-lookup"><span data-stu-id="713eb-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="713eb-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="713eb-154">0x80041006</span></span> | <span data-ttu-id="713eb-155">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="713eb-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="713eb-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="713eb-156">0x80041033</span></span> | <span data-ttu-id="713eb-157">WMI è stato probabilmente interrotto e riavviato.</span><span class="sxs-lookup"><span data-stu-id="713eb-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="713eb-158">Chiamare nuovamente [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="713eb-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="713eb-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="713eb-159">0x80041015</span></span> | <span data-ttu-id="713eb-160">Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="713eb-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="713eb-161">0</span><span class="sxs-lookup"><span data-stu-id="713eb-161">0</span></span> | <span data-ttu-id="713eb-162">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="713eb-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="713eb-163">Note</span><span class="sxs-lookup"><span data-stu-id="713eb-163">Remarks</span></span>

<span data-ttu-id="713eb-164">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .</span><span class="sxs-lookup"><span data-stu-id="713eb-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="713eb-165">La `PutInstanceWmi` funzione supporta la creazione di istanze e l'aggiornamento solo delle istanze delle classi esistenti.</span><span class="sxs-lookup"><span data-stu-id="713eb-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="713eb-166">A seconda della modalità di `pCtx` impostazione del parametro, vengono aggiornate alcune o tutte le proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="713eb-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="713eb-167">Quando l'istanza a `pInst` cui fa riferimento appartiene a una sottoclasse, gestione Windows chiama tutti i provider responsabili delle classi da cui deriva la sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="713eb-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="713eb-168">Tutti questi provider devono avere esito positivo affinché `PutInstanceWmi` la richiesta originale abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="713eb-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="713eb-169">Il provider che supporta la classe più in alto nella gerarchia viene chiamato per primo.</span><span class="sxs-lookup"><span data-stu-id="713eb-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="713eb-170">L'ordine di chiamata continua con la sottoclasse della classe superiore e procede dall'alto verso il basso fino a quando gestione Windows non raggiunge il provider per la classe proprietaria dell' `pInst`istanza a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="713eb-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="713eb-171">Gestione Windows non chiama i provider per nessuna delle classi figlio di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="713eb-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="713eb-172">Quando un'applicazione deve aggiornare un'istanza che appartiene a una gerarchia di classi, `pInst` il parametro deve puntare all'istanza contenente le proprietà da modificare.</span><span class="sxs-lookup"><span data-stu-id="713eb-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="713eb-173">Ovvero, si consideri un'istanza di destinazione che appartiene a **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="713eb-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="713eb-174">L'istanza di **ClassB** deriva da **ClassA**e **ClassA** definisce la proprietà **propa**.</span><span class="sxs-lookup"><span data-stu-id="713eb-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="713eb-175">Se un'applicazione vuole apportare una modifica al valore di **propa** nell'istanza di **ClassB** , deve impostare `pInst` su tale istanza anziché su un'istanza di **ClassA**.</span><span class="sxs-lookup"><span data-stu-id="713eb-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="713eb-176">La `PutInstanceWmi` chiamata su un'istanza di una classe astratta non è consentita.</span><span class="sxs-lookup"><span data-stu-id="713eb-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="713eb-177">Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="713eb-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="713eb-178">Requisiti</span><span class="sxs-lookup"><span data-stu-id="713eb-178">Requirements</span></span>

<span data-ttu-id="713eb-179">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="713eb-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="713eb-180">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="713eb-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="713eb-181">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="713eb-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="713eb-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="713eb-182">See also</span></span>

- [<span data-ttu-id="713eb-183">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="713eb-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
