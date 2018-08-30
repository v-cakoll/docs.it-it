---
title: Funzione ConnectServerWmi (riferimenti alle API non gestite)
description: La funzione ConnectServerWmi Usa DCOM per creare una connessione a uno spazio dei nomi WMI.
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
ms.openlocfilehash: 163e61eef8a753b5b6470285e5e3ce63789e25a4
ms.sourcegitcommit: 875ecc3ab2437e299b1d50076bd9b878fa8c64de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "43238482"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="5b04a-103">ConnectServerWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="5b04a-103">ConnectServerWmi function</span></span>
<span data-ttu-id="5b04a-104">Crea una connessione mediante DCOM per uno spazio dei nomi WMI in un computer specifico.</span><span class="sxs-lookup"><span data-stu-id="5b04a-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5b04a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b04a-105">Syntax</span></span>  
  
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
## <a name="parameters"></a><span data-ttu-id="5b04a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b04a-106">Parameters</span></span>

<span data-ttu-id="5b04a-107">`strNetworkResource` [in] Puntatore a un valore valido `BSTR` che contiene il percorso dell'oggetto dello spazio dei nomi WMI corretto.</span><span class="sxs-lookup"><span data-stu-id="5b04a-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="5b04a-108">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="5b04a-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="5b04a-109">`strUser` [in] Un puntatore a un valore valido `BSTR` che contiene il nome utente.</span><span class="sxs-lookup"><span data-stu-id="5b04a-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="5b04a-110">Oggetto `null` valore indica il contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="5b04a-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="5b04a-111">Se l'utente è di un dominio diverso da quello corrente, `strUser` può inoltre contenere il nome utente e dominio separato da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="5b04a-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="5b04a-112">`strUser` può anche essere utente principal nome (UPN) formattare, suhc come *userName@domainName*.</span><span class="sxs-lookup"><span data-stu-id="5b04a-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="5b04a-113">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="5b04a-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="5b04a-114">`strPassword` [in] Un puntatore a un valore valido `BSTR` che contiene la password.</span><span class="sxs-lookup"><span data-stu-id="5b04a-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="5b04a-115">Oggetto `null` indica il contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="5b04a-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="5b04a-116">Una stringa vuota ("") indica una password valida di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="5b04a-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="5b04a-117">`strLocale` [in] Un puntatore a un valore valido `BSTR` che indica le impostazioni locali corrette per il recupero delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="5b04a-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="5b04a-118">Per gli identificatori delle impostazioni locali di Microsoft, il formato della stringa è "MS\_*xxx*", dove *xxx* è una stringa in formato esadecimale che indica l'identificatore delle impostazioni locali (LCID).</span><span class="sxs-lookup"><span data-stu-id="5b04a-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="5b04a-119">Se si specifica delle impostazioni locali non valida, il metodo restituisce `WBEM_E_INVALID_PARAMETER` tranne che in Windows 7, in cui le impostazioni locali predefinite del server viene usata invece.</span><span class="sxs-lookup"><span data-stu-id="5b04a-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="5b04a-120">Se ' viene usato null1, le impostazioni locali correnti.</span><span class="sxs-lookup"><span data-stu-id="5b04a-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="5b04a-121">`lSecurityFlags` [in] Flag da passare per il `ConnectServerWmi` (metodo).</span><span class="sxs-lookup"><span data-stu-id="5b04a-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="5b04a-122">Un valore pari a zero (0) per questo parametro determina la chiamata a `ConnectServerWmi` restituendo solo dopo aver stabilita una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="5b04a-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="5b04a-123">Ciò può comportare un'applicazione non risponde all'infinito se il server è interrotto.</span><span class="sxs-lookup"><span data-stu-id="5b04a-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="5b04a-124">Gli altri valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="5b04a-124">The other valid values are:</span></span>

| <span data-ttu-id="5b04a-125">Costante</span><span class="sxs-lookup"><span data-stu-id="5b04a-125">Constant</span></span>  | <span data-ttu-id="5b04a-126">Valore</span><span class="sxs-lookup"><span data-stu-id="5b04a-126">Value</span></span>  | <span data-ttu-id="5b04a-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b04a-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="5b04a-128">0x40</span><span class="sxs-lookup"><span data-stu-id="5b04a-128">0x40</span></span> | <span data-ttu-id="5b04a-129">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="5b04a-129">Reserved for internal use.</span></span> <span data-ttu-id="5b04a-130">Non usare.</span><span class="sxs-lookup"><span data-stu-id="5b04a-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="5b04a-131">0x80</span><span class="sxs-lookup"><span data-stu-id="5b04a-131">0x80</span></span> | <span data-ttu-id="5b04a-132">`ConnectServerWmi` Restituisce due minuti o meno.</span><span class="sxs-lookup"><span data-stu-id="5b04a-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="5b04a-133">`strAuthority` [in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5b04a-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="5b04a-134">Se son presenti i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5b04a-134">It can have the following values:</span></span>

| <span data-ttu-id="5b04a-135">Valore</span><span class="sxs-lookup"><span data-stu-id="5b04a-135">Value</span></span> | <span data-ttu-id="5b04a-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b04a-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="5b04a-137">blank</span><span class="sxs-lookup"><span data-stu-id="5b04a-137">blank</span></span> | <span data-ttu-id="5b04a-138">Viene utilizzata l'autenticazione NTLM e viene utilizzato il dominio NTLM dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="5b04a-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="5b04a-139">Se `strUser` specifica il dominio (la posizione consigliata), non deve essere specificato qui.</span><span class="sxs-lookup"><span data-stu-id="5b04a-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="5b04a-140">La funzione restituisce `WBEM_E_INVALID_PARAMETER` se si specifica il dominio in entrambi i parametri.</span><span class="sxs-lookup"><span data-stu-id="5b04a-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="5b04a-141">Kerberos:*nome dell'entità*</span><span class="sxs-lookup"><span data-stu-id="5b04a-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="5b04a-142">Viene utilizzata l'autenticazione Kerberos, e questo parametro contiene un nome dell'entità Kerberos.</span><span class="sxs-lookup"><span data-stu-id="5b04a-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="5b04a-143">NTLMDOMAIN:*nome di dominio*</span><span class="sxs-lookup"><span data-stu-id="5b04a-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="5b04a-144">Viene utilizzata l'autenticazione NT LAN Manager, e questo parametro contiene un nome di dominio NTLM.</span><span class="sxs-lookup"><span data-stu-id="5b04a-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="5b04a-145">[in] In genere, questo parametro è è `null`.</span><span class="sxs-lookup"><span data-stu-id="5b04a-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="5b04a-146">In caso contrario, è un puntatore a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) oggetto richiesto da uno o più provider di classe dinamica.</span><span class="sxs-lookup"><span data-stu-id="5b04a-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="5b04a-147">[out] Quando termina, la funzione riceve un puntatore a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto associato allo spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="5b04a-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="5b04a-148">Impostarlo in modo che punti a `null` quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="5b04a-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="5b04a-149">[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="5b04a-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="5b04a-150">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b04a-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="5b04a-151">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5b04a-151">Return value</span></span>

<span data-ttu-id="5b04a-152">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="5b04a-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5b04a-153">Costante</span><span class="sxs-lookup"><span data-stu-id="5b04a-153">Constant</span></span>  |<span data-ttu-id="5b04a-154">Valore</span><span class="sxs-lookup"><span data-stu-id="5b04a-154">Value</span></span>  |<span data-ttu-id="5b04a-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b04a-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="5b04a-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5b04a-156">0x80041001</span></span> | <span data-ttu-id="5b04a-157">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="5b04a-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5b04a-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5b04a-158">0x80041008</span></span> | <span data-ttu-id="5b04a-159">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="5b04a-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5b04a-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5b04a-160">0x80041006</span></span> | <span data-ttu-id="5b04a-161">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5b04a-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5b04a-162">0</span><span class="sxs-lookup"><span data-stu-id="5b04a-162">0</span></span> | <span data-ttu-id="5b04a-163">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5b04a-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5b04a-164">Note</span><span class="sxs-lookup"><span data-stu-id="5b04a-164">Remarks</span></span>

<span data-ttu-id="5b04a-165">Questa funzione esegue il wrapping di una chiamata per il [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) (metodo).</span><span class="sxs-lookup"><span data-stu-id="5b04a-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="5b04a-166">Per l'accesso locale per lo spazio dei nomi predefinito, `strNetworkResource` può essere un percorso semplice dell'oggetto: "root\default" o "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="5b04a-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="5b04a-167">Per l'accesso allo spazio dei nomi predefinito in un computer remoto utilizza COM o compatibile Microsoft, di rete, incluso il nome del computer: "\\myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="5b04a-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="5b04a-168">Inoltre, il nome del computer può essere un nome DNS o indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="5b04a-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="5b04a-169">Il `ConnectServerWmi` (funzione) possa anche connettersi con computer che eseguono IPv6 usando un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="5b04a-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="5b04a-170">`strUser` non può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="5b04a-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="5b04a-171">Se il dominio specificato nel `strAuthority`, perché non deve inoltre essere incluso nella `strUser`, o la funzione restituisce `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="5b04a-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="5b04a-172">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b04a-172">Requirements</span></span>  
 <span data-ttu-id="5b04a-173">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b04a-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b04a-174">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5b04a-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5b04a-175">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5b04a-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b04a-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b04a-176">See also</span></span>  
[<span data-ttu-id="5b04a-177">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="5b04a-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
