---
title: Configurazione proxy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 41f7cfe76acfb4b6bbf66207685935c190a51901
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="proxy-configuration"></a><span data-ttu-id="00b0c-102">Configurazione proxy</span><span class="sxs-lookup"><span data-stu-id="00b0c-102">Proxy Configuration</span></span>
<span data-ttu-id="00b0c-103">Un server proxy gestisce le richieste di risorse del client.</span><span class="sxs-lookup"><span data-stu-id="00b0c-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="00b0c-104">Un proxy può restituire una risorsa richiesta dalla cache o inoltrare la richiesta al server in cui risiede la risorsa.</span><span class="sxs-lookup"><span data-stu-id="00b0c-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="00b0c-105">I proxy possono migliorare le prestazioni della rete riducendo il numero di richieste inviate ai server remoti.</span><span class="sxs-lookup"><span data-stu-id="00b0c-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="00b0c-106">I proxy possono essere usati anche per limitare l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="00b0c-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="00b0c-107">Proxy adattivi</span><span class="sxs-lookup"><span data-stu-id="00b0c-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="00b0c-108">In .NET Framework i proxy possono essere di due tipi: adattivi e statici.</span><span class="sxs-lookup"><span data-stu-id="00b0c-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="00b0c-109">I proxy adattivi regolano le impostazioni quando viene modificata la configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="00b0c-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="00b0c-110">Ad esempio, se un utente avvia una connessione di rete remota sul laptop, un proxy adattivo riconosce questa modifica, individua ed esegue il nuovo script di configurazione e regola le impostazioni in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="00b0c-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="00b0c-111">I proxy adattivi vengono configurati con uno script di configurazione (vedere [Rilevamento automatico proxy](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="00b0c-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="00b0c-112">Lo script genera un set di protocolli di applicazioni e un proxy per ogni protocollo.</span><span class="sxs-lookup"><span data-stu-id="00b0c-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="00b0c-113">Diverse opzioni controllano come viene eseguito lo script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00b0c-113">Several options control how the configuration script is run.</span></span> <span data-ttu-id="00b0c-114">È possibile specificare:</span><span class="sxs-lookup"><span data-stu-id="00b0c-114">You can specify the following:</span></span>  
  
-   <span data-ttu-id="00b0c-115">Frequenza di download e di esecuzione dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00b0c-115">How often the configuration script is downloaded and run.</span></span>  
  
-   <span data-ttu-id="00b0c-116">Tempo di attesa del download dello script.</span><span class="sxs-lookup"><span data-stu-id="00b0c-116">How long to wait for the script to download.</span></span>  
  
-   <span data-ttu-id="00b0c-117">Credenziali usate dal sistema per accedere al proxy.</span><span class="sxs-lookup"><span data-stu-id="00b0c-117">Which credentials your system should use to access the proxy.</span></span>  
  
-   <span data-ttu-id="00b0c-118">Credenziali usate dal sistema per il download dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00b0c-118">Which credentials your system should use to download the configuration script.</span></span>  
  
 <span data-ttu-id="00b0c-119">Le modifiche nell'ambiente di rete possono richiedere che il sistema usi un nuovo set di proxy.</span><span class="sxs-lookup"><span data-stu-id="00b0c-119">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="00b0c-120">Se una connessione di rete non funziona o viene inizializzata una nuova connessione di rete, il sistema deve individuare l'origine appropriata dello script di configurazione nel nuovo ambiente ed eseguire il nuovo script.</span><span class="sxs-lookup"><span data-stu-id="00b0c-120">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="00b0c-121">La tabella seguente mostra le opzioni di configurazione per un proxy adattivo.</span><span class="sxs-lookup"><span data-stu-id="00b0c-121">The following table shows configuration options for an adaptive proxy.</span></span>  
  
|<span data-ttu-id="00b0c-122">Impostazione di attributo, proprietà o file di configurazione</span><span class="sxs-lookup"><span data-stu-id="00b0c-122">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="00b0c-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00b0c-123">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|<span data-ttu-id="00b0c-124">Tempo trascorso in secondi tra i download dello script.</span><span class="sxs-lookup"><span data-stu-id="00b0c-124">Elapsed time in seconds between script downloads.</span></span>|  
|`scriptDownloadTimeout`|<span data-ttu-id="00b0c-125">Tempo di attesa (in secondi) per il download dello script.</span><span class="sxs-lookup"><span data-stu-id="00b0c-125">Time to wait (in seconds) for the script to download.</span></span>|  
|<span data-ttu-id="00b0c-126">`useDefaultCredentials` o <xref:System.Net.WebProxy.UseDefaultCredentials></span><span class="sxs-lookup"><span data-stu-id="00b0c-126">`useDefaultCredentials` or <xref:System.Net.WebProxy.UseDefaultCredentials></span></span>|<span data-ttu-id="00b0c-127">Controlla se il sistema usa le credenziali di rete predefinite per l'accesso a un proxy.</span><span class="sxs-lookup"><span data-stu-id="00b0c-127">Controls whether the system uses the default network credentials to access a proxy.</span></span>|  
|`useDefaultCredentialForScriptDownload`|<span data-ttu-id="00b0c-128">Controlla se il sistema usa le credenziali di rete predefinite per il download dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00b0c-128">Controls whether the system uses the default network credentials to download the configuration script.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="00b0c-129">Controlla se le impostazioni del proxy statico (indirizzo proxy, elenco di esclusione e opzione che specifica se ignorare il proxy per indirizzi locali) devono essere lette dalle impostazioni del proxy di Internet Explorer per l'utente.</span><span class="sxs-lookup"><span data-stu-id="00b0c-129">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="00b0c-130">Se questo valore è impostato su "true", verranno usate le impostazioni del proxy statico di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="00b0c-130">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span><br /><br /> <span data-ttu-id="00b0c-131">Se questo valore è "false" o non impostato, le impostazioni del proxy statico possono essere specificate nella configurazione e sostituiranno le impostazioni del proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="00b0c-131">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="00b0c-132">Questo valore deve essere impostato su "false" o non deve essere impostato anche per abilitare i proxy adattivi.</span><span class="sxs-lookup"><span data-stu-id="00b0c-132">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="00b0c-133">L'esempio seguente mostra una configurazione tipica di un proxy adattivo.</span><span class="sxs-lookup"><span data-stu-id="00b0c-133">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="00b0c-134">Proxy statici</span><span class="sxs-lookup"><span data-stu-id="00b0c-134">Static Proxies</span></span>  
 <span data-ttu-id="00b0c-135">I proxy statici in genere vengono configurati in modo esplicito da un'applicazione o quando un file di configurazione viene richiamato da un'applicazione o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="00b0c-135">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="00b0c-136">I proxy statici sono utili nelle reti in cui la topologia cambia raramente, ad esempio un computer desktop connesso a una rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="00b0c-136">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="00b0c-137">Diverse opzioni controllano il funzionamento di un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="00b0c-137">Several options control how a static proxy operates.</span></span> <span data-ttu-id="00b0c-138">È possibile specificare:</span><span class="sxs-lookup"><span data-stu-id="00b0c-138">You can specify the following:</span></span>  
  
-   <span data-ttu-id="00b0c-139">Indirizzo del proxy.</span><span class="sxs-lookup"><span data-stu-id="00b0c-139">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="00b0c-140">Valore che controlla se il proxy deve essere ignorato per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="00b0c-140">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="00b0c-141">Valore che controlla se il proxy deve essere ignorato per un set di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="00b0c-141">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="00b0c-142">La tabella seguente mostra le opzioni di configurazione di un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="00b0c-142">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="00b0c-143">Impostazione di attributo, proprietà o file di configurazione</span><span class="sxs-lookup"><span data-stu-id="00b0c-143">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="00b0c-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00b0c-144">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="00b0c-145">`proxyaddress` o <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="00b0c-145">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="00b0c-146">Indirizzo del proxy da usare.</span><span class="sxs-lookup"><span data-stu-id="00b0c-146">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="00b0c-147">`bypassonlocal` o <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="00b0c-147">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="00b0c-148">Valore che controlla se il proxy viene ignorato per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="00b0c-148">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="00b0c-149">`bypasslist` o <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="00b0c-149">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="00b0c-150">Descrive con espressioni regolari un set di indirizzi che ignorano il proxy.</span><span class="sxs-lookup"><span data-stu-id="00b0c-150">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="00b0c-151">Controlla se le impostazioni del proxy statico (indirizzo proxy, elenco di esclusione e opzione che specifica se ignorare il proxy per indirizzi locali) devono essere lette dalle impostazioni del proxy di Internet Explorer per l'utente.</span><span class="sxs-lookup"><span data-stu-id="00b0c-151">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="00b0c-152">Se questo valore è impostato su "true", verranno usate le impostazioni del proxy statico di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="00b0c-152">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="00b0c-153">In .NET Framework 2.0 quando questo valore è impostato su "true", le impostazioni del proxy di Internet Explorer non vengono sostituite dalle altre impostazioni del proxy specificate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00b0c-153">On .NET Framework 2.0 when this value is set to "true", the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="00b0c-154">In .NET Framework 1.1 le impostazioni del proxy di Internet Explorer possono essere sostituite dalle altre impostazioni del proxy specificate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00b0c-154">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="00b0c-155">Se questo valore è "false" o non impostato, le impostazioni del proxy statico possono essere specificate nella configurazione e sostituiranno le impostazioni del proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="00b0c-155">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="00b0c-156">Questo valore deve essere impostato su "false" o non deve essere impostato anche per abilitare i proxy adattivi.</span><span class="sxs-lookup"><span data-stu-id="00b0c-156">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="00b0c-157">L'esempio seguente illustra una configurazione tipica di un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="00b0c-157">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00b0c-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00b0c-158">See Also</span></span>  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.GlobalProxySelection>  
 [<span data-ttu-id="00b0c-159">Rilevamento automatico proxy</span><span class="sxs-lookup"><span data-stu-id="00b0c-159">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
