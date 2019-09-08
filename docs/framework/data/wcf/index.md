---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 017fe2177cf824d461b4c51ea805f75b6ddbe064
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779996"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="cb9ad-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="cb9ad-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="cb9ad-103">WCF Data Services (noto in precedenza come "ADO.NET Data Services") è un componente del .NET Framework che consente di creare servizi che utilizzano [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] per esporre e utilizzare dati sul Web o su Intranet tramite la semantica dello stato di [rappresentazione Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="cb9ad-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="cb9ad-104">In OData i dati vengono esposti come risorse indirizzabili tramite URI.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="cb9ad-105">Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="cb9ad-106">OData utilizza le convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md) per esporre le risorse come set di entità correlate da associazioni.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="cb9ad-107">WCF Data Services USA il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="cb9ad-108">In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporti OData.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="cb9ad-109">OData consente di richiedere e scrivere dati nelle risorse usando formati di trasferimento noti: Atom, un set di standard per lo scambio e l'aggiornamento di dati come XML e JavaScript Object Notation (JSON), un formato di scambio di dati basato su testo ampiamente utilizzato nelle applicazioni AJAX.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="cb9ad-110">WCF Data Services possibile esporre i dati originati da varie origini come feed OData.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="cb9ad-111">Gli strumenti di Visual Studio semplificano la creazione di un servizio basato su OData tramite un modello di dati ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="cb9ad-112">È anche possibile creare feed OData in base a classi Common Language Runtime (CLR) e anche a dati ad associazione tardiva o non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="cb9ad-113">WCF Data Services include inoltre un set di librerie client, una per le applicazioni client .NET Framework generali e un'altra specifica per le applicazioni basate su Silverlight.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="cb9ad-114">Queste librerie client forniscono un modello di programmazione basato su oggetti quando si accede a un feed OData da ambienti quali il .NET Framework e Silverlight.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="cb9ad-115">Da dove iniziare</span><span class="sxs-lookup"><span data-stu-id="cb9ad-115">Where Should I Start?</span></span>

<span data-ttu-id="cb9ad-116">A seconda dei propri interessi, prendere in considerazione la Guida introduttiva a WCF Data Services in uno degli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="cb9ad-117">Passare subito a...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-117">I want to jump right in...</span></span>

- [<span data-ttu-id="cb9ad-118">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="cb9ad-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="cb9ad-119">Introduzione</span><span class="sxs-lookup"><span data-stu-id="cb9ad-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

- [<span data-ttu-id="cb9ad-120">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="cb9ad-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="cb9ad-121">Guida rapida di Silverlight per lo sviluppo per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="cb9ad-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="cb9ad-122">Mostra solo codice...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-122">Just show me some code...</span></span>

- [<span data-ttu-id="cb9ad-123">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="cb9ad-123">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="cb9ad-124">Procedura: Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="cb9ad-124">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="cb9ad-125">Procedura: Associare dati a elementi Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="cb9ad-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="cb9ad-126">Desidero saperne di più su OData...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-126">I want to know more about OData...</span></span>

- [<span data-ttu-id="cb9ad-127">Whitepaper Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="cb9ad-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="cb9ad-128">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="cb9ad-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

- [<span data-ttu-id="cb9ad-129">OData SDK</span><span class="sxs-lookup"><span data-stu-id="cb9ad-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

- [<span data-ttu-id="cb9ad-130">OData domande frequenti</span><span class="sxs-lookup"><span data-stu-id="cb9ad-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="cb9ad-131">Desidero guardare alcuni video...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-131">I want to watch some videos...</span></span>

- [<span data-ttu-id="cb9ad-132">Guida per i principianti di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cb9ad-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

- [<span data-ttu-id="cb9ad-133">Video per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cb9ad-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

- [<span data-ttu-id="cb9ad-134">OData Sito Web per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="cb9ad-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="cb9ad-135">Si desidera visualizzare gli esempi end-to-end...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-135">I want to see end-to-end samples...</span></span>

- [<span data-ttu-id="cb9ad-136">Esempi di documentazione di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="cb9ad-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

- [<span data-ttu-id="cb9ad-137">Altri esempi di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="cb9ad-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

- [<span data-ttu-id="cb9ad-138">OData SDK</span><span class="sxs-lookup"><span data-stu-id="cb9ad-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="cb9ad-139">Integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cb9ad-139">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="cb9ad-140">Generazione della libreria client del servizio dati</span><span class="sxs-lookup"><span data-stu-id="cb9ad-140">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="cb9ad-141">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="cb9ad-141">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="cb9ad-142">Provider di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="cb9ad-142">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="cb9ad-143">Attività possibili</span><span class="sxs-lookup"><span data-stu-id="cb9ad-143">What can I do with it?</span></span>

- [<span data-ttu-id="cb9ad-144">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cb9ad-144">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="cb9ad-145">Whitepaper Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="cb9ad-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="cb9ad-146">Scenari di applicazione</span><span class="sxs-lookup"><span data-stu-id="cb9ad-146">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="cb9ad-147">Si desidera utilizzare Silverlight...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-147">I want to use Silverlight...</span></span>

- [<span data-ttu-id="cb9ad-148">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="cb9ad-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="cb9ad-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="cb9ad-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

- [<span data-ttu-id="cb9ad-150">Introduzione a Silverlight</span><span class="sxs-lookup"><span data-stu-id="cb9ad-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="cb9ad-151">Si vuole usare LINQ...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-151">I want to use LINQ...</span></span>

- [<span data-ttu-id="cb9ad-152">Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="cb9ad-152">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="cb9ad-153">Considerazioni su LINQ</span><span class="sxs-lookup"><span data-stu-id="cb9ad-153">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="cb9ad-154">Procedura: Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="cb9ad-154">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="cb9ad-155">Ho ancora bisogno di altre informazioni...</span><span class="sxs-lookup"><span data-stu-id="cb9ad-155">I still need some more information...</span></span>

- [<span data-ttu-id="cb9ad-156">Blog del team di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cb9ad-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

- [<span data-ttu-id="cb9ad-157">Risorse</span><span class="sxs-lookup"><span data-stu-id="cb9ad-157">Resources</span></span>](wcf-data-services-resources.md)

- [<span data-ttu-id="cb9ad-158">Centro per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cb9ad-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

- [<span data-ttu-id="cb9ad-159">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="cb9ad-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="cb9ad-160">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cb9ad-160">In This Section</span></span>

[<span data-ttu-id="cb9ad-161">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cb9ad-161">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="cb9ad-162">Viene fornita una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="cb9ad-163">[Novità di WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="cb9ad-163">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="cb9ad-164">Vengono descritte le nuove funzionalità di WCF Data Services e il supporto per le nuove funzionalità OData.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="cb9ad-165">Introduzione</span><span class="sxs-lookup"><span data-stu-id="cb9ad-165">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="cb9ad-166">Viene descritto come esporre e utilizzare feed OData utilizzando WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="cb9ad-167">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cb9ad-167">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="cb9ad-168">Viene descritto come creare e configurare un servizio dati che espone feed OData.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="cb9ad-169">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cb9ad-169">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="cb9ad-170">Viene descritto come utilizzare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb9ad-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb9ad-171">See also</span></span>

- [<span data-ttu-id="cb9ad-172">REST (Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="cb9ad-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
