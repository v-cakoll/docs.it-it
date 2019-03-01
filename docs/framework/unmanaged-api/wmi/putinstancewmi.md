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
ms.openlocfilehash: 8268aca920c0b9fc8ea3390d80b9164c22c1ad9c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977856"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="3a759-103">PutInstanceWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="3a759-103">PutInstanceWmi function</span></span>
<span data-ttu-id="3a759-104">Crea o aggiorna un'istanza di una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="3a759-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="3a759-105">L'istanza viene scritta nel repository WMI.</span><span class="sxs-lookup"><span data-stu-id="3a759-105">The instance is written to the WMI repository.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3a759-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a759-106">Syntax</span></span>  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="3a759-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a759-107">Parameters</span></span>

`pInst`    
<span data-ttu-id="3a759-108">[in] Un puntatore all'istanza di essere scritto.</span><span class="sxs-lookup"><span data-stu-id="3a759-108">[in] A pointer to the instance to be writen.</span></span>

`lFlags`   
<span data-ttu-id="3a759-109">[in] Una combinazione di flag che influiscono sul comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="3a759-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="3a759-110">I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="3a759-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="3a759-111">Costante</span><span class="sxs-lookup"><span data-stu-id="3a759-111">Constant</span></span>  |<span data-ttu-id="3a759-112">Valore</span><span class="sxs-lookup"><span data-stu-id="3a759-112">Value</span></span>  |<span data-ttu-id="3a759-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a759-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="3a759-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="3a759-114">0x20000</span></span> | <span data-ttu-id="3a759-115">Se impostato, WMI non archivia i qualificatori con il **modificato** flavor.</span><span class="sxs-lookup"><span data-stu-id="3a759-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="3a759-116">Se non impostato, si presuppone che non viene localizzato con questo oggetto e tutti i qualificatori vengono storedwith questa istanza.</span><span class="sxs-lookup"><span data-stu-id="3a759-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="3a759-117">0</span><span class="sxs-lookup"><span data-stu-id="3a759-117">0</span></span> | <span data-ttu-id="3a759-118">Se non esiste o di sovrascriverlo se esiste già, creare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a759-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="3a759-119">1</span><span class="sxs-lookup"><span data-stu-id="3a759-119">1</span></span> | <span data-ttu-id="3a759-120">Aggiornare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a759-120">Update the instance.</span></span> <span data-ttu-id="3a759-121">L'istanza deve esistere per la chiamata abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3a759-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="3a759-122">2</span><span class="sxs-lookup"><span data-stu-id="3a759-122">2</span></span> | <span data-ttu-id="3a759-123">Creare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a759-123">Create the instance.</span></span> <span data-ttu-id="3a759-124">La chiamata ha esito negativo se l'istanza esiste già.</span><span class="sxs-lookup"><span data-stu-id="3a759-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="3a759-125">0x10</span><span class="sxs-lookup"><span data-stu-id="3a759-125">0x10</span></span> | <span data-ttu-id="3a759-126">Il flag determina una chiamata semisincrona.</span><span class="sxs-lookup"><span data-stu-id="3a759-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`  
<span data-ttu-id="3a759-127">[in] In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="3a759-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="3a759-128">In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istanza che può essere utilizzata dal provider che fornisce le classi richieste.</span><span class="sxs-lookup"><span data-stu-id="3a759-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="3a759-129">[out] Se `null`, questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="3a759-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="3a759-130">Se `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la funzione restituisce immediatamente il `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="3a759-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="3a759-131">Il `ppCallResult` parametro riceve un puntatore a una nuova [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) oggetto.</span><span class="sxs-lookup"><span data-stu-id="3a759-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="3a759-132">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3a759-132">Return value</span></span>

<span data-ttu-id="3a759-133">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="3a759-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3a759-134">Costante</span><span class="sxs-lookup"><span data-stu-id="3a759-134">Constant</span></span>  |<span data-ttu-id="3a759-135">Valore</span><span class="sxs-lookup"><span data-stu-id="3a759-135">Value</span></span>  |<span data-ttu-id="3a759-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a759-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="3a759-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="3a759-137">0x80041003</span></span> | <span data-ttu-id="3a759-138">L'utente dispone dell'autorizzazione per aggiornare un'istanza della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="3a759-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="3a759-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3a759-139">0x80041001</span></span> | <span data-ttu-id="3a759-140">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="3a759-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="3a759-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="3a759-141">0x80041010</span></span> | <span data-ttu-id="3a759-142">La classe di supporto di questa istanza non è valida.</span><span class="sxs-lookup"><span data-stu-id="3a759-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="3a759-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="3a759-143">0x80041028</span></span> | <span data-ttu-id="3a759-144">un `null` è stato specificato per una proprietà che non può essere `null`, ad esempio un oggetto che è stata contrassegnata da un **Indexed** oppure **Not_Null** qualificatore.</span><span class="sxs-lookup"><span data-stu-id="3a759-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="3a759-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="3a759-145">0x8004100f</span></span> | <span data-ttu-id="3a759-146">L'istanza specificata non è valido.</span><span class="sxs-lookup"><span data-stu-id="3a759-146">The specified instance is not valid.</span></span> <span data-ttu-id="3a759-147">(Ad esempio, la chiamata `PutInstanceWmi` con una classe restituisce questo valore.)</span><span class="sxs-lookup"><span data-stu-id="3a759-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3a759-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3a759-148">0x80041008</span></span> | <span data-ttu-id="3a759-149">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="3a759-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="3a759-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="3a759-150">0x80041019</span></span> | <span data-ttu-id="3a759-151">Il `WBEM_FLAG_CREATE_ONLY` flag è stato specificato, ma l'istanza è già presente.</span><span class="sxs-lookup"><span data-stu-id="3a759-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="3a759-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3a759-152">0x80041002</span></span> | <span data-ttu-id="3a759-153">`WBEM_FLAG_UPDATE_ONLY` è stato specificato `lFlags`, ma l'istanza non esiste.</span><span class="sxs-lookup"><span data-stu-id="3a759-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3a759-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3a759-154">0x80041006</span></span> | <span data-ttu-id="3a759-155">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="3a759-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="3a759-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="3a759-156">0x80041033</span></span> | <span data-ttu-id="3a759-157">WMI è stato probabilmente arresto e riavvio.</span><span class="sxs-lookup"><span data-stu-id="3a759-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="3a759-158">Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3a759-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="3a759-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="3a759-159">0x80041015</span></span> | <span data-ttu-id="3a759-160">Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="3a759-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3a759-161">0</span><span class="sxs-lookup"><span data-stu-id="3a759-161">0</span></span> | <span data-ttu-id="3a759-162">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3a759-162">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3a759-163">Note</span><span class="sxs-lookup"><span data-stu-id="3a759-163">Remarks</span></span>

<span data-ttu-id="3a759-164">Questa funzione esegue il wrapping di una chiamata per il [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3a759-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="3a759-165">Il `PutInstanceWmi` funzione supporta la creazione di istanze e aggiornamento delle istanze di classi esistenti solo.</span><span class="sxs-lookup"><span data-stu-id="3a759-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="3a759-166">A seconda del modo in cui il `pCtx` parametro è impostato, alcune o tutte le proprietà dell'istanza vengono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="3a759-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span> 

<span data-ttu-id="3a759-167">Quando l'istanza a cui punta `pInst` appartiene a una sottoclasse, gestione di Windows chiamate tutti i provider responsabile per le classi da cui deriva la sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="3a759-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="3a759-168">Tutti questi provider devono essere completate per originale `PutInstanceWmi` richiesta abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3a759-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="3a759-169">Il provider che supporta la classe di livello superiore nella gerarchia viene chiamato per primo.</span><span class="sxs-lookup"><span data-stu-id="3a759-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="3a759-170">Ordine di chiamata continua con la sottoclasse della classe di livello superiore e consente di passare dall'alto verso il basso finché gestione Windows raggiunge il provider per la classe proprietario di istanza a cui fa riferimento `pInst`.</span><span class="sxs-lookup"><span data-stu-id="3a759-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="3a759-171">Gestione di Windows non chiama il provider per tutte le classi figlio di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a759-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span> 

<span data-ttu-id="3a759-172">Quando un'applicazione deve aggiornare un'istanza che appartiene a una gerarchia di classi, le `pInst` parametro deve puntare all'istanza che contiene le proprietà da modificare.</span><span class="sxs-lookup"><span data-stu-id="3a759-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="3a759-173">Vale a dire, prendere in considerazione un'istanza di destinazione a cui appartiene **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="3a759-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="3a759-174">Il **ClassB** istanza derivata da **ClassA**, e **ClassA** definisce la proprietà **PropA**.</span><span class="sxs-lookup"><span data-stu-id="3a759-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="3a759-175">Se un'applicazione vuole apportare una modifica al valore di **PropA** nel **ClassB** istanza, è necessario impostare `pInst` a quell'istanza anziché a un'istanza di **ClassA** .</span><span class="sxs-lookup"><span data-stu-id="3a759-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="3a759-176">La chiamata `PutInstanceWmi` in un'istanza di una classe astratta non è consentita.</span><span class="sxs-lookup"><span data-stu-id="3a759-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="3a759-177">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="3a759-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a759-178">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a759-178">Requirements</span></span>  
 <span data-ttu-id="3a759-179">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a759-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a759-180">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3a759-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3a759-181">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a759-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a759-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a759-182">See also</span></span>
- [<span data-ttu-id="3a759-183">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="3a759-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
