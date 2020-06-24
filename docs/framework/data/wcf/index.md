---
title: WCF Data Services 4.5
description: Informazioni su WCF Data Services, un componente .NET Framework che supporta i servizi per esporre e utilizzare i dati mediante la semantica REST.
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: ca6b196e8c910f97ead6d1df5b6c0dd6c49c68a4
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247753"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="9ad8d-103">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="9ad8d-103">WCF Data Services 4.5</span></span>

<span data-ttu-id="9ad8d-104">WCF Data Services (precedentemente noto come "ADO.NET Data Services") è un componente del .NET Framework che consente di creare servizi che utilizzano il Open Data Protocol (OData) per esporre e utilizzare dati sul Web o su Intranet tramite la semantica [Rest (Representational State Transfer)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span><span class="sxs-lookup"><span data-stu-id="9ad8d-104">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="9ad8d-105">In OData i dati vengono esposti come risorse indirizzabili tramite URI.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-105">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="9ad8d-106">Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-106">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="9ad8d-107">OData utilizza le convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md) per esporre le risorse come set di entità correlate da associazioni.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-107">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="9ad8d-108">WCF Data Services USA il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-108">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="9ad8d-109">In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporti OData.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-109">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="9ad8d-110">OData consente di richiedere e scrivere dati nelle risorse utilizzando formati di trasferimento noti, ovvero Atom, un set di standard per lo scambio e l'aggiornamento di dati come XML e JavaScript Object Notation (JSON), un formato di scambio di dati basato su testo ampiamente utilizzato nelle applicazioni AJAX.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-110">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="9ad8d-111">WCF Data Services possibile esporre i dati originati da varie origini come feed OData.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-111">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="9ad8d-112">Gli strumenti di Visual Studio semplificano la creazione di un servizio basato su OData tramite un modello di dati ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-112">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="9ad8d-113">È anche possibile creare feed OData in base a classi Common Language Runtime (CLR) e anche a dati ad associazione tardiva o non tipizzati.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-113">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="9ad8d-114">WCF Data Services include inoltre un set di librerie client, una per le applicazioni client .NET Framework generali e un'altra specifica per le applicazioni basate su Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-114">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="9ad8d-115">Queste librerie client forniscono un modello di programmazione basato su oggetti per l'accesso a un feed OData da ambienti quali .NET Framework e Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-115">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="9ad8d-116">Da dove iniziare</span><span class="sxs-lookup"><span data-stu-id="9ad8d-116">Where Should I Start?</span></span>

<span data-ttu-id="9ad8d-117">A seconda dei propri interessi, prendere in considerazione la Guida introduttiva a WCF Data Services in uno degli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-117">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="9ad8d-118">Passare subito a...</span><span class="sxs-lookup"><span data-stu-id="9ad8d-118">I want to jump right in...</span></span>

- [<span data-ttu-id="9ad8d-119">Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="9ad8d-119">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="9ad8d-120">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="9ad8d-120">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="9ad8d-121">Mostra solo codice...</span><span class="sxs-lookup"><span data-stu-id="9ad8d-121">Just show me some code...</span></span>

- [<span data-ttu-id="9ad8d-122">Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="9ad8d-122">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="9ad8d-123">Procedura: eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="9ad8d-123">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="9ad8d-124">Procedura: associare dati a elementi Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="9ad8d-124">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="9ad8d-125">Desidero saperne di più su OData...</span><span class="sxs-lookup"><span data-stu-id="9ad8d-125">I want to know more about OData...</span></span>

- [<span data-ttu-id="9ad8d-126">White paper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="9ad8d-126">White paper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="9ad8d-127">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="9ad8d-127">Open Data Protocol website</span></span>](https://www.odata.org/)
- [<span data-ttu-id="9ad8d-128">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="9ad8d-128">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="9ad8d-129">Si desidera visualizzare gli esempi end-to-end...</span><span class="sxs-lookup"><span data-stu-id="9ad8d-129">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="9ad8d-130">[Guida introduttiva a WCF Data Services](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="9ad8d-130">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="9ad8d-131">OData SDK-codice di esempio</span><span class="sxs-lookup"><span data-stu-id="9ad8d-131">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="9ad8d-132">Integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9ad8d-132">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="9ad8d-133">Generazione della libreria dati del servizio dati</span><span class="sxs-lookup"><span data-stu-id="9ad8d-133">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="9ad8d-134">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="9ad8d-134">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="9ad8d-135">Provider di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9ad8d-135">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="9ad8d-136">Che si può fare con questa funzionalità?</span><span class="sxs-lookup"><span data-stu-id="9ad8d-136">What can I do with it?</span></span>

- [<span data-ttu-id="9ad8d-137">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9ad8d-137">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="9ad8d-138">Scenari applicativi</span><span class="sxs-lookup"><span data-stu-id="9ad8d-138">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="9ad8d-139">Si vuole usare LINQ...</span><span class="sxs-lookup"><span data-stu-id="9ad8d-139">I want to use LINQ...</span></span>

- [<span data-ttu-id="9ad8d-140">Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="9ad8d-140">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="9ad8d-141">Considerazioni su LINQ</span><span class="sxs-lookup"><span data-stu-id="9ad8d-141">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="9ad8d-142">Procedura: eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="9ad8d-142">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="9ad8d-143">Ho ancora bisogno di altre informazioni...</span><span class="sxs-lookup"><span data-stu-id="9ad8d-143">I still need some more information...</span></span>

- [<span data-ttu-id="9ad8d-144">Blog del team di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9ad8d-144">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="9ad8d-145">Risorse</span><span class="sxs-lookup"><span data-stu-id="9ad8d-145">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="9ad8d-146">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9ad8d-146">In This Section</span></span>

[<span data-ttu-id="9ad8d-147">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9ad8d-147">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="9ad8d-148">Viene fornita una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-148">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="9ad8d-149">[Novità di WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="9ad8d-149">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="9ad8d-150">Vengono descritte le nuove funzionalità di WCF Data Services e il supporto per le nuove funzionalità OData.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-150">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="9ad8d-151">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="9ad8d-151">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="9ad8d-152">Viene descritto come esporre e utilizzare feed OData utilizzando WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-152">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="9ad8d-153">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9ad8d-153">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="9ad8d-154">Viene descritto come creare e configurare un servizio dati che espone feed OData.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-154">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="9ad8d-155">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="9ad8d-155">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="9ad8d-156">Viene descritto come utilizzare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ad8d-156">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ad8d-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ad8d-157">See also</span></span>

- [<span data-ttu-id="9ad8d-158">REST (Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="9ad8d-158">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
