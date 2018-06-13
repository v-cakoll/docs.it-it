---
title: Funzione CreateInstanceEnumWmi (riferimenti alle API non gestite)
description: La funzione CreateInstanceEnumWmi restituisce un enumeratore che contiene le istanze di una classe specificata che soddisfano i criteri di selezione.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f9297d34b01c03075db67bd904a81e589bfcc10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461376"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="8cec7-103">CreateInstanceEnumWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="8cec7-103">CreateInstanceEnumWmi function</span></span>
<span data-ttu-id="8cec7-104">Restituisce un enumeratore che restituisce le istanze di una classe specificata che soddisfano i criteri di selezione specificati.</span><span class="sxs-lookup"><span data-stu-id="8cec7-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8cec7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cec7-105">Syntax</span></span>  
  
```  
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
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

## <a name="parameters"></a><span data-ttu-id="8cec7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8cec7-106">Parameters</span></span>

`strFilter`    
<span data-ttu-id="8cec7-107">[in] Il nome della classe per cui si desidera creare istanze.</span><span class="sxs-lookup"><span data-stu-id="8cec7-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="8cec7-108">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="8cec7-108">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="8cec7-109">[in] Una combinazione di flag che influenzano il comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="8cec7-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="8cec7-110">I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="8cec7-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="8cec7-111">Costante</span><span class="sxs-lookup"><span data-stu-id="8cec7-111">Constant</span></span>  |<span data-ttu-id="8cec7-112">Valore</span><span class="sxs-lookup"><span data-stu-id="8cec7-112">Value</span></span>  |<span data-ttu-id="8cec7-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cec7-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="8cec7-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="8cec7-114">0x20000</span></span> | <span data-ttu-id="8cec7-115">Se impostato, la funzione recupera i qualificatori archiviati nello spazio dei nomi localizzata delle impostazioni locali della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="8cec7-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="8cec7-116">Se non impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato.</span><span class="sxs-lookup"><span data-stu-id="8cec7-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="8cec7-117">0</span><span class="sxs-lookup"><span data-stu-id="8cec7-117">0</span></span> | <span data-ttu-id="8cec7-118">L'enumerazione include questa e tutte le sottoclassi della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="8cec7-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="8cec7-119">1</span><span class="sxs-lookup"><span data-stu-id="8cec7-119">1</span></span> | <span data-ttu-id="8cec7-120">L'enumerazione include solo pure istanze di questa classe ed esclude tutte le istanze delle sottoclassi che forniscono le proprietà non è state trovate in questa classe.</span><span class="sxs-lookup"><span data-stu-id="8cec7-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="8cec7-121">0x10</span><span class="sxs-lookup"><span data-stu-id="8cec7-121">0x10</span></span> | <span data-ttu-id="8cec7-122">Il flag determina una chiamata semisincrona.</span><span class="sxs-lookup"><span data-stu-id="8cec7-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="8cec7-123">0x20</span><span class="sxs-lookup"><span data-stu-id="8cec7-123">0x20</span></span> | <span data-ttu-id="8cec7-124">La funzione restituisce un enumeratore forward-only.</span><span class="sxs-lookup"><span data-stu-id="8cec7-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="8cec7-125">In genere, gli enumeratori forward-only sono più veloci e utilizzano meno memoria convenzionali enumeratori, ma non consentono le chiamate a [Clone](clone.md).</span><span class="sxs-lookup"><span data-stu-id="8cec7-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="8cec7-126">0</span><span class="sxs-lookup"><span data-stu-id="8cec7-126">0</span></span> | <span data-ttu-id="8cec7-127">WMI consente di mantenere i puntatori agli oggetti di enumration finché vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="8cec7-127">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="8cec7-128">I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="8cec7-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="8cec7-129">[in] In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="8cec7-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="8cec7-130">In caso contrario, è un puntatore a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) istanza che può essere utilizzata dal provider che fornisce le istanze richieste.</span><span class="sxs-lookup"><span data-stu-id="8cec7-130">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`  
<span data-ttu-id="8cec7-131">[out] Riceve il puntatore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="8cec7-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="8cec7-132">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="8cec7-132">[in] The authorization level.</span></span>

<span data-ttu-id="8cec7-133">`impLevel` [in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="8cec7-133">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="8cec7-134">[in] Un puntatore a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto che rappresenta lo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="8cec7-134">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="8cec7-135">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="8cec7-135">[in] The user name.</span></span> <span data-ttu-id="8cec7-136">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="8cec7-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="8cec7-137">[in] La password.</span><span class="sxs-lookup"><span data-stu-id="8cec7-137">[in] The password.</span></span> <span data-ttu-id="8cec7-138">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="8cec7-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="8cec7-139">[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8cec7-139">[in] The domain name of the user.</span></span> <span data-ttu-id="8cec7-140">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="8cec7-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="8cec7-141">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8cec7-141">Return value</span></span>

<span data-ttu-id="8cec7-142">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="8cec7-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8cec7-143">Costante</span><span class="sxs-lookup"><span data-stu-id="8cec7-143">Constant</span></span>  |<span data-ttu-id="8cec7-144">Valore</span><span class="sxs-lookup"><span data-stu-id="8cec7-144">Value</span></span>  |<span data-ttu-id="8cec7-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cec7-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="8cec7-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="8cec7-146">0x80041003</span></span> | <span data-ttu-id="8cec7-147">L'utente non dispone dell'autorizzazione per visualizzare le istanze della classe specificata.</span><span class="sxs-lookup"><span data-stu-id="8cec7-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="8cec7-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8cec7-148">0x80041001</span></span> | <span data-ttu-id="8cec7-149">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="8cec7-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="8cec7-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="8cec7-150">0x80041010</span></span> | <span data-ttu-id="8cec7-151">`strFilter` non esiste.</span><span class="sxs-lookup"><span data-stu-id="8cec7-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8cec7-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8cec7-152">0x80041008</span></span> | <span data-ttu-id="8cec7-153">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="8cec7-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8cec7-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8cec7-154">0x80041006</span></span> | <span data-ttu-id="8cec7-155">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8cec7-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="8cec7-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="8cec7-156">0x80041033</span></span> | <span data-ttu-id="8cec7-157">WMI è stato probabilmente arrestato e riavviarlo.</span><span class="sxs-lookup"><span data-stu-id="8cec7-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="8cec7-158">Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente.</span><span class="sxs-lookup"><span data-stu-id="8cec7-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="8cec7-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="8cec7-159">0x80041015</span></span> | <span data-ttu-id="8cec7-160">Il collegamento remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="8cec7-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8cec7-161">0</span><span class="sxs-lookup"><span data-stu-id="8cec7-161">0</span></span> | <span data-ttu-id="8cec7-162">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="8cec7-162">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8cec7-163">Note</span><span class="sxs-lookup"><span data-stu-id="8cec7-163">Remarks</span></span>

<span data-ttu-id="8cec7-164">Questa funzione esegue il wrapping di una chiamata al [CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="8cec7-164">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="8cec7-165">Si noti che l'enumeratore restituito può disporre di zero elementi.</span><span class="sxs-lookup"><span data-stu-id="8cec7-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="8cec7-166">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="8cec7-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="8cec7-167">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8cec7-167">Requirements</span></span>  
 <span data-ttu-id="8cec7-168">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cec7-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cec7-169">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8cec7-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8cec7-170">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8cec7-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cec7-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cec7-171">See also</span></span>  
[<span data-ttu-id="8cec7-172">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="8cec7-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
