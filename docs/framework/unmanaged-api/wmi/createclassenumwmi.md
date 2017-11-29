---
title: Funzione CreateClassEnumWmi (riferimenti alle API non gestite)
description: La funzione CreateClassEnumWmi restituisce un enumeratore per tutte le classi che soddisfano criteri specificati.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateClassEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateClassEnumWmi
helpviewer_keywords: CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbfee6f8e98d04a591c58560e6d50044e716a1f
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="40d22-103">CreateClassEnumWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="40d22-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="40d22-104">Restituisce un enumeratore per tutte le classi che soddisfano i criteri di selezione specificati.</span><span class="sxs-lookup"><span data-stu-id="40d22-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="40d22-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40d22-105">Syntax</span></span>  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

## <a name="parameters"></a><span data-ttu-id="40d22-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="40d22-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="40d22-107">[in] Se non `null` o vuoto, che specifica il nome di una classe padre; l'enumeratore restituisce solo le sottoclassi di questa classe.</span><span class="sxs-lookup"><span data-stu-id="40d22-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="40d22-108">Se è `null` o vuoto e `lFlags` WBEM_FLAG_SHALLOW, restituisce solo classi di primo livello (classi con nessuna classe padre).</span><span class="sxs-lookup"><span data-stu-id="40d22-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="40d22-109">Se è `null` o vuoto e `lFlags` è `WBEM_FLAG_DEEP`, restituisce tutte le classi nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="40d22-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="40d22-110">[in] Una combinazione di flag che influenzano il comportamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="40d22-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="40d22-111">I valori seguenti vengono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="40d22-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="40d22-112">Costante</span><span class="sxs-lookup"><span data-stu-id="40d22-112">Constant</span></span>  |<span data-ttu-id="40d22-113">Valore</span><span class="sxs-lookup"><span data-stu-id="40d22-113">Value</span></span>  |<span data-ttu-id="40d22-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40d22-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="40d22-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="40d22-115">0x20000</span></span> | <span data-ttu-id="40d22-116">Se impostato, la funzione recupera i qualificatori archiviati nello spazio dei nomi localizzata delle impostazioni locali della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="40d22-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="40d22-117">Se non impostato, la funzione recupera solo i qualificatori archiviati nello spazio dei nomi immediato.</span><span class="sxs-lookup"><span data-stu-id="40d22-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="40d22-118">0</span><span class="sxs-lookup"><span data-stu-id="40d22-118">0</span></span> | <span data-ttu-id="40d22-119">L'enumerazione include tutte le sottoclassi nella gerarchia, ma non da questa classe.</span><span class="sxs-lookup"><span data-stu-id="40d22-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="40d22-120">1</span><span class="sxs-lookup"><span data-stu-id="40d22-120">1</span></span> | <span data-ttu-id="40d22-121">L'enumerazione include solo pure istanze di questa classe ed esclude tutte le istanze delle sottoclassi che forniscono le proprietà non è state trovate in questa classe.</span><span class="sxs-lookup"><span data-stu-id="40d22-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="40d22-122">0x10</span><span class="sxs-lookup"><span data-stu-id="40d22-122">0x10</span></span> | <span data-ttu-id="40d22-123">Il flag determina una chiamata semisincrona.</span><span class="sxs-lookup"><span data-stu-id="40d22-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="40d22-124">0x20</span><span class="sxs-lookup"><span data-stu-id="40d22-124">0x20</span></span> | <span data-ttu-id="40d22-125">La funzione restituisce un enumeratore forward-only.</span><span class="sxs-lookup"><span data-stu-id="40d22-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="40d22-126">In genere, gli enumeratori forward-only sono più veloci e utilizzano meno memoria convenzionali enumeratori, ma non consentono le chiamate a [Clone](clone.md).</span><span class="sxs-lookup"><span data-stu-id="40d22-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="40d22-127">0</span><span class="sxs-lookup"><span data-stu-id="40d22-127">0</span></span> | <span data-ttu-id="40d22-128">WMI consente di mantenere i puntatori agli oggetti di enumration finché vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="40d22-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="40d22-129">I flag consigliati sono `WBEM_FLAG_RETURN_IMMEDIATELY` e `WBEM_FLAG_FORWARD_ONLY` per prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="40d22-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="40d22-130">[in] In genere, questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="40d22-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="40d22-131">In caso contrario, è un puntatore a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) istanza che può essere utilizzato dal provider che fornisce le classi di richieste.</span><span class="sxs-lookup"><span data-stu-id="40d22-131">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="40d22-132">[out] Riceve il puntatore dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="40d22-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="40d22-133">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="40d22-133">[in] The authorization level.</span></span>

<span data-ttu-id="40d22-134">`impLevel`[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="40d22-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="40d22-135">[in] Un puntatore a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto che rappresenta lo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="40d22-135">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="40d22-136">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="40d22-136">[in] The user name.</span></span> <span data-ttu-id="40d22-137">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="40d22-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="40d22-138">[in] La password.</span><span class="sxs-lookup"><span data-stu-id="40d22-138">[in] The password.</span></span> <span data-ttu-id="40d22-139">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="40d22-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="40d22-140">[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="40d22-140">[in] The domain name of the user.</span></span> <span data-ttu-id="40d22-141">Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="40d22-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="40d22-142">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="40d22-142">Return value</span></span>

<span data-ttu-id="40d22-143">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="40d22-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="40d22-144">Costante</span><span class="sxs-lookup"><span data-stu-id="40d22-144">Constant</span></span>  |<span data-ttu-id="40d22-145">Valore</span><span class="sxs-lookup"><span data-stu-id="40d22-145">Value</span></span>  |<span data-ttu-id="40d22-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40d22-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="40d22-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="40d22-147">0x80041003</span></span> | <span data-ttu-id="40d22-148">L'utente non dispone dell'autorizzazione per visualizzare uno o più classi che la funzione può restituire.</span><span class="sxs-lookup"><span data-stu-id="40d22-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="40d22-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="40d22-149">0x80041001</span></span> | <span data-ttu-id="40d22-150">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="40d22-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="40d22-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="40d22-151">0x80041010</span></span> | <span data-ttu-id="40d22-152">`strSuperClass` non esiste.</span><span class="sxs-lookup"><span data-stu-id="40d22-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="40d22-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="40d22-153">0x80041008</span></span> | <span data-ttu-id="40d22-154">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="40d22-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="40d22-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="40d22-155">0x80041006</span></span> | <span data-ttu-id="40d22-156">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="40d22-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="40d22-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="40d22-157">0x80041033</span></span> | <span data-ttu-id="40d22-158">WMI è stato probabilmente arrestato e riavviarlo.</span><span class="sxs-lookup"><span data-stu-id="40d22-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="40d22-159">Chiamare [ConnectServerWmi](connectserverwmi.md) nuovamente.</span><span class="sxs-lookup"><span data-stu-id="40d22-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="40d22-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="40d22-160">0x80041015</span></span> | <span data-ttu-id="40d22-161">Il collegamento remote procedure call (RPC) tra il processo corrente e WMI non riuscita.</span><span class="sxs-lookup"><span data-stu-id="40d22-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="40d22-162">0</span><span class="sxs-lookup"><span data-stu-id="40d22-162">0</span></span> | <span data-ttu-id="40d22-163">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="40d22-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="40d22-164">Note</span><span class="sxs-lookup"><span data-stu-id="40d22-164">Remarks</span></span>

<span data-ttu-id="40d22-165">Questa funzione esegue il wrapping di una chiamata al [CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="40d22-165">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="40d22-166">Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="40d22-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="40d22-167">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40d22-167">Requirements</span></span>  
 <span data-ttu-id="40d22-168">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40d22-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40d22-169">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="40d22-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="40d22-170">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="40d22-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d22-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40d22-171">See also</span></span>  
[<span data-ttu-id="40d22-172">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="40d22-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
