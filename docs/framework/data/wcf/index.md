---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 1ce152b84f17a35982a75f54b5418623ba39210f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975225"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="009ac-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="009ac-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="009ac-103">WCF Data Services (precedentemente noto come "ADO.NET Data Services") è un componente del .NET Framework che consente di creare servizi che utilizzano il Open Data Protocol (OData) per esporre e utilizzare dati sul Web o su Intranet tramite la semantica [Rest (Representational State Transfer)](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="009ac-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="009ac-104">In OData i dati vengono esposti come risorse indirizzabili tramite URI.</span><span class="sxs-lookup"><span data-stu-id="009ac-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="009ac-105">Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE.</span><span class="sxs-lookup"><span data-stu-id="009ac-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="009ac-106">OData utilizza le convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md) per esporre le risorse come set di entità correlate da associazioni.</span><span class="sxs-lookup"><span data-stu-id="009ac-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="009ac-107">WCF Data Services USA il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse.</span><span class="sxs-lookup"><span data-stu-id="009ac-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="009ac-108">In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporti OData.</span><span class="sxs-lookup"><span data-stu-id="009ac-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="009ac-109">OData consente di richiedere e scrivere dati nelle risorse usando formati di trasferimento noti, ovvero Atom, un set di standard per lo scambio e l'aggiornamento di dati come XML e JavaScript Object Notation (JSON), un formato di scambio di dati basato su testo ampiamente usato in AJAX applicazioni.</span><span class="sxs-lookup"><span data-stu-id="009ac-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="009ac-110">WCF Data Services possibile esporre i dati originati da varie origini come feed OData.</span><span class="sxs-lookup"><span data-stu-id="009ac-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="009ac-111">Gli strumenti di Visual Studio semplificano la creazione di un servizio basato su OData tramite un modello di dati ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="009ac-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="009ac-112">È anche possibile creare feed OData in base a classi Common Language Runtime (CLR) e anche a dati ad associazione tardiva o non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="009ac-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="009ac-113">WCF Data Services include inoltre un set di librerie client, una per le applicazioni client .NET Framework generali e un'altra specifica per le applicazioni basate su Silverlight.</span><span class="sxs-lookup"><span data-stu-id="009ac-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="009ac-114">Queste librerie client forniscono un modello di programmazione basato su oggetti quando si accede a un feed OData da ambienti quali il .NET Framework e Silverlight.</span><span class="sxs-lookup"><span data-stu-id="009ac-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="009ac-115">Da dove iniziare</span><span class="sxs-lookup"><span data-stu-id="009ac-115">Where Should I Start?</span></span>

<span data-ttu-id="009ac-116">A seconda dei propri interessi, prendere in considerazione la Guida introduttiva a WCF Data Services in uno degli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="009ac-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="009ac-117">Passare subito a...</span><span class="sxs-lookup"><span data-stu-id="009ac-117">I want to jump right in...</span></span>

- [<span data-ttu-id="009ac-118">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="009ac-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="009ac-119">Introduzione</span><span class="sxs-lookup"><span data-stu-id="009ac-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

- [<span data-ttu-id="009ac-120">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="009ac-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="009ac-121">Guida rapida di Silverlight per lo sviluppo per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="009ac-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="009ac-122">Mostra solo codice...</span><span class="sxs-lookup"><span data-stu-id="009ac-122">Just show me some code...</span></span>

- [<span data-ttu-id="009ac-123">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="009ac-123">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="009ac-124">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="009ac-124">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="009ac-125">Procedura: Associare dati a elementi Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="009ac-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="009ac-126">Desidero saperne di più su OData...</span><span class="sxs-lookup"><span data-stu-id="009ac-126">I want to know more about OData...</span></span>

- [<span data-ttu-id="009ac-127">Whitepaper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="009ac-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="009ac-128">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="009ac-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

- [<span data-ttu-id="009ac-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="009ac-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

- [<span data-ttu-id="009ac-130">OData: Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="009ac-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="009ac-131">Desidero guardare alcuni video...</span><span class="sxs-lookup"><span data-stu-id="009ac-131">I want to watch some videos...</span></span>

- [<span data-ttu-id="009ac-132">Guida per i principianti di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="009ac-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

- [<span data-ttu-id="009ac-133">Video per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="009ac-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

- [<span data-ttu-id="009ac-134">OData: Sito Web degli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="009ac-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="009ac-135">Si desidera visualizzare gli esempi end-to-end...</span><span class="sxs-lookup"><span data-stu-id="009ac-135">I want to see end-to-end samples...</span></span>

- [<span data-ttu-id="009ac-136">Esempi di documentazione di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="009ac-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

- [<span data-ttu-id="009ac-137">Altri esempi di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="009ac-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

- [<span data-ttu-id="009ac-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="009ac-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="009ac-139">Integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="009ac-139">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="009ac-140">Generazione della libreria client del servizio dati</span><span class="sxs-lookup"><span data-stu-id="009ac-140">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="009ac-141">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="009ac-141">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="009ac-142">Provider di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="009ac-142">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="009ac-143">Attività possibili</span><span class="sxs-lookup"><span data-stu-id="009ac-143">What can I do with it?</span></span>

- [<span data-ttu-id="009ac-144">Panoramica</span><span class="sxs-lookup"><span data-stu-id="009ac-144">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="009ac-145">Whitepaper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="009ac-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="009ac-146">Scenari di applicazione</span><span class="sxs-lookup"><span data-stu-id="009ac-146">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="009ac-147">Si desidera utilizzare Silverlight...</span><span class="sxs-lookup"><span data-stu-id="009ac-147">I want to use Silverlight...</span></span>

- [<span data-ttu-id="009ac-148">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="009ac-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="009ac-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="009ac-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

- [<span data-ttu-id="009ac-150">Introduzione a Silverlight</span><span class="sxs-lookup"><span data-stu-id="009ac-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="009ac-151">Si vuole usare LINQ...</span><span class="sxs-lookup"><span data-stu-id="009ac-151">I want to use LINQ...</span></span>

- [<span data-ttu-id="009ac-152">Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="009ac-152">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="009ac-153">Considerazioni su LINQ</span><span class="sxs-lookup"><span data-stu-id="009ac-153">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="009ac-154">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="009ac-154">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="009ac-155">Ho ancora bisogno di altre informazioni...</span><span class="sxs-lookup"><span data-stu-id="009ac-155">I still need some more information...</span></span>

- [<span data-ttu-id="009ac-156">Blog del team di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="009ac-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

- [<span data-ttu-id="009ac-157">Risorse</span><span class="sxs-lookup"><span data-stu-id="009ac-157">Resources</span></span>](wcf-data-services-resources.md)

- [<span data-ttu-id="009ac-158">Centro per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="009ac-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

- [<span data-ttu-id="009ac-159">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="009ac-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="009ac-160">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="009ac-160">In This Section</span></span>

[<span data-ttu-id="009ac-161">Panoramica</span><span class="sxs-lookup"><span data-stu-id="009ac-161">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="009ac-162">Viene fornita una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="009ac-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="009ac-163">[Novità di WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="009ac-163">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="009ac-164">Vengono descritte le nuove funzionalità di WCF Data Services e il supporto per le nuove funzionalità OData.</span><span class="sxs-lookup"><span data-stu-id="009ac-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="009ac-165">Introduzione</span><span class="sxs-lookup"><span data-stu-id="009ac-165">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="009ac-166">Viene descritto come esporre e utilizzare feed OData utilizzando WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="009ac-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="009ac-167">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="009ac-167">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="009ac-168">Viene descritto come creare e configurare un servizio dati che espone feed OData.</span><span class="sxs-lookup"><span data-stu-id="009ac-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="009ac-169">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="009ac-169">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="009ac-170">Viene descritto come utilizzare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="009ac-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="009ac-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="009ac-171">See also</span></span>

- [<span data-ttu-id="009ac-172">REST (Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="009ac-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
