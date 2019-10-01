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
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698157"
---
# <a name="network-settings-schema"></a><span data-ttu-id="6ddfa-102">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="6ddfa-102">Network Settings Schema</span></span>
<span data-ttu-id="6ddfa-103">Tramite le impostazioni di rete viene specificata la modalità di connessione a Internet di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-103">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="6ddfa-104">Le impostazioni @no__t -0system. net > specificano il modo in cui il .NET Framework si connette alla rete.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-104">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="6ddfa-105">La tabella seguente descrive la funzione di ogni elemento di configurazione figlio dell'[elemento \<system.Net> (impostazioni di rete)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6ddfa-105">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="6ddfa-106">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ddfa-106">Element</span></span>|<span data-ttu-id="6ddfa-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ddfa-107">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ddfa-108">Elemento \<authenticationModules> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-108">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="6ddfa-109">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-109">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="6ddfa-110">Elemento \<connectionManagement> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-110">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="6ddfa-111">Specifica il numero massimo di connessioni a host Internet.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-111">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="6ddfa-112">Elemento \<defaultProxy> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-112">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="6ddfa-113">Specifica il server proxy usato per le richieste HTTP indirizzate a Internet.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-113">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="6ddfa-114">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-114">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="6ddfa-115">Contiene le impostazioni per le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-115">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="6ddfa-116">Elemento \<requestCaching> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-116">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="6ddfa-117">Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-117">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="6ddfa-118">Elemento \<webRequestModules> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-118">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="6ddfa-119">Specifica i moduli usati per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-119">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="6ddfa-120">Le impostazioni di > \<uri specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="6ddfa-120">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="6ddfa-121">Nella tabella seguente viene descritta la funzione di ogni elemento di configurazione figlio sotto l' [elemento \<uri > (impostazioni URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6ddfa-121">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="6ddfa-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ddfa-122">Element</span></span>|<span data-ttu-id="6ddfa-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ddfa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ddfa-124">Elemento \<idn> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-124">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="6ddfa-125">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-125">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="6ddfa-126">Elemento \<iriParsing> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-126">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="6ddfa-127">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-127">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="6ddfa-128">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="6ddfa-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="6ddfa-129">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="6ddfa-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ddfa-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ddfa-130">See also</span></span>

- [<span data-ttu-id="6ddfa-131">Configurazione di applicazioni Internet</span><span class="sxs-lookup"><span data-stu-id="6ddfa-131">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="6ddfa-132">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6ddfa-132">Configuration File Schema</span></span>](../index.md)
