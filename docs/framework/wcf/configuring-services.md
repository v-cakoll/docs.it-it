---
title: Configurazione dei servizi WCF
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 81727adbf985986a71cc9f9e2d42a1de0cb1fd76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608536"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="b68de-102">Configurazione dei servizi WCF</span><span class="sxs-lookup"><span data-stu-id="b68de-102">Configuring WCF services</span></span>

<span data-ttu-id="b68de-103">Dopo aver progettato e implementato il contratto di servizio, è possibile configurare il servizio.</span><span class="sxs-lookup"><span data-stu-id="b68de-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="b68de-104">Questa è la fase in cui si definisce e si personalizza il modo in cui il servizio viene esposto ai client, inclusa l'indicazione dell'indirizzo, del trasporto e della codifica dei messaggi usata per inviare e ricevere messaggi e del tipo di sicurezza richiesto.</span><span class="sxs-lookup"><span data-stu-id="b68de-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="b68de-105">La configurazione specificata in questo punto include tutti i modi, imperativo nel codice o mediante un file di configurazione, in cui è possibile definire e personalizzare i vari aspetti di un servizio, ad esempio la specifica degli indirizzi dell'endpoint, dei trasporti usati e degli schemi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b68de-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="b68de-106">In pratica, la creazione della configurazione è un'importante parte della programmazione di applicazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="b68de-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b68de-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b68de-107">In This Section</span></span>  
 [<span data-ttu-id="b68de-108">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="b68de-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="b68de-109">A partire da [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF viene fornito con un nuovo modello di configurazione predefinito che semplifica i requisiti di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="b68de-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="b68de-110">Se non si specifica alcuna configurazione di WCF per un determinato servizio, il runtime configura automaticamente il servizio con i comportamenti, associazioni e gli endpoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b68de-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="b68de-111">Configurazione dei servizi tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b68de-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="b68de-112">È un servizio di Windows Communication Foundation (WCF) può essere configurato utilizzando il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] la tecnologia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b68de-112">A Windows Communication Foundation (WCF) service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="b68de-113">In genere, gli elementi XML vengono aggiunti al file Web. config per un sito Internet Information Services (IIS) che ospita un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="b68de-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="b68de-114">Gli elementi consentono di modificare i dettagli, ad esempio gli indirizzi dell'endpoint (gli indirizzi effettivi usati per comunicare con il servizio) per i singoli computer.</span><span class="sxs-lookup"><span data-stu-id="b68de-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="b68de-115">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b68de-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="b68de-116">Inoltre, WCF include numerose configurazioni comuni fornite dal sistema sotto forma di associazioni che consentono di selezionare rapidamente le funzionalità di base per la comunicazione tra client e servizio, ad esempio i trasporti, sicurezza e messaggio codifiche utilizzate.</span><span class="sxs-lookup"><span data-stu-id="b68de-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="b68de-117">Endpoint</span><span class="sxs-lookup"><span data-stu-id="b68de-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="b68de-118">Si verifica tutte le comunicazioni con un servizio WCF tramite il *endpoint* del servizio.</span><span class="sxs-lookup"><span data-stu-id="b68de-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="b68de-119">Gli endpoint contengono il contratto, le informazioni di configurazione specificate nelle associazioni e gli indirizzi che indicano dove si trova il servizio o dove ottenere informazioni sul servizio.</span><span class="sxs-lookup"><span data-stu-id="b68de-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="b68de-120">Protezione dei servizi</span><span class="sxs-lookup"><span data-stu-id="b68de-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="b68de-121">Utilizzo di WCF e con meccanismi di sicurezza, è possibile implementare la riservatezza, integrità, l'autenticazione e autorizzazione in qualsiasi servizio.</span><span class="sxs-lookup"><span data-stu-id="b68de-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="b68de-122">È inoltre possibile controllare le attività di sicurezza riuscite e non riuscite.</span><span class="sxs-lookup"><span data-stu-id="b68de-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="b68de-123">Creazione di servizi interoperativi WS-I Basic Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="b68de-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="b68de-124">I requisiti per la distribuzione di un servizio che sia interoperativo con i servizi e i client su qualsiasi altra piattaforma o sistema operativo sono delineati nella specifica WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="b68de-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b68de-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="b68de-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="b68de-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b68de-126">Related Sections</span></span>  
 [<span data-ttu-id="b68de-127">Ciclo di vita della programmazione di base</span><span class="sxs-lookup"><span data-stu-id="b68de-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="b68de-128">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="b68de-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="b68de-129">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="b68de-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="b68de-130">Creazione di client</span><span class="sxs-lookup"><span data-stu-id="b68de-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="b68de-131">Introduzione all'estendibilità</span><span class="sxs-lookup"><span data-stu-id="b68de-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="b68de-132">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="b68de-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="b68de-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b68de-133">See also</span></span>

- [<span data-ttu-id="b68de-134">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="b68de-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="b68de-135">Panoramica dei concetti</span><span class="sxs-lookup"><span data-stu-id="b68de-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="b68de-136">Dettagli delle funzionalità di WCF</span><span class="sxs-lookup"><span data-stu-id="b68de-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
