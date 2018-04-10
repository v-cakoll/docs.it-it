---
title: Dettagli delle funzionalità di WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- features [WCF]
- WCF, features
- Windows Communication Foundation, features
ms.assetid: 9b4368ca-0bd3-40dc-a539-bcd5779cee5f
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2aa8adc0ce197c3776b8314009fcaa061bed884d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-feature-details"></a><span data-ttu-id="d8463-102">Dettagli delle funzionalità di WCF</span><span class="sxs-lookup"><span data-stu-id="d8463-102">WCF Feature Details</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="d8463-103"> consente di esercitare un controllo esteso sulle funzioni di messaggistica di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8463-103"> allows extensive control over the messaging functions of an application.</span></span> <span data-ttu-id="d8463-104">Negli argomenti contenuti in questa sezione vengono descritte in dettaglio le funzionalità disponibili.</span><span class="sxs-lookup"><span data-stu-id="d8463-104">The topics in this section go into detail about the available features.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d8463-105">Vedere programmazione, base [programmazione WCF di base](../../../../docs/framework/wcf/basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="d8463-105"> basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8463-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d8463-106">In This Section</span></span>  
 [<span data-ttu-id="d8463-107">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8463-107">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 <span data-ttu-id="d8463-108">Viene illustrato come creare e configurare servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8463-108">Describes how to create and configure workflow services.</span></span>  
  
 [<span data-ttu-id="d8463-109">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="d8463-109">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 <span data-ttu-id="d8463-110">Viene descritto come controllare più aspetti del servizio.</span><span class="sxs-lookup"><span data-stu-id="d8463-110">Describes how to control multiple aspects of your service.</span></span>  
  
 [<span data-ttu-id="d8463-111">Trasferimento e serializzazione dei dati</span><span class="sxs-lookup"><span data-stu-id="d8463-111">Data Transfer and Serialization</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)  
 <span data-ttu-id="d8463-112">Viene spiegato come la serializzazione dei dati possa essere adattata per l'interoperatività o la compatibilità futura.</span><span class="sxs-lookup"><span data-stu-id="d8463-112">Describes how serialization of data can be tailored for interoperation or future compatibility.</span></span>  
  
 [<span data-ttu-id="d8463-113">Sessioni, istanze e concorrenza</span><span class="sxs-lookup"><span data-stu-id="d8463-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 <span data-ttu-id="d8463-114">Vengono descritte la modalità di creazione di istanze e la modalità di sessione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e viene spiegato come selezionare la modalità appropriata per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8463-114">Describes the instancing and session modes of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and how to select the right mode for your application.</span></span>  
  
 [<span data-ttu-id="d8463-115">Trasporti</span><span class="sxs-lookup"><span data-stu-id="d8463-115">Transports</span></span>](../../../../docs/framework/wcf/feature-details/transports.md)  
 <span data-ttu-id="d8463-116">Viene descritto come configurare il livello di trasporto, il livello più basso dello stack dei canali.</span><span class="sxs-lookup"><span data-stu-id="d8463-116">Describes how to configure the transport layer, the lowest level of the channel stack.</span></span>  
  
 [<span data-ttu-id="d8463-117">Code e sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="d8463-117">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)  
 <span data-ttu-id="d8463-118">Vengono descritte le code, che archiviano i messaggi provenienti da un'applicazione di origine per conto di un'applicazione ricevente e in seguito li inoltrano all'applicazione ricevente.</span><span class="sxs-lookup"><span data-stu-id="d8463-118">Describes queues, which store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span>  
  
 [<span data-ttu-id="d8463-119">Transazioni</span><span class="sxs-lookup"><span data-stu-id="d8463-119">Transactions</span></span>](../../../../docs/framework/wcf/feature-details/transactions-in-wcf.md)  
 <span data-ttu-id="d8463-120">Viene spiegato come creare operazioni transazionali per le quali, se necessario, è possibile eseguire il rollback.</span><span class="sxs-lookup"><span data-stu-id="d8463-120">Explains how to create transacted operations that can be rolled back if needed.</span></span>  
  
 [<span data-ttu-id="d8463-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8463-121">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 <span data-ttu-id="d8463-122">Viene descritto come la sicurezza [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consenta di creare applicazioni che garantiscono riservatezza e integrità.</span><span class="sxs-lookup"><span data-stu-id="d8463-122">Describes how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security helps you to create applications that have confidentiality and integrity.</span></span> <span data-ttu-id="d8463-123">Sono inoltre disponibili autenticazione e autorizzazione, nonché funzionalità di controllo.</span><span class="sxs-lookup"><span data-stu-id="d8463-123">Authentication and authorization are also available, as are auditing features.</span></span>  
  
 [<span data-ttu-id="d8463-124">Reti peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="d8463-124">Peer-to-Peer Networking</span></span>](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 <span data-ttu-id="d8463-125">Viene spiegato dettagliatamente come creare servizi e client peer.</span><span class="sxs-lookup"><span data-stu-id="d8463-125">Details how to create peer services and clients.</span></span>  
  
 [<span data-ttu-id="d8463-126">Metadati</span><span class="sxs-lookup"><span data-stu-id="d8463-126">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 <span data-ttu-id="d8463-127">Vengono descritti l'architettura e i formati dei metadati.</span><span class="sxs-lookup"><span data-stu-id="d8463-127">Describes metadata architecture and formats.</span></span>  
  
 [<span data-ttu-id="d8463-128">Client</span><span class="sxs-lookup"><span data-stu-id="d8463-128">Clients</span></span>](../../../../docs/framework/wcf/feature-details/clients.md)  
 <span data-ttu-id="d8463-129">Viene descritto come creare una varietà di client che accedono a servizi.</span><span class="sxs-lookup"><span data-stu-id="d8463-129">Describes how to create a variety of clients that access services.</span></span>  
  
 [<span data-ttu-id="d8463-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="d8463-130">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 <span data-ttu-id="d8463-131">Viene descritto l'hosting.</span><span class="sxs-lookup"><span data-stu-id="d8463-131">Describes hosting.</span></span> <span data-ttu-id="d8463-132">Un servizio può essere ospitato da un'altra applicazione o essere indipendente.</span><span class="sxs-lookup"><span data-stu-id="d8463-132">A service can be hosted by another application, or it can be self-hosted.</span></span>  
  
 [<span data-ttu-id="d8463-133">Interoperabilità e integrazione</span><span class="sxs-lookup"><span data-stu-id="d8463-133">Interoperability and Integration</span></span>](../../../../docs/framework/wcf/feature-details/interoperability-and-integration.md)  
 <span data-ttu-id="d8463-134">Viene descritto come utilizzare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per estendere la logica esistente anziché riscriverla, nel caso in cui si disponga di una grande quantità di logica di applicazione basata sul componente in COM+.</span><span class="sxs-lookup"><span data-stu-id="d8463-134">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to extend your existing logic rather than having to rewrite it if you have a substantial investment in component-based application logic hosted in COM+.</span></span>  
  
 [<span data-ttu-id="d8463-135">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="d8463-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 <span data-ttu-id="d8463-136">Viene descritto il modello di programmazione Web [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che consente agli sviluppatori di esporre operazioni del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] agli endpoint non-SOAP.</span><span class="sxs-lookup"><span data-stu-id="d8463-136">Describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Programming Model that allows developers to expose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service operations to non-SOAP endpoints.</span></span>  
  
 [<span data-ttu-id="d8463-137">Diffusione WCF</span><span class="sxs-lookup"><span data-stu-id="d8463-137">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)  
 <span data-ttu-id="d8463-138">Viene descritto il supporto che consente di esporre facilmente feed di diffusione da un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8463-138">Describes support to easily expose syndication feeds from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [<span data-ttu-id="d8463-139">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="d8463-139">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 <span data-ttu-id="d8463-140">Viene descritto il supporto per il formato dati AJAX (Asynchronous JavaScript e XML) ASP.NET e JSON (JavaScript Object Notation) per consentire ai servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di esporre operazioni ai client AJAX.</span><span class="sxs-lookup"><span data-stu-id="d8463-140">Describes support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format to allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span>  
  
 [<span data-ttu-id="d8463-141">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="d8463-141">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
 <span data-ttu-id="d8463-142">Viene descritto il supporto per consentire ai servizi di essere individuabile in fase di runtime in una modalità interoperativa utilizzando il protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="d8463-142">Describes support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span>  
  
 [<span data-ttu-id="d8463-143">Routing</span><span class="sxs-lookup"><span data-stu-id="d8463-143">Routing</span></span>](../../../../docs/framework/wcf/feature-details/routing.md)  
 <span data-ttu-id="d8463-144">Viene descritto il servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="d8463-144">Describes the routing service.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d8463-145">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="d8463-145">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.ServiceModel.Routing>  
  
## <a name="related-sections"></a><span data-ttu-id="d8463-146">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d8463-146">Related Sections</span></span>  
 [<span data-ttu-id="d8463-147">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="d8463-147">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
