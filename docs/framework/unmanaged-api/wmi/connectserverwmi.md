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
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798746"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="45bee-103">ConnectServerWmi (funzione)</span><span class="sxs-lookup"><span data-stu-id="45bee-103">ConnectServerWmi function</span></span>

<span data-ttu-id="45bee-104">Crea una connessione tramite DCOM a uno spazio dei nomi WMI in un computer specifico.</span><span class="sxs-lookup"><span data-stu-id="45bee-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="45bee-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45bee-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="45bee-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="45bee-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="45bee-107">in Puntatore a un oggetto `BSTR` valido che contiene il percorso dell'oggetto dello spazio dei nomi WMI corretto.</span><span class="sxs-lookup"><span data-stu-id="45bee-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="45bee-108">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="45bee-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="45bee-109">in Puntatore a un oggetto valido `BSTR` che contiene il nome utente.</span><span class="sxs-lookup"><span data-stu-id="45bee-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="45bee-110">`null` Valore che indica il contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="45bee-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="45bee-111">Se l'utente si trova in un dominio diverso da quello corrente, `strUser` può contenere anche il dominio e il nome utente separati da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="45bee-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="45bee-112">`strUser`può anche essere nel formato del nome dell'entità utente (UPN), `userName@domainName`ad esempio.</span><span class="sxs-lookup"><span data-stu-id="45bee-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="45bee-113">Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="45bee-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="45bee-114">in Puntatore a un oggetto valido `BSTR` che contiene la password.</span><span class="sxs-lookup"><span data-stu-id="45bee-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="45bee-115">Indica `null` il contesto di sicurezza corrente.</span><span class="sxs-lookup"><span data-stu-id="45bee-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="45bee-116">Una stringa vuota ("") indica una password di lunghezza zero valida.</span><span class="sxs-lookup"><span data-stu-id="45bee-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="45bee-117">in Puntatore a un oggetto valido `BSTR` che indica le impostazioni locali corrette per il recupero delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="45bee-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="45bee-118">Per gli identificatori delle impostazioni locali Microsoft, il formato della stringa è "\_MS*xxx*", dove *xxx* è una stringa in formato esadecimale che indica l'identificatore delle impostazioni locali (LCID).</span><span class="sxs-lookup"><span data-stu-id="45bee-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="45bee-119">Se si specificano impostazioni locali non valide, il metodo `WBEM_E_INVALID_PARAMETER` restituisce eccetto Windows 7, in cui vengono invece usate le impostazioni locali predefinite del server.</span><span class="sxs-lookup"><span data-stu-id="45bee-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="45bee-120">Se ' NULL1, vengono usate le impostazioni locali correnti.</span><span class="sxs-lookup"><span data-stu-id="45bee-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="45bee-121">in Flag da passare al `ConnectServerWmi` metodo.</span><span class="sxs-lookup"><span data-stu-id="45bee-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="45bee-122">Il valore zero (0) per questo parametro determina la `ConnectServerWmi` restituzione della chiamata solo dopo che è stata stabilita una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="45bee-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="45bee-123">Questo potrebbe comportare un'applicazione che non risponde a tempo indefinito se il server è danneggiato.</span><span class="sxs-lookup"><span data-stu-id="45bee-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="45bee-124">Gli altri valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="45bee-124">The other valid values are:</span></span>

| <span data-ttu-id="45bee-125">Costante</span><span class="sxs-lookup"><span data-stu-id="45bee-125">Constant</span></span>  | <span data-ttu-id="45bee-126">Value</span><span class="sxs-lookup"><span data-stu-id="45bee-126">Value</span></span>  | <span data-ttu-id="45bee-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="45bee-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="45bee-128">0x40</span><span class="sxs-lookup"><span data-stu-id="45bee-128">0x40</span></span> | <span data-ttu-id="45bee-129">Riservato per uso interno.</span><span class="sxs-lookup"><span data-stu-id="45bee-129">Reserved for internal use.</span></span> <span data-ttu-id="45bee-130">Non usare.</span><span class="sxs-lookup"><span data-stu-id="45bee-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="45bee-131">0x80</span><span class="sxs-lookup"><span data-stu-id="45bee-131">0x80</span></span> | <span data-ttu-id="45bee-132">`ConnectServerWmi`Restituisce tra due minuti o meno.</span><span class="sxs-lookup"><span data-stu-id="45bee-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="45bee-133">in Nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="45bee-133">[in] The domain name of the user.</span></span> <span data-ttu-id="45bee-134">Se son presenti i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="45bee-134">It can have the following values:</span></span>

| <span data-ttu-id="45bee-135">Value</span><span class="sxs-lookup"><span data-stu-id="45bee-135">Value</span></span> | <span data-ttu-id="45bee-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45bee-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="45bee-137">blank</span><span class="sxs-lookup"><span data-stu-id="45bee-137">blank</span></span> | <span data-ttu-id="45bee-138">Viene utilizzata l'autenticazione NTLM e viene utilizzato il dominio NTLM dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="45bee-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="45bee-139">Se `strUser` specifica il dominio (percorso consigliato), non deve essere specificato qui.</span><span class="sxs-lookup"><span data-stu-id="45bee-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="45bee-140">La funzione restituisce `WBEM_E_INVALID_PARAMETER` se si specifica il dominio in entrambi i parametri.</span><span class="sxs-lookup"><span data-stu-id="45bee-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="45bee-141">Kerberos:*nome entità*</span><span class="sxs-lookup"><span data-stu-id="45bee-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="45bee-142">Viene utilizzata l'autenticazione Kerberos e questo parametro contiene il nome di un'entità Kerberos.</span><span class="sxs-lookup"><span data-stu-id="45bee-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="45bee-143">NTLMDOMAIN:*nome di dominio*</span><span class="sxs-lookup"><span data-stu-id="45bee-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="45bee-144">Viene utilizzata l'autenticazione NT LAN Manager e questo parametro contiene un nome di dominio NTLM.</span><span class="sxs-lookup"><span data-stu-id="45bee-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="45bee-145">in In genere, questo parametro `null`è.</span><span class="sxs-lookup"><span data-stu-id="45bee-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="45bee-146">In caso contrario, è un puntatore a un oggetto [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) richiesto da uno o più provider di classi dinamici.</span><span class="sxs-lookup"><span data-stu-id="45bee-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="45bee-147">out Quando la funzione restituisce un risultato, riceve un puntatore a un oggetto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) associato allo spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="45bee-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="45bee-148">Viene impostato in modo da puntare `null` a quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="45bee-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="45bee-149">in Livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="45bee-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="45bee-150">in Livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="45bee-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="45bee-151">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45bee-151">Return value</span></span>

<span data-ttu-id="45bee-152">I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="45bee-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="45bee-153">Costante</span><span class="sxs-lookup"><span data-stu-id="45bee-153">Constant</span></span>  |<span data-ttu-id="45bee-154">Value</span><span class="sxs-lookup"><span data-stu-id="45bee-154">Value</span></span>  |<span data-ttu-id="45bee-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45bee-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="45bee-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="45bee-156">0x80041001</span></span> | <span data-ttu-id="45bee-157">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="45bee-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="45bee-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="45bee-158">0x80041008</span></span> | <span data-ttu-id="45bee-159">Parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="45bee-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="45bee-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="45bee-160">0x80041006</span></span> | <span data-ttu-id="45bee-161">Memoria insufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="45bee-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="45bee-162">0</span><span class="sxs-lookup"><span data-stu-id="45bee-162">0</span></span> | <span data-ttu-id="45bee-163">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="45bee-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="45bee-164">Note</span><span class="sxs-lookup"><span data-stu-id="45bee-164">Remarks</span></span>

<span data-ttu-id="45bee-165">Questa funzione esegue il wrapping di una chiamata al metodo [IWbemLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) .</span><span class="sxs-lookup"><span data-stu-id="45bee-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="45bee-166">Per l'accesso locale allo spazio dei nomi `strNetworkResource` predefinito, può essere un percorso di oggetto semplice: "root\default\\" o ".\root\default".</span><span class="sxs-lookup"><span data-stu-id="45bee-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="45bee-167">Per accedere allo spazio dei nomi predefinito in un computer remoto utilizzando le reti com o compatibili con Microsoft, includere il nome del\\computer: "myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="45bee-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="45bee-168">Il nome del computer può anche essere un nome DNS o un indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="45bee-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="45bee-169">La `ConnectServerWmi` funzione può inoltre connettersi a computer che eseguono IPv6 utilizzando un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="45bee-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="45bee-170">`strUser`non può essere una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="45bee-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="45bee-171">Se il dominio viene specificato in `strAuthority`, non deve essere incluso anche in `strUser`oppure la funzione restituisce `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="45bee-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="45bee-172">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45bee-172">Requirements</span></span>

 <span data-ttu-id="45bee-173">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45bee-173">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="45bee-174">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="45bee-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="45bee-175">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45bee-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="45bee-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45bee-176">See also</span></span>

- [<span data-ttu-id="45bee-177">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="45bee-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
