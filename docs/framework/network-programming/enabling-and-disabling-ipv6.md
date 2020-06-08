---
title: Abilitazione e disabilitazione di IPv6
description: Seguire questi passaggi di configurazione per abilitare l'uso del protocollo IPv6, inclusa la modifica del file di configurazione per il computer o per l'applicazione.
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 7729647b09df20a98d5d639a641cb0a31f557330
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502613"
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="eda7e-103">Abilitazione e disabilitazione di IPv6</span><span class="sxs-lookup"><span data-stu-id="eda7e-103">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="eda7e-104">Per usare il protocollo IPv6, assicurarsi di eseguire una versione del sistema operativo che supporti IPv6 e che il sistema operativo e le classi di rete siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="eda7e-104">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="eda7e-105">Procedura di configurazione</span><span class="sxs-lookup"><span data-stu-id="eda7e-105">Configuration Steps</span></span>  
 <span data-ttu-id="eda7e-106">La tabella seguente elenca diverse configurazioni</span><span class="sxs-lookup"><span data-stu-id="eda7e-106">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="eda7e-107">Sistema operativo abilitato per IPv6</span><span class="sxs-lookup"><span data-stu-id="eda7e-107">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="eda7e-108">Classi di rete abilitate per IPv6</span><span class="sxs-lookup"><span data-stu-id="eda7e-108">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="eda7e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eda7e-109">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="eda7e-110">No</span><span class="sxs-lookup"><span data-stu-id="eda7e-110">No</span></span>|<span data-ttu-id="eda7e-111">No</span><span class="sxs-lookup"><span data-stu-id="eda7e-111">No</span></span>|<span data-ttu-id="eda7e-112">È possibile analizzare gli indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="eda7e-112">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="eda7e-113">No</span><span class="sxs-lookup"><span data-stu-id="eda7e-113">No</span></span>|<span data-ttu-id="eda7e-114">Sì</span><span class="sxs-lookup"><span data-stu-id="eda7e-114">Yes</span></span>|<span data-ttu-id="eda7e-115">È possibile analizzare gli indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="eda7e-115">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="eda7e-116">Sì</span><span class="sxs-lookup"><span data-stu-id="eda7e-116">Yes</span></span>|<span data-ttu-id="eda7e-117">No</span><span class="sxs-lookup"><span data-stu-id="eda7e-117">No</span></span>|<span data-ttu-id="eda7e-118">È possibile analizzare gli indirizzi IPv6 e risolvere gli indirizzi IPv6 usando metodi di risoluzione dei nomi non contrassegnati come obsoleti.</span><span class="sxs-lookup"><span data-stu-id="eda7e-118">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="eda7e-119">Sì</span><span class="sxs-lookup"><span data-stu-id="eda7e-119">Yes</span></span>|<span data-ttu-id="eda7e-120">Sì</span><span class="sxs-lookup"><span data-stu-id="eda7e-120">Yes</span></span>|<span data-ttu-id="eda7e-121">È possibile analizzare e risolvere gli indirizzi IPv6 usando tutti i metodi, inclusi quelli contrassegnati come obsoleti.</span><span class="sxs-lookup"><span data-stu-id="eda7e-121">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="eda7e-122">Tenere presente che, per abilitare il supporto IPv6 per tutte le classi nello spazio dei nomi System.Net, è necessario modificare il file di configurazione del computer o il file di configurazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eda7e-122">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="eda7e-123">Il file di configurazione per un'applicazione ha la precedenza sul file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="eda7e-123">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="eda7e-124">Per un esempio di come modificare il file di configurazione del computer, *machine.config*, per abilitare il supporto Ipv6, vedere [Procedura: Modificare il file di configurazione del computer per abilitare il supporto IPv6](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="eda7e-124">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="eda7e-125">Verificare anche che il supporto IPv6 sia abilitato per il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eda7e-125">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="eda7e-126">.NET Framework ha un'opzione di configurazione impostata in un file di configurazione nel modo seguente</span><span class="sxs-lookup"><span data-stu-id="eda7e-126">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 <span data-ttu-id="eda7e-127">Per .NET Framework versione 1.1 e versioni precedenti, il valore dell'opzione di configurazione **ipv6 enabled** specifica se i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> restituiscono indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="eda7e-127">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="eda7e-128">Per .NET Framework versione 2.0 e versioni successive, se Windows supporta IPv6, i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) restituiscono indirizzi IPv6 con una limitazione.</span><span class="sxs-lookup"><span data-stu-id="eda7e-128">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="eda7e-129">I membri obsoleti del DNS <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leggeranno e riconosceranno il valore nel file di configurazione per l'impostazione abilitata per ipv6.</span><span class="sxs-lookup"><span data-stu-id="eda7e-129">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda7e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eda7e-130">See also</span></span>

- [<span data-ttu-id="eda7e-131">Protocollo IP versione 6</span><span class="sxs-lookup"><span data-stu-id="eda7e-131">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="eda7e-132">Socket</span><span class="sxs-lookup"><span data-stu-id="eda7e-132">Sockets</span></span>](sockets.md)
- [<span data-ttu-id="eda7e-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="eda7e-133">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="eda7e-134">\<ipv6>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="eda7e-134">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
