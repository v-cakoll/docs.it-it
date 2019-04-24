---
title: Abilitazione e disabilitazione di IPv6
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 73dee0cb57674c8a2fa4ba2246162870ab1e3a10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083686"
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="6460a-102">Abilitazione e disabilitazione di IPv6</span><span class="sxs-lookup"><span data-stu-id="6460a-102">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="6460a-103">Per usare il protocollo IPv6, assicurarsi di eseguire una versione del sistema operativo che supporti IPv6 e che il sistema operativo e le classi di rete siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="6460a-103">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="6460a-104">Procedura di configurazione</span><span class="sxs-lookup"><span data-stu-id="6460a-104">Configuration Steps</span></span>  
 <span data-ttu-id="6460a-105">La tabella seguente elenca diverse configurazioni</span><span class="sxs-lookup"><span data-stu-id="6460a-105">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="6460a-106">Sistema operativo abilitato per IPv6</span><span class="sxs-lookup"><span data-stu-id="6460a-106">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="6460a-107">Classi di rete abilitate per IPv6</span><span class="sxs-lookup"><span data-stu-id="6460a-107">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="6460a-108">Description</span><span class="sxs-lookup"><span data-stu-id="6460a-108">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="6460a-109">No</span><span class="sxs-lookup"><span data-stu-id="6460a-109">No</span></span>|<span data-ttu-id="6460a-110">No</span><span class="sxs-lookup"><span data-stu-id="6460a-110">No</span></span>|<span data-ttu-id="6460a-111">È possibile analizzare gli indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="6460a-111">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="6460a-112">No</span><span class="sxs-lookup"><span data-stu-id="6460a-112">No</span></span>|<span data-ttu-id="6460a-113">Sì</span><span class="sxs-lookup"><span data-stu-id="6460a-113">Yes</span></span>|<span data-ttu-id="6460a-114">È possibile analizzare gli indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="6460a-114">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="6460a-115">Sì</span><span class="sxs-lookup"><span data-stu-id="6460a-115">Yes</span></span>|<span data-ttu-id="6460a-116">No</span><span class="sxs-lookup"><span data-stu-id="6460a-116">No</span></span>|<span data-ttu-id="6460a-117">È possibile analizzare gli indirizzi IPv6 e risolvere gli indirizzi IPv6 usando metodi di risoluzione dei nomi non contrassegnati come obsoleti.</span><span class="sxs-lookup"><span data-stu-id="6460a-117">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="6460a-118">Sì</span><span class="sxs-lookup"><span data-stu-id="6460a-118">Yes</span></span>|<span data-ttu-id="6460a-119">Sì</span><span class="sxs-lookup"><span data-stu-id="6460a-119">Yes</span></span>|<span data-ttu-id="6460a-120">È possibile analizzare e risolvere gli indirizzi IPv6 usando tutti i metodi, inclusi quelli contrassegnati come obsoleti.</span><span class="sxs-lookup"><span data-stu-id="6460a-120">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="6460a-121">Tenere presente che, per abilitare il supporto IPv6 per tutte le classi nello spazio dei nomi System.Net, è necessario modificare il file di configurazione del computer o il file di configurazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6460a-121">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="6460a-122">Il file di configurazione per un'applicazione ha la precedenza sul file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="6460a-122">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="6460a-123">Per un esempio di modifica del file di configurazione del computer, *machine.config*, per abilitare il supporto Ipv6, vedere [Procedura: Modificare il file di configurazione del computer per abilitare il supporto Ipv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="6460a-123">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="6460a-124">Verificare anche che il supporto IPv6 sia abilitato per il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6460a-124">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="6460a-125">.NET Framework ha un'opzione di configurazione impostata in un file di configurazione nel modo seguente</span><span class="sxs-lookup"><span data-stu-id="6460a-125">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
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
  
 <span data-ttu-id="6460a-126">Per .NET Framework versione 1.1 e versioni precedenti, il valore dell'opzione di configurazione **ipv6 enabled** specifica se i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> restituiscono indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="6460a-126">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="6460a-127">Per .NET Framework versione 2.0 e versioni successive, se Windows supporta IPv6, i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) restituiscono indirizzi IPv6 con una limitazione.</span><span class="sxs-lookup"><span data-stu-id="6460a-127">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="6460a-128">I membri obsoleti del DNS <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leggeranno e riconosceranno il valore nel file di configurazione per l'impostazione abilitata per ipv6.</span><span class="sxs-lookup"><span data-stu-id="6460a-128">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6460a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6460a-129">See also</span></span>

- [<span data-ttu-id="6460a-130">Protocollo IPv6</span><span class="sxs-lookup"><span data-stu-id="6460a-130">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)
- [<span data-ttu-id="6460a-131">Socket</span><span class="sxs-lookup"><span data-stu-id="6460a-131">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
- [<span data-ttu-id="6460a-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="6460a-132">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="6460a-133">Elemento \<ipv6> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6460a-133">\<ipv6> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
