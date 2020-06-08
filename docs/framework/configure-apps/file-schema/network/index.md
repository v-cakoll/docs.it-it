---
title: Schema delle impostazioni di rete
description: Informazioni sullo schema per le impostazioni di rete che specificano il modo in cui il .NET Framework si connette a Internet e gestisce gli URI.
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 6a22d7f1608db2e8909d0ead11e9110ec8a8a2c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504576"
---
# <a name="network-settings-schema"></a><span data-ttu-id="175ad-103">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="175ad-103">Network Settings Schema</span></span>
<span data-ttu-id="175ad-104">Tramite le impostazioni di rete viene specificata la modalità di connessione a Internet di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="175ad-104">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="175ad-105">Le \<system.net> impostazioni specificano il modo in cui il .NET Framework si connette alla rete.</span><span class="sxs-lookup"><span data-stu-id="175ad-105">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="175ad-106">Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [ \<system.Net> elemento (impostazioni di rete)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="175ad-106">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="175ad-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="175ad-107">Element</span></span>|<span data-ttu-id="175ad-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="175ad-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="175ad-109">\<authenticationModules>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="175ad-109">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="175ad-110">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="175ad-110">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="175ad-111">\<connectionManagement>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="175ad-111">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="175ad-112">Specifica il numero massimo di connessioni a host Internet.</span><span class="sxs-lookup"><span data-stu-id="175ad-112">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="175ad-113">\<defaultProxy>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="175ad-113">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="175ad-114">Specifica il server proxy usato per le richieste HTTP indirizzate a Internet.</span><span class="sxs-lookup"><span data-stu-id="175ad-114">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="175ad-115">\<mailSettings>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="175ad-115">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="175ad-116">Contiene le impostazioni per le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="175ad-116">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="175ad-117">\<requestCaching>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="175ad-117">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="175ad-118">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="175ad-118">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="175ad-119">\<webRequestModules>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="175ad-119">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="175ad-120">Specifica i moduli usati per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="175ad-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="175ad-121">Le \<uri> impostazioni specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="175ad-121">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="175ad-122">Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [ \<uri> elemento (impostazioni URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="175ad-122">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="175ad-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="175ad-123">Element</span></span>|<span data-ttu-id="175ad-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="175ad-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="175ad-125">\<idn>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="175ad-125">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="175ad-126">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="175ad-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="175ad-127">\<iriParsing>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="175ad-127">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="175ad-128">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="175ad-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="175ad-129">\<schemeSettings>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="175ad-129">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="175ad-130">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="175ad-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="175ad-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="175ad-131">See also</span></span>

- [<span data-ttu-id="175ad-132">Configurazione di applicazioni Internet</span><span class="sxs-lookup"><span data-stu-id="175ad-132">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="175ad-133">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="175ad-133">Configuration File Schema</span></span>](../index.md)
