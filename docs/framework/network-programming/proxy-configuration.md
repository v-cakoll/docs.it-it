---
title: Configurazione proxy
ms.date: 06/18/2018
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
ms.openlocfilehash: 1fbfe25b90e810ff96924a2341582ff3f5ee5e5d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047362"
---
# <a name="proxy-configuration"></a><span data-ttu-id="2c885-102">Configurazione proxy</span><span class="sxs-lookup"><span data-stu-id="2c885-102">Proxy Configuration</span></span>
<span data-ttu-id="2c885-103">Un server proxy gestisce le richieste di risorse del client.</span><span class="sxs-lookup"><span data-stu-id="2c885-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="2c885-104">Un proxy può restituire una risorsa richiesta dalla cache o inoltrare la richiesta al server in cui risiede la risorsa.</span><span class="sxs-lookup"><span data-stu-id="2c885-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="2c885-105">I proxy possono migliorare le prestazioni della rete riducendo il numero di richieste inviate ai server remoti.</span><span class="sxs-lookup"><span data-stu-id="2c885-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="2c885-106">I proxy possono essere usati anche per limitare l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="2c885-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="2c885-107">Proxy adattivi</span><span class="sxs-lookup"><span data-stu-id="2c885-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="2c885-108">In .NET Framework i proxy possono essere di due tipi: adattivi e statici.</span><span class="sxs-lookup"><span data-stu-id="2c885-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="2c885-109">I proxy adattivi regolano le impostazioni quando viene modificata la configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="2c885-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="2c885-110">Ad esempio, se un utente avvia una connessione di rete remota sul laptop, un proxy adattivo riconosce questa modifica, individua ed esegue il nuovo script di configurazione e regola le impostazioni in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="2c885-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="2c885-111">I proxy adattivi vengono configurati con uno script di configurazione (vedere [Rilevamento automatico proxy](automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="2c885-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](automatic-proxy-detection.md)).</span></span> <span data-ttu-id="2c885-112">Lo script genera un set di protocolli di applicazioni e un proxy per ogni protocollo.</span><span class="sxs-lookup"><span data-stu-id="2c885-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="2c885-113">Le modifiche nell'ambiente di rete possono richiedere che il sistema usi un nuovo set di proxy.</span><span class="sxs-lookup"><span data-stu-id="2c885-113">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="2c885-114">Se una connessione di rete non funziona o viene inizializzata una nuova connessione di rete, il sistema deve individuare l'origine appropriata dello script di configurazione nel nuovo ambiente ed eseguire il nuovo script.</span><span class="sxs-lookup"><span data-stu-id="2c885-114">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="2c885-115">È possibile `usesystemdefault` utilizzare l'attributo dell'elemento [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2c885-115">You can use the `usesystemdefault` attribute of the [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) element in your configuration file.</span></span> <span data-ttu-id="2c885-116">L'attributo `usesystemdefault` controlla se le impostazioni del proxy statico (indirizzo proxy, elenco di esclusione e opzione che specifica se ignorare il proxy per indirizzi locali) devono essere lette dalle impostazioni del proxy di Internet Explorer per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2c885-116">The `usesystemdefault` attribute controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="2c885-117">Se questo valore è impostato su `true`, verranno usate le impostazioni del proxy statico di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c885-117">If this value is set to `true`, the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="2c885-118">Se questo valore è `false` o non impostato, le impostazioni del proxy statico possono essere specificate nella configurazione e sostituiranno le impostazioni del proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c885-118">If this value is `false` or not set, the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="2c885-119">Questo valore deve essere impostato su `false` o non deve essere impostato anche per abilitare i proxy adattivi.</span><span class="sxs-lookup"><span data-stu-id="2c885-119">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>  
  
 <span data-ttu-id="2c885-120">L'esempio seguente mostra una configurazione tipica di un proxy adattivo.</span><span class="sxs-lookup"><span data-stu-id="2c885-120">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="2c885-121">Proxy statici</span><span class="sxs-lookup"><span data-stu-id="2c885-121">Static Proxies</span></span>  
 <span data-ttu-id="2c885-122">I proxy statici in genere vengono configurati in modo esplicito da un'applicazione o quando un file di configurazione viene richiamato da un'applicazione o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2c885-122">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="2c885-123">I proxy statici sono utili nelle reti in cui la topologia cambia raramente, ad esempio un computer desktop connesso a una rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="2c885-123">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="2c885-124">Diverse opzioni controllano il funzionamento di un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="2c885-124">Several options control how a static proxy operates.</span></span> <span data-ttu-id="2c885-125">È possibile specificare:</span><span class="sxs-lookup"><span data-stu-id="2c885-125">You can specify the following:</span></span>  
  
- <span data-ttu-id="2c885-126">Indirizzo del proxy.</span><span class="sxs-lookup"><span data-stu-id="2c885-126">The address of the proxy.</span></span>  
  
- <span data-ttu-id="2c885-127">Valore che controlla se il proxy deve essere ignorato per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="2c885-127">Whether the proxy should be bypassed for local addresses.</span></span>  
  
- <span data-ttu-id="2c885-128">Valore che controlla se il proxy deve essere ignorato per un set di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="2c885-128">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="2c885-129">La tabella seguente mostra le opzioni di configurazione di un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="2c885-129">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="2c885-130">Impostazione di attributo, proprietà o file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2c885-130">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="2c885-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c885-131">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="2c885-132">`proxyaddress` o <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="2c885-132">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="2c885-133">Indirizzo del proxy da usare.</span><span class="sxs-lookup"><span data-stu-id="2c885-133">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="2c885-134">`bypassonlocal` o <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="2c885-134">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="2c885-135">Valore che controlla se il proxy viene ignorato per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="2c885-135">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="2c885-136">`bypasslist` o <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="2c885-136">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="2c885-137">Descrive con espressioni regolari un set di indirizzi che ignorano il proxy.</span><span class="sxs-lookup"><span data-stu-id="2c885-137">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="2c885-138">Controlla se le impostazioni del proxy statico (indirizzo proxy, elenco di esclusione e opzione che specifica se ignorare il proxy per indirizzi locali) devono essere lette dalle impostazioni del proxy di Internet Explorer per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2c885-138">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="2c885-139">Se questo valore è impostato su `true`, verranno usate le impostazioni del proxy statico di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c885-139">If this value is set to `true`, then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="2c885-140">In .NET Framework 2.0 quando questo valore è impostato su `true`, le impostazioni del proxy di Internet Explorer non vengono sostituite dalle altre impostazioni del proxy specificate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2c885-140">On .NET Framework 2.0 when this value is set to `true`, the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="2c885-141">In .NET Framework 1.1 le impostazioni del proxy di Internet Explorer possono essere sostituite dalle altre impostazioni del proxy specificate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2c885-141">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="2c885-142">Se questo valore è `false` o non impostato, le impostazioni del proxy statico possono essere specificate nella configurazione e sostituiranno le impostazioni del proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c885-142">If this value is `false` or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="2c885-143">Questo valore deve essere impostato su `false` o non deve essere impostato anche per abilitare i proxy adattivi.</span><span class="sxs-lookup"><span data-stu-id="2c885-143">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="2c885-144">L'esempio seguente illustra una configurazione tipica di un proxy statico.</span><span class="sxs-lookup"><span data-stu-id="2c885-144">The following example shows a typical static proxy configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c885-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c885-145">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [<span data-ttu-id="2c885-146">Rilevamento automatico proxy</span><span class="sxs-lookup"><span data-stu-id="2c885-146">Automatic Proxy Detection</span></span>](automatic-proxy-detection.md)
