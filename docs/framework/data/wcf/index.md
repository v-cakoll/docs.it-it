---
title: WCF Data Services 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b6b9ddd27422c09f21833548634afd7945afa89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="9b52a-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="9b52a-102">WCF Data Services 4.5</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="9b52a-103"> (precedentemente noto come "ADO.NET Data Services") è un componente di .NET Framework che consente di creare servizi che si basano su [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] per esporre e utilizzare dati sul Web o su Intranet tramite la semantica [REST (Representational State Transfer)](http://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="9b52a-103"> (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="9b52a-104"> espone i dati come risorse indirizzabili tramite URI.</span><span class="sxs-lookup"><span data-stu-id="9b52a-104"> exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="9b52a-105">Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE.</span><span class="sxs-lookup"><span data-stu-id="9b52a-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="9b52a-106"> usa le convenzioni entità-relazione di [Entity Data Model (EDM)](../../../../docs/framework/data/adonet/entity-data-model.md) per esporre risorse come set di entità correlate da associazioni.</span><span class="sxs-lookup"><span data-stu-id="9b52a-106"> uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="9b52a-107"> usa il protocollo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] per l'indirizzamento e l'aggiornamento delle risorse.</span><span class="sxs-lookup"><span data-stu-id="9b52a-107"> uses the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol for addressing and updating resources.</span></span> <span data-ttu-id="9b52a-108">In questo modo, è possibile accedere ai servizi da qualsiasi client che supporti [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b52a-108">In this way, you can access these services from any client that supports [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="9b52a-109"> consente di richiedere e scrivere dati nelle risorse usando formati di trasferimento noti, ovvero Atom, un set di standard per lo scambio e l'aggiornamento di dati come XML, e JSON (JavaScript Object Notation), un formato per lo scambio di dati basati su testo ampiamente usato nelle applicazioni AJAX.</span><span class="sxs-lookup"><span data-stu-id="9b52a-109"> enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="9b52a-110"> consente di esporre i dati provenienti da varie origini come feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b52a-110"> can expose data that originates from various sources as [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span> <span data-ttu-id="9b52a-111">Gli strumenti di Visual Studio semplificano la creazione di un servizio basato su [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] tramite un modello di dati di ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="9b52a-111">Visual Studio tools make it easier for you to create an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="9b52a-112">È anche possibile creare feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] basati sulle classi CLR (Common Language Runtime), nonché dati ad associazione tardiva o senza tipo.</span><span class="sxs-lookup"><span data-stu-id="9b52a-112">You can also create [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="9b52a-113"> include inoltre un set di librerie client: una per le applicazioni client .NET Framework in generale e un'altra specifica per le applicazioni basate su Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9b52a-113"> also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="9b52a-114">Queste librerie client forniscono un modello di programmazione basato su oggetti per l'accesso a un feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] da ambienti quali .NET Framework e Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9b52a-114">These client libraries provide an object-based programming model when you access an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from environments such as the .NET Framework and Silverlight.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="9b52a-115">Da dove iniziare</span><span class="sxs-lookup"><span data-stu-id="9b52a-115">Where Should I Start?</span></span>  
 <span data-ttu-id="9b52a-116">A seconda degli argomenti di maggiore interesse, si consiglia di iniziare a usare [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in uno degli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="9b52a-116">Depending on your interests, consider getting started with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in one of the following topics.</span></span>  
  
 <span data-ttu-id="9b52a-117">Passare subito a...</span><span class="sxs-lookup"><span data-stu-id="9b52a-117">I want to jump right in…</span></span>  
 -   [<span data-ttu-id="9b52a-118">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="9b52a-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="9b52a-119">Introduzione</span><span class="sxs-lookup"><span data-stu-id="9b52a-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [<span data-ttu-id="9b52a-120">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="9b52a-120">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="9b52a-121">Guida rapida di Silverlight per lo sviluppo per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9b52a-121">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 <span data-ttu-id="9b52a-122">Codice di esempio...</span><span class="sxs-lookup"><span data-stu-id="9b52a-122">Just show me some code…</span></span>  
 -   [<span data-ttu-id="9b52a-123">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="9b52a-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="9b52a-124">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="9b52a-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [<span data-ttu-id="9b52a-125">Procedura: Associare dati a elementi Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="9b52a-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 <span data-ttu-id="9b52a-126">Ulteriori informazioni su [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b52a-126">I want to know more about [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span></span>  
 -   [<span data-ttu-id="9b52a-127">Whitepaper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="9b52a-127">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="9b52a-128">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="9b52a-128">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [<span data-ttu-id="9b52a-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="9b52a-129">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [<span data-ttu-id="9b52a-130">OData: Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="9b52a-130">OData: Frequently Asked Questions</span></span>](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 <span data-ttu-id="9b52a-131">Vedere alcuni video...</span><span class="sxs-lookup"><span data-stu-id="9b52a-131">I want to watch some videos…</span></span>  
 -   [<span data-ttu-id="9b52a-132">Guida per i principianti di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9b52a-132">Beginner's Guide to WCF Data Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [<span data-ttu-id="9b52a-133">Video per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9b52a-133">WCF Data Services Developer Videos</span></span>](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [<span data-ttu-id="9b52a-134">OData: Sito Web degli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="9b52a-134">OData: Developers Web site</span></span>](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 <span data-ttu-id="9b52a-135">Vedere esempi end-to-end</span><span class="sxs-lookup"><span data-stu-id="9b52a-135">I want to see end-to-end samples</span></span>  
 -   [<span data-ttu-id="9b52a-136">Esempi di documentazione di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="9b52a-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [<span data-ttu-id="9b52a-137">Altri esempi di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="9b52a-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [<span data-ttu-id="9b52a-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="9b52a-138">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 <span data-ttu-id="9b52a-139">Integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b52a-139">How does it integrate with Visual Studio?</span></span>  
 -   [<span data-ttu-id="9b52a-140">Generazione della libreria client del servizio dati</span><span class="sxs-lookup"><span data-stu-id="9b52a-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [<span data-ttu-id="9b52a-141">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="9b52a-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [<span data-ttu-id="9b52a-142">Provider di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9b52a-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 <span data-ttu-id="9b52a-143">Attività possibili</span><span class="sxs-lookup"><span data-stu-id="9b52a-143">What can I do with it?</span></span>  
 -   [<span data-ttu-id="9b52a-144">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9b52a-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [<span data-ttu-id="9b52a-145">Whitepaper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="9b52a-145">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="9b52a-146">Scenari di applicazione</span><span class="sxs-lookup"><span data-stu-id="9b52a-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 <span data-ttu-id="9b52a-147">Uso di Silverlight</span><span class="sxs-lookup"><span data-stu-id="9b52a-147">I want to use Silverlight…</span></span>  
 -   [<span data-ttu-id="9b52a-148">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="9b52a-148">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="9b52a-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="9b52a-149">WCF Data Services (Silverlight)</span></span>](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [<span data-ttu-id="9b52a-150">Introduzione a Silverlight</span><span class="sxs-lookup"><span data-stu-id="9b52a-150">Getting Started with Silverlight</span></span>](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 <span data-ttu-id="9b52a-151">Creazione di un'applicazione Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9b52a-151">I want to create a Windows Phone application…</span></span>  
 -   [<span data-ttu-id="9b52a-152">Guida rapida di Silverlight per lo sviluppo per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9b52a-152">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [<span data-ttu-id="9b52a-153">Client OData (Open Data Protocol) per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9b52a-153">Open Data Protocol (OData) Client for Windows Phone</span></span>](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 <span data-ttu-id="9b52a-154">Uso di LINQ...</span><span class="sxs-lookup"><span data-stu-id="9b52a-154">I want to use LINQ…</span></span>  
 -   [<span data-ttu-id="9b52a-155">Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="9b52a-155">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [<span data-ttu-id="9b52a-156">Considerazioni su LINQ</span><span class="sxs-lookup"><span data-stu-id="9b52a-156">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [<span data-ttu-id="9b52a-157">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="9b52a-157">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 <span data-ttu-id="9b52a-158">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9b52a-158">I still need some more information…</span></span>  
 -   [<span data-ttu-id="9b52a-159">Blog del team di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9b52a-159">WCF Data Services Team Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [<span data-ttu-id="9b52a-160">Risorse</span><span class="sxs-lookup"><span data-stu-id="9b52a-160">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [<span data-ttu-id="9b52a-161">Centro per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9b52a-161">WCF Data Services Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [<span data-ttu-id="9b52a-162">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="9b52a-162">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a><span data-ttu-id="9b52a-163">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9b52a-163">In This Section</span></span>  
 [<span data-ttu-id="9b52a-164">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9b52a-164">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 <span data-ttu-id="9b52a-165">Viene fornita una panoramica delle caratteristiche e delle funzionalità introdotte in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b52a-165">Provides an overview of the features and functionality available in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="9b52a-166">Novità in WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9b52a-166">What's New in WCF Data Services</span></span>](http://msdn.microsoft.com/en-us/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 <span data-ttu-id="9b52a-167">Vengono descritti le nuove funzionalità in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] e il supporto delle nuove funzionalità di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b52a-167">Describes new functionality in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and support for new [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] features.</span></span>  
  
 [<span data-ttu-id="9b52a-168">Introduzione</span><span class="sxs-lookup"><span data-stu-id="9b52a-168">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 <span data-ttu-id="9b52a-169">Viene illustrato come esporre e usare feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] tramite [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b52a-169">Describes how to expose and consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds by using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="9b52a-170">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9b52a-170">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 <span data-ttu-id="9b52a-171">Viene descritto come creare e configurare un servizio dati che espone feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b52a-171">Describes how to create and configure a data service that exposes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="9b52a-172">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9b52a-172">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 <span data-ttu-id="9b52a-173">Viene descritto come servirsi delle librerie client per usare i feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] da un'applicazione client .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b52a-173">Describes how to use client libraries to consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from a .NET Framework client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b52a-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b52a-174">See Also</span></span>  
 [<span data-ttu-id="9b52a-175">REST (Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="9b52a-175">Representational State Transfer (REST)</span></span>](http://go.microsoft.com/fwlink/?LinkId=113919)
