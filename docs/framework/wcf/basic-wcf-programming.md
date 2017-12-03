---
title: Programmazione WCF di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 83404a56de68de8f8aec271c28e9896c4fa8702b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="636c0-102">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="636c0-102">Basic WCF Programming</span></span>
<span data-ttu-id="636c0-103">Contenuto della sezione vengono illustrati i principi per la creazione di applicazioni [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="636c0-103">This section presents the fundamentals for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="636c0-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="636c0-104">In This Section</span></span>  
 [<span data-ttu-id="636c0-105">Ciclo di vita della programmazione di base</span><span class="sxs-lookup"><span data-stu-id="636c0-105">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 <span data-ttu-id="636c0-106">Descrive il ciclo di vita relativo alla progettazione, generazione e distribuzione di applicazioni di servizio e client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="636c0-106">Describes the lifecycle of designing, building, and deploying [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service and client applications.</span></span>  
  
 [<span data-ttu-id="636c0-107">Progettazione e implementazione di servizi</span><span class="sxs-lookup"><span data-stu-id="636c0-107">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 <span data-ttu-id="636c0-108">Descrive come progettare e implementare un contratto di servizio, scegliere un modello per lo scambio di messaggi, specificare un contratto di errore e altri aspetti di base dei servizi.</span><span class="sxs-lookup"><span data-stu-id="636c0-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>  
  
 [<span data-ttu-id="636c0-109">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="636c0-109">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 <span data-ttu-id="636c0-110">Descrive come configurare un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per supportare i requisiti del contratto, personalizzare il comportamento in fase di esecuzione locale e indicare l'indirizzo per pubblicare il servizio.</span><span class="sxs-lookup"><span data-stu-id="636c0-110">Describes how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>  
  
 [<span data-ttu-id="636c0-111">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="636c0-111">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 <span data-ttu-id="636c0-112">Descrive le caratteristiche fondamentali dei servizi host in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="636c0-112">Describes the basics of hosting services in an application.</span></span>  
  
 [<span data-ttu-id="636c0-113">Creazione di client</span><span class="sxs-lookup"><span data-stu-id="636c0-113">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 <span data-ttu-id="636c0-114">Descrive come ottenere metadati dai servizi, convertirli in codice client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], gestire problemi di sicurezza e generare, configurare e ospitare un client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="636c0-114">Describes how to obtain metadata from services, convert that into [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code, handle security issues, and build, configure, and host an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span>  
  
 [<span data-ttu-id="636c0-115">Introduzione all'estendibilità</span><span class="sxs-lookup"><span data-stu-id="636c0-115">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
 <span data-ttu-id="636c0-116">Descrive come estendere [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per creare soluzioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="636c0-116">Describes how to extend [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] to create custom solutions.</span></span>  
  
 [<span data-ttu-id="636c0-117">Guida rapida alla risoluzione dei problemi di WCF</span><span class="sxs-lookup"><span data-stu-id="636c0-117">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 <span data-ttu-id="636c0-118">Descrive alcuni dei problemi più comuni, cosa è possibile fare per risolverli e dove trovare ulteriori informazioni sul problema.</span><span class="sxs-lookup"><span data-stu-id="636c0-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>  
  
 [<span data-ttu-id="636c0-119">API Web ASP.NET e WCF</span><span class="sxs-lookup"><span data-stu-id="636c0-119">WCF and ASP.NET Web API</span></span>](../../../docs/framework/wcf/wcf-and-aspnet-web-api.md)  
 <span data-ttu-id="636c0-120">Vengono illustrate le due tecnologie, come interagiscono tra loro e quando utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="636c0-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="636c0-121">Riferimento</span><span class="sxs-lookup"><span data-stu-id="636c0-121">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="636c0-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="636c0-122">Related Sections</span></span>  
 [<span data-ttu-id="636c0-123">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="636c0-123">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)  
  
 [<span data-ttu-id="636c0-124">Panoramica dei concetti</span><span class="sxs-lookup"><span data-stu-id="636c0-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="636c0-125">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="636c0-125">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="636c0-126">Linee guida e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="636c0-126">Guidelines and Best Practices</span></span>](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
  
 [<span data-ttu-id="636c0-127">Strumenti Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="636c0-127">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
  
 [<span data-ttu-id="636c0-128">Esempi di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="636c0-128">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [<span data-ttu-id="636c0-129">Introduzione</span><span class="sxs-lookup"><span data-stu-id="636c0-129">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
  
 [<span data-ttu-id="636c0-130">Hosting IIS mediante il codice Inline</span><span class="sxs-lookup"><span data-stu-id="636c0-130">IIS Hosting Using Inline Code</span></span>](../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)  
  
 [<span data-ttu-id="636c0-131">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="636c0-131">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
