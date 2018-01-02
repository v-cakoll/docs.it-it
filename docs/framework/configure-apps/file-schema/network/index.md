---
title: Schema delle impostazioni di rete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d8f13b75d0558c002fd29938ce98d85f358acc9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="network-settings-schema"></a><span data-ttu-id="8ad38-102">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="8ad38-102">Network Settings Schema</span></span>
<span data-ttu-id="8ad38-103">Tramite le impostazioni di rete viene specificata la modalità di connessione a Internet di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8ad38-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="8ad38-104">La tabella seguente descrive la funzione di ogni elemento di configurazione figlio dell'[elemento \<system.Net> (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8ad38-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="8ad38-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ad38-105">Element</span></span>|<span data-ttu-id="8ad38-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ad38-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ad38-107">Elemento \<authenticationModules> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8ad38-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="8ad38-108">Specifica i moduli usati per autenticare le richieste Internet.</span><span class="sxs-lookup"><span data-stu-id="8ad38-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="8ad38-109">Elemento \<connectionManagement> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8ad38-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="8ad38-110">Specifica il numero massimo di connessioni a host Internet.</span><span class="sxs-lookup"><span data-stu-id="8ad38-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="8ad38-111">Elemento \<defaultProxy> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8ad38-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="8ad38-112">Specifica il server proxy usato per le richieste HTTP indirizzate a Internet.</span><span class="sxs-lookup"><span data-stu-id="8ad38-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="8ad38-113">Elemento \<mailSettings> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8ad38-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="8ad38-114">Contiene le impostazioni per le opzioni di invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8ad38-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="8ad38-115">Elemento \<requestCaching> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8ad38-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="8ad38-116">Specifica i moduli usati per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="8ad38-116">Specifies the modules used to request information from Internet hosts.</span></span>|  
|[<span data-ttu-id="8ad38-117">Elemento \<requestCaching> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8ad38-117">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="8ad38-118">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8ad38-118">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>|  
|[<span data-ttu-id="8ad38-119">Elemento \<webRequestModules> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8ad38-119">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="8ad38-120">Specifica i moduli usati per richiedere informazioni da host Internet.</span><span class="sxs-lookup"><span data-stu-id="8ad38-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="8ad38-121">Tramite le impostazioni URI viene specificata la modalità di gestione da parte di .NET Framework degli indirizzi Web espressi tramite Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="8ad38-121">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="8ad38-122">La tabella seguente descrive la funzione di ogni elemento di configurazione figlio dell'[elemento \<Uri> (impostazioni URI)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8ad38-122">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="8ad38-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ad38-123">Element</span></span>|<span data-ttu-id="8ad38-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ad38-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ad38-125">Elemento \<idn> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="8ad38-125">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="8ad38-126">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="8ad38-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="8ad38-127">Elemento \<iriParsing> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="8ad38-127">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="8ad38-128">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="8ad38-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="8ad38-129">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="8ad38-129">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="8ad38-130">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="8ad38-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ad38-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ad38-131">See Also</span></span>  
 [<span data-ttu-id="8ad38-132">Configurazione di applicazioni Internet</span><span class="sxs-lookup"><span data-stu-id="8ad38-132">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [<span data-ttu-id="8ad38-133">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8ad38-133">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
