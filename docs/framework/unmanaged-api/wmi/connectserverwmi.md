---
title: Funzione ConnectServerWmi (riferimenti alle API non gestite)
description: La funzione ConnectServerWmi utilizza DCOM per creare una connessione a uno spazio dei nomi WMI.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de8447b9b090fc7f53df23346d61932bcb4dd6ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461997"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="1cfb0-103">ConnectServerWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="1cfb0-103">ConnectServerWmi function</span></span>
<span data-ttu-id="1cfb0-104">Crea una connessione mediante DCOM uno spazio dei nomi WMI in un computer specifico.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1cfb0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cfb0-105">Syntax</span></span>  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a><span data-ttu-id="1cfb0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1cfb0-106">Parameters</span></span>

<span data-ttu-id="1cfb0-107">`strNetworkResource` [in] Puntatore a un valore valido `BSTR` che contiene il percorso dell'oggetto dello spazio dei nomi WMI corretto.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="1cfb0-108">Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="1cfb0-109">`strUser` [in] Un puntatore a un valore valido `BSTR` che contiene il nome utente.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="1cfb0-110">Oggetto `null` valore indica il contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="1cfb0-111">Se l'utente è di un dominio diverso da quello corrente, `strUser` può inoltre contenere il nome di dominio e separato da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="1cfb0-112">`strUser` può anche essere utente nome principale (UPN) formattare, suhc come *userName@domainName*.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="1cfb0-113">Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="1cfb0-114">`strPassword` [in] Un puntatore a un valore valido `BSTR` che contiene la password.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="1cfb0-115">Oggetto `null` indica il contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="1cfb0-116">Una stringa vuota ("") indica una password valida di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="1cfb0-117">`strLocale` [in] Un puntatore a un valore valido `BSTR` che indica le impostazioni locali corrette per il recupero di informazioni.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="1cfb0-118">Per gli identificatori delle impostazioni locali Microsoft, il formato della stringa è "MS\_*xxx*", dove *xxx* è una stringa in formato esadecimale che indica l'identificatore delle impostazioni locali (LCID).</span><span class="sxs-lookup"><span data-stu-id="1cfb0-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="1cfb0-119">Se si specificano delle impostazioni locali non valida, il metodo restituisce `WBEM_E_INVALID_PARAMETER` tranne che in Windows 7, in cui le impostazioni locali predefinite del server viene utilizzata invece.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="1cfb0-120">Se ' viene utilizzato null1, le impostazioni locali correnti.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="1cfb0-121">`lSecurityFlags` [in] Flag da passare per il `ConnectServerWmi` metodo.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="1cfb0-122">Un valore pari a zero (0) per questo parametro determina la chiamata a `ConnectServerWmi` restituzione solo dopo che viene stabilita una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="1cfb0-123">Ciò potrebbe causare un'applicazione non risponde in modo indefinito se il server è interrotto.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="1cfb0-124">Gli altri valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="1cfb0-124">The other valid values are:</span></span>

| <span data-ttu-id="1cfb0-125">Costante</span><span class="sxs-lookup"><span data-stu-id="1cfb0-125">Constant</span></span>  | <span data-ttu-id="1cfb0-126">Valore</span><span class="sxs-lookup"><span data-stu-id="1cfb0-126">Value</span></span>  | <span data-ttu-id="1cfb0-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cfb0-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="1cfb0-128">0x40</span><span class="sxs-lookup"><span data-stu-id="1cfb0-128">0x40</span></span> | <span data-ttu-id="1cfb0-129">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-129">Reserved for internal use.</span></span> <span data-ttu-id="1cfb0-130">Non usare.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="1cfb0-131">0x80</span><span class="sxs-lookup"><span data-stu-id="1cfb0-131">0x80</span></span> | <span data-ttu-id="1cfb0-132">`ConnectServerWmi` Restituisce entro due minuti o meno.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="1cfb0-133">`strAuthority` [in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="1cfb0-134">Se son presenti i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1cfb0-134">It can have the following values:</span></span>

| <span data-ttu-id="1cfb0-135">Valore</span><span class="sxs-lookup"><span data-stu-id="1cfb0-135">Value</span></span> | <span data-ttu-id="1cfb0-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cfb0-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="1cfb0-137">blank</span><span class="sxs-lookup"><span data-stu-id="1cfb0-137">blank</span></span> | <span data-ttu-id="1cfb0-138">Viene utilizzata l'autenticazione NTLM e viene utilizzato il dominio NTLM dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="1cfb0-139">Se `strUser` specifica il dominio (il percorso consigliato), non deve essere specificato qui.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="1cfb0-140">La funzione restituisce `WBEM_E_INVALID_PARAMETER` se si specifica il dominio in entrambi i parametri.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="1cfb0-141">Kerberos:*nome dell'entità*</span><span class="sxs-lookup"><span data-stu-id="1cfb0-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="1cfb0-142">Viene utilizzata l'autenticazione Kerberos e questo parametro contiene un nome principale Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="1cfb0-143">NTLMDOMAIN:*nome di dominio*</span><span class="sxs-lookup"><span data-stu-id="1cfb0-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="1cfb0-144">Viene utilizzata l'autenticazione NT LAN Manager e questo parametro contiene un nome di dominio NTLM.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="1cfb0-145">[in] In genere, questo parametro è `null`.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="1cfb0-146">In caso contrario, è un puntatore a un [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) oggetto richiesto da uno o più provider di classe dinamica.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-146">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="1cfb0-147">[out] Quando la funzione restituisce, riceve un puntatore a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) oggetto associato allo spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-147">[out] When the function returns, receives a pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object bound to the specified namespace.</span></span> <span data-ttu-id="1cfb0-148">Si è impostato per puntare alla `null` quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="1cfb0-149">[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="1cfb0-150">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="1cfb0-151">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1cfb0-151">Return value</span></span>

<span data-ttu-id="1cfb0-152">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="1cfb0-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1cfb0-153">Costante</span><span class="sxs-lookup"><span data-stu-id="1cfb0-153">Constant</span></span>  |<span data-ttu-id="1cfb0-154">Valore</span><span class="sxs-lookup"><span data-stu-id="1cfb0-154">Value</span></span>  |<span data-ttu-id="1cfb0-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cfb0-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="1cfb0-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1cfb0-156">0x80041001</span></span> | <span data-ttu-id="1cfb0-157">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1cfb0-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1cfb0-158">0x80041008</span></span> | <span data-ttu-id="1cfb0-159">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1cfb0-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1cfb0-160">0x80041006</span></span> | <span data-ttu-id="1cfb0-161">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1cfb0-162">0</span><span class="sxs-lookup"><span data-stu-id="1cfb0-162">0</span></span> | <span data-ttu-id="1cfb0-163">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1cfb0-164">Note</span><span class="sxs-lookup"><span data-stu-id="1cfb0-164">Remarks</span></span>

<span data-ttu-id="1cfb0-165">Questa funzione esegue il wrapping di una chiamata al [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="1cfb0-166">Per l'accesso locale per lo spazio dei nomi predefinito, `strNetworkResource` può essere un percorso dell'oggetto semplice: "root\default" o "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="1cfb0-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="1cfb0-167">Per l'accesso allo spazio dei nomi predefinito in un computer remoto con una rete compatibile con Microsoft o di COM, includere il nome del computer: "\\myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="1cfb0-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="1cfb0-168">Inoltre, il nome del computer può essere un nome DNS o l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="1cfb0-169">Il `ConnectServerWmi` (funzione) può inoltre connettersi con computer che eseguono IPv6 utilizzando un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="1cfb0-170">`strUser` non può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="1cfb0-171">Se viene specificato il dominio `strAuthority`, non deve anche essere incluso `strUser`, o la funzione restituisce `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="1cfb0-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="1cfb0-172">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1cfb0-172">Requirements</span></span>  
 <span data-ttu-id="1cfb0-173">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cfb0-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cfb0-174">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1cfb0-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1cfb0-175">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1cfb0-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfb0-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cfb0-176">See also</span></span>  
[<span data-ttu-id="1cfb0-177">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="1cfb0-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
