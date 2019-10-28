---
title: Programmazione WCF di base
ms.date: 03/30/2017
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
ms.openlocfilehash: eff565fa18e3360170584395adcf2a3e7029ac07
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960925"
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="9a3fa-102">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="9a3fa-102">Basic WCF programming</span></span>

<span data-ttu-id="9a3fa-103">Questa sezione presenta le nozioni di base per la creazione di applicazioni Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9a3fa-103">This section presents the fundamentals for creating Windows Communication Foundation (WCF) applications.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9a3fa-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9a3fa-104">In this section</span></span>

 <span data-ttu-id="9a3fa-105">[Ciclo](basic-programming-lifecycle.md) di vita della programmazione di base</span><span class="sxs-lookup"><span data-stu-id="9a3fa-105">[Basic Programming Lifecycle](basic-programming-lifecycle.md)</span></span>\
 <span data-ttu-id="9a3fa-106">Viene descritto il ciclo di vita di progettazione, compilazione e distribuzione di applicazioni client e di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-106">Describes the lifecycle of designing, building, and deploying WCF service and client applications.</span></span>

 <span data-ttu-id="9a3fa-107">[Progettazione e implementazione di servizi](designing-and-implementing-services.md)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-107">[Designing and Implementing Services](designing-and-implementing-services.md)</span></span>\
 <span data-ttu-id="9a3fa-108">Descrive come progettare e implementare un contratto di servizio, scegliere un modello per lo scambio di messaggi, specificare un contratto di errore e altri aspetti di base dei servizi.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>

 <span data-ttu-id="9a3fa-109">[Configuring Services](configuring-services.md)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-109">[Configuring Services](configuring-services.md)</span></span>\
 <span data-ttu-id="9a3fa-110">Viene descritto come configurare un servizio WCF per supportare i requisiti del contratto, personalizzare il comportamento del runtime locale e indicare l'indirizzo per la pubblicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-110">Describes how to configure a WCF service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>

 <span data-ttu-id="9a3fa-111">[Servizi di Hosting](hosting-services.md)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-111">[Hosting Services](hosting-services.md)</span></span>\
 <span data-ttu-id="9a3fa-112">Descrive le caratteristiche fondamentali dei servizi host in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-112">Describes the basics of hosting services in an application.</span></span>

 <span data-ttu-id="9a3fa-113">[Creazione di client](building-clients.md)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-113">[Building Clients](building-clients.md)</span></span>\
 <span data-ttu-id="9a3fa-114">Viene descritto come ottenere i metadati dai servizi, convertirli nel codice client WCF, gestire problemi di sicurezza e compilare, configurare e ospitare un client WCF.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-114">Describes how to obtain metadata from services, convert that into WCF client code, handle security issues, and build, configure, and host a WCF client.</span></span>

 <span data-ttu-id="9a3fa-115">[Introduzione all'estendibilità](introduction-to-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-115">[Introduction to Extensibility](introduction-to-extensibility.md)</span></span>\
 <span data-ttu-id="9a3fa-116">Viene descritto come estendere WCF per creare soluzioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-116">Describes how to extend WCF to create custom solutions.</span></span>

 <span data-ttu-id="9a3fa-117">[Guida introduttiva alla risoluzione dei problemi di WCF](wcf-troubleshooting-quickstart.md)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-117">[WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md)</span></span>\
 <span data-ttu-id="9a3fa-118">Descrive alcuni dei problemi più comuni, cosa è possibile fare per risolverli e dove trovare ulteriori informazioni sul problema.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>

 <span data-ttu-id="9a3fa-119">[WCF e API Web ASP.NET](wcf-and-aspnet-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-119">[WCF and ASP.NET Web API](wcf-and-aspnet-web-api.md)</span></span>\
 <span data-ttu-id="9a3fa-120">Vengono illustrate le due tecnologie, come interagiscono tra loro e quando utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="9a3fa-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>

## <a name="reference"></a><span data-ttu-id="9a3fa-121">Reference</span><span class="sxs-lookup"><span data-stu-id="9a3fa-121">Reference</span></span>

- <xref:System.ServiceModel>
- <xref:System.ServiceModel.Channels>
- <xref:System.ServiceModel.Description>

## <a name="related-sections"></a><span data-ttu-id="9a3fa-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9a3fa-122">Related sections</span></span>

- [<span data-ttu-id="9a3fa-123">Panoramica dei concetti</span><span class="sxs-lookup"><span data-stu-id="9a3fa-123">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="9a3fa-124">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="9a3fa-124">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="9a3fa-125">Linee guida e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="9a3fa-125">Guidelines and Best Practices</span></span>](guidelines-and-best-practices.md)
- [<span data-ttu-id="9a3fa-126">Strumenti Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9a3fa-126">Windows Communication Foundation Tools</span></span>](tools.md)
- [<span data-ttu-id="9a3fa-127">Esempi di Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="9a3fa-127">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="9a3fa-128">Introduzione</span><span class="sxs-lookup"><span data-stu-id="9a3fa-128">Getting Started</span></span>](./samples/getting-started-sample.md)
- [<span data-ttu-id="9a3fa-129">Hosting IIS mediante il codice inline</span><span class="sxs-lookup"><span data-stu-id="9a3fa-129">IIS Hosting Using Inline Code</span></span>](./samples/iis-hosting-using-inline-code.md)
- [<span data-ttu-id="9a3fa-130">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="9a3fa-130">Self-Host</span></span>](./samples/self-host.md)
