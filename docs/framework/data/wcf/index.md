---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 890f0ba25d8320008228c73660753b9899269fd7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900992"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="10f8f-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="10f8f-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="10f8f-103">WCF Data Services (precedentemente noto come "ADO.NET Data Services") è un componente del .NET Framework che consente di creare servizi che utilizzano il Open Data Protocol (OData) per esporre e utilizzare dati sul Web o su Intranet tramite la semantica [Rest (Representational State Transfer)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span><span class="sxs-lookup"><span data-stu-id="10f8f-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="10f8f-104">OData espone i dati come risorse indirizzabili tramite URI.</span><span class="sxs-lookup"><span data-stu-id="10f8f-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="10f8f-105">È possibile accedere ai dati e modificarli utilizzando i verbi HTTP standard GET, PUT, POST e DELETE.</span><span class="sxs-lookup"><span data-stu-id="10f8f-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="10f8f-106">OData utilizza le convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md) per esporre le risorse come set di entità correlate da associazioni.</span><span class="sxs-lookup"><span data-stu-id="10f8f-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="10f8f-107">WCF Data Services USA il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse.</span><span class="sxs-lookup"><span data-stu-id="10f8f-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="10f8f-108">In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporti OData.</span><span class="sxs-lookup"><span data-stu-id="10f8f-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="10f8f-109">OData consente di richiedere e scrivere dati nelle risorse usando formati di trasferimento noti, ovvero Atom, un set di standard per lo scambio e l'aggiornamento di dati come XML e JavaScript Object Notation (JSON), un formato di scambio di dati basato su testo ampiamente usato in AJAX applicazioni.</span><span class="sxs-lookup"><span data-stu-id="10f8f-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="10f8f-110">WCF Data Services possibile esporre i dati originati da varie origini come feed OData.</span><span class="sxs-lookup"><span data-stu-id="10f8f-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="10f8f-111">Gli strumenti di Visual Studio semplificano la creazione di un servizio basato su OData tramite un modello di dati ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="10f8f-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="10f8f-112">È anche possibile creare feed OData in base a classi Common Language Runtime (CLR) e anche a dati ad associazione tardiva o non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="10f8f-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="10f8f-113">WCF Data Services include inoltre un set di librerie client, una per le applicazioni client .NET Framework generali e un'altra specifica per le applicazioni basate su Silverlight.</span><span class="sxs-lookup"><span data-stu-id="10f8f-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="10f8f-114">Queste librerie client forniscono un modello di programmazione basato su oggetti quando si accede a un feed OData da ambienti quali il .NET Framework e Silverlight.</span><span class="sxs-lookup"><span data-stu-id="10f8f-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="10f8f-115">Da dove iniziare</span><span class="sxs-lookup"><span data-stu-id="10f8f-115">Where Should I Start?</span></span>

<span data-ttu-id="10f8f-116">A seconda dei propri interessi, prendere in considerazione la Guida introduttiva a WCF Data Services in uno degli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="10f8f-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="10f8f-117">Passare subito a...</span><span class="sxs-lookup"><span data-stu-id="10f8f-117">I want to jump right in...</span></span>

- [<span data-ttu-id="10f8f-118">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="10f8f-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="10f8f-119">Introduzione</span><span class="sxs-lookup"><span data-stu-id="10f8f-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="10f8f-120">Mostra solo codice...</span><span class="sxs-lookup"><span data-stu-id="10f8f-120">Just show me some code...</span></span>

- [<span data-ttu-id="10f8f-121">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="10f8f-121">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="10f8f-122">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="10f8f-122">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="10f8f-123">Procedura: Associare dati a elementi Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="10f8f-123">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="10f8f-124">Desidero saperne di più su OData...</span><span class="sxs-lookup"><span data-stu-id="10f8f-124">I want to know more about OData...</span></span>

- [<span data-ttu-id="10f8f-125">Whitepaper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="10f8f-125">Whitepaper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="10f8f-126">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="10f8f-126">Open Data Protocol Web site</span></span>](https://www.odata.org/)
- [<span data-ttu-id="10f8f-127">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="10f8f-127">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="10f8f-128">Si desidera visualizzare gli esempi end-to-end...</span><span class="sxs-lookup"><span data-stu-id="10f8f-128">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="10f8f-129">[Guida introduttiva a WCF Data Services](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="10f8f-129">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="10f8f-130">OData SDK-codice di esempio</span><span class="sxs-lookup"><span data-stu-id="10f8f-130">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="10f8f-131">Integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="10f8f-131">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="10f8f-132">Generazione della libreria client del servizio dati</span><span class="sxs-lookup"><span data-stu-id="10f8f-132">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="10f8f-133">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="10f8f-133">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="10f8f-134">Provider di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="10f8f-134">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="10f8f-135">Attività possibili</span><span class="sxs-lookup"><span data-stu-id="10f8f-135">What can I do with it?</span></span>

- [<span data-ttu-id="10f8f-136">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10f8f-136">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="10f8f-137">Scenari di applicazione</span><span class="sxs-lookup"><span data-stu-id="10f8f-137">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="10f8f-138">Si vuole usare LINQ...</span><span class="sxs-lookup"><span data-stu-id="10f8f-138">I want to use LINQ...</span></span>

- [<span data-ttu-id="10f8f-139">Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="10f8f-139">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="10f8f-140">Considerazioni su LINQ</span><span class="sxs-lookup"><span data-stu-id="10f8f-140">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="10f8f-141">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="10f8f-141">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="10f8f-142">Ho ancora bisogno di altre informazioni...</span><span class="sxs-lookup"><span data-stu-id="10f8f-142">I still need some more information...</span></span>

- [<span data-ttu-id="10f8f-143">Blog del team di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="10f8f-143">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="10f8f-144">Risorse</span><span class="sxs-lookup"><span data-stu-id="10f8f-144">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="10f8f-145">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="10f8f-145">In This Section</span></span>

[<span data-ttu-id="10f8f-146">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10f8f-146">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="10f8f-147">Viene fornita una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="10f8f-147">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="10f8f-148">[Novità di WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="10f8f-148">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="10f8f-149">Vengono descritte le nuove funzionalità di WCF Data Services e il supporto per le nuove funzionalità OData.</span><span class="sxs-lookup"><span data-stu-id="10f8f-149">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="10f8f-150">Introduzione</span><span class="sxs-lookup"><span data-stu-id="10f8f-150">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="10f8f-151">Viene descritto come esporre e utilizzare feed OData utilizzando WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="10f8f-151">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="10f8f-152">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="10f8f-152">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="10f8f-153">Viene descritto come creare e configurare un servizio dati che espone feed OData.</span><span class="sxs-lookup"><span data-stu-id="10f8f-153">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="10f8f-154">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="10f8f-154">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="10f8f-155">Viene descritto come utilizzare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="10f8f-155">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="10f8f-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10f8f-156">See also</span></span>

- [<span data-ttu-id="10f8f-157">REST (Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="10f8f-157">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
