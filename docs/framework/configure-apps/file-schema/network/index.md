---
title: Schema delle impostazioni di rete
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
ms.openlocfilehash: 5e3bd1b1734fc7fba50b72785531a8b001d6d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698157"
---
# <a name="network-settings-schema"></a><span data-ttu-id="2d923-102">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="2d923-102">Network Settings Schema</span></span>
<span data-ttu-id="2d923-103">Tramite le impostazioni di rete viene specificata la modalità di connessione a Internet di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d923-103">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="2d923-104">Le \<system.net> impostazioni specificano il modo in cui il .NET Framework si connette alla rete.</span><span class="sxs-lookup"><span data-stu-id="2d923-104">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="2d923-105">Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [ \<system.Net> elemento (impostazioni di rete)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2d923-105">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="2d923-106">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d923-106">Element</span></span>|<span data-ttu-id="2d923-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d923-107">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d923-108">\<authenticationModules>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d923-108">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="2d923-109">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="2d923-109">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="2d923-110">\<connectionManagement>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d923-110">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="2d923-111">Specifica il numero massimo di connessioni a host Internet.</span><span class="sxs-lookup"><span data-stu-id="2d923-111">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="2d923-112">\<defaultProxy>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d923-112">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2d923-113">Specifica il server proxy usato per le richieste HTTP indirizzate a Internet.</span><span class="sxs-lookup"><span data-stu-id="2d923-113">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="2d923-114">\<mailSettings>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d923-114">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="2d923-115">Contiene le impostazioni per le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2d923-115">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="2d923-116">\<requestCaching>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d923-116">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="2d923-117">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="2d923-117">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="2d923-118">\<webRequestModules>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2d923-118">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="2d923-119">Specifica i moduli usati per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="2d923-119">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="2d923-120">Le \<uri> impostazioni specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="2d923-120">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="2d923-121">Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [ \<uri> elemento (impostazioni URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2d923-121">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="2d923-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d923-122">Element</span></span>|<span data-ttu-id="2d923-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d923-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d923-124">\<idn>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="2d923-124">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="2d923-125">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="2d923-125">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="2d923-126">\<iriParsing>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="2d923-126">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="2d923-127">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="2d923-127">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="2d923-128">\<schemeSettings>Elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="2d923-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="2d923-129">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="2d923-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d923-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2d923-130">See also</span></span>

- [<span data-ttu-id="2d923-131">Configurazione di applicazioni Internet</span><span class="sxs-lookup"><span data-stu-id="2d923-131">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="2d923-132">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2d923-132">Configuration File Schema</span></span>](../index.md)
