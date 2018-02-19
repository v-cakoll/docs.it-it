---
title: Progettare applicazioni Web moderne con ASP.NET Core e Azure
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Introduzione
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: db9f0ddd875df1f84bcc5681ee1383b0185f8b7e
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2018
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="22e6c-103">Progettare applicazioni Web moderne con ASP.NET Core e Azure</span><span class="sxs-lookup"><span data-stu-id="22e6c-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![Immagine di copertina](./media/cover.jpg)


<span data-ttu-id="22e6c-105">.NET Core e ASP.NET Core offrono diversi vantaggi rispetto allo sviluppo .NET tradizionale.</span><span class="sxs-lookup"><span data-stu-id="22e6c-105">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="22e6c-106">È consigliabile usare .NET Core per le applicazioni server se alcuni o tutti gli aspetti seguenti sono importanti per il successo dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="22e6c-106">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="22e6c-107">Supporto multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="22e6c-107">Cross-platform support</span></span>

-   <span data-ttu-id="22e6c-108">Uso di microservizi</span><span class="sxs-lookup"><span data-stu-id="22e6c-108">Use of microservices</span></span>

-   <span data-ttu-id="22e6c-109">Uso di contenitori Docker</span><span class="sxs-lookup"><span data-stu-id="22e6c-109">Use of Docker containers</span></span>

-   <span data-ttu-id="22e6c-110">Requisiti di scalabilità e prestazioni elevate</span><span class="sxs-lookup"><span data-stu-id="22e6c-110">High performance and scalability requirements</span></span>

-   <span data-ttu-id="22e6c-111">Controllo delle versioni side-by-side di .NET in base all'applicazione nello stesso server</span><span class="sxs-lookup"><span data-stu-id="22e6c-111">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="22e6c-112">Le applicazioni .NET tradizionali possono supportare e supportano questi requisiti, ma ASP.NET Core e .NET Core sono stati ottimizzati per offrire supporto migliorato per gli scenari elencati sopra.</span><span class="sxs-lookup"><span data-stu-id="22e6c-112">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="22e6c-113">Sempre più organizzazioni scelgono di ospitare le proprie applicazioni Web nel cloud usando servizi come Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22e6c-113">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="22e6c-114">Prendere in considerazione di ospitare l'applicazione nel cloud se gli aspetti seguenti sono importanti per l'applicazione o l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="22e6c-114">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="22e6c-115">Riduzione dell'investimento nei costi del data center (hardware, software, spazio, utilità e così via)</span><span class="sxs-lookup"><span data-stu-id="22e6c-115">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="22e6c-116">Prezzi flessibili (pagamento in base all'utilizzo, non per la capacità inattiva)</span><span class="sxs-lookup"><span data-stu-id="22e6c-116">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="22e6c-117">Affidabilità estrema</span><span class="sxs-lookup"><span data-stu-id="22e6c-117">Extreme reliability</span></span>

-   <span data-ttu-id="22e6c-118">Mobilità delle app migliorata, con semplice modifica di come e dove distribuire l'app</span><span class="sxs-lookup"><span data-stu-id="22e6c-118">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="22e6c-119">Capacità flessibile, con ridimensionamento in base alle effettive esigenze</span><span class="sxs-lookup"><span data-stu-id="22e6c-119">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="22e6c-120">La compilazione di applicazioni Web con ASP.NET Core, ospitato in Microsoft Azure, offre diversi vantaggi competitivi rispetto alle alternative tradizionali.</span><span class="sxs-lookup"><span data-stu-id="22e6c-120">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="22e6c-121">ASP.NET Core è ottimizzato per procedure di sviluppo di applicazioni Web moderne e scenari di hosting sul cloud.</span><span class="sxs-lookup"><span data-stu-id="22e6c-121">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="22e6c-122">In questa guida viene descritto come progettare applicazioni ASP.NET Core per sfruttare al meglio i vantaggi di queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="22e6c-122">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="22e6c-123">Scopo</span><span class="sxs-lookup"><span data-stu-id="22e6c-123">Purpose</span></span>

<span data-ttu-id="22e6c-124">Questa guida offre linee guida end-to-end sulla compilazione di applicazioni Web monolitiche usando ASP.NET Core e Azure.</span><span class="sxs-lookup"><span data-stu-id="22e6c-124">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="22e6c-125">Questa guida è complementare al documento "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" (Architettura e sviluppo di applicazioni basate su microservizi e in contenitori con .NET), incentrato più su Docker, microservizi e distribuzione di contenitori per ospitare applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="22e6c-125">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="22e6c-126">Architecting and Developing Containerized Microservice Based Apps in .NET (Architettura e sviluppo di applicazioni basate su microservizi e in contenitori con .NET)</span><span class="sxs-lookup"><span data-stu-id="22e6c-126">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="22e6c-127">**eBook**</span><span class="sxs-lookup"><span data-stu-id="22e6c-127">**e-book**</span></span>  
> <span data-ttu-id="22e6c-128"><http://aka.ms/MicroservicesEbook></span><span class="sxs-lookup"><span data-stu-id="22e6c-128"><http://aka.ms/MicroservicesEbook></span></span>
> - <span data-ttu-id="22e6c-129">**Applicazione di esempio**</span><span class="sxs-lookup"><span data-stu-id="22e6c-129">**Sample Application**</span></span>  
> <span data-ttu-id="22e6c-130"><http://aka.ms/microservicesarchitecture></span><span class="sxs-lookup"><span data-stu-id="22e6c-130"><http://aka.ms/microservicesarchitecture></span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="22e6c-131">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="22e6c-131">Who should use this guide</span></span>

<span data-ttu-id="22e6c-132">I destinatari di questa guida sono prevalentemente sviluppatori, responsabili dello sviluppo e progettisti di architetture interessati alla compilazione di applicazioni Web moderne con tecnologie e servizi Microsoft nel cloud.</span><span class="sxs-lookup"><span data-stu-id="22e6c-132">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="22e6c-133">Un'altra parte minore dei destinatari di questa guida è costituita da responsabili delle decisioni tecniche che hanno già familiarità con ASP.NET e/o Azure e vogliono ottenere informazioni sull'opportunità o meno di eseguire l'aggiornamento ad ASP.NET Core per progetti nuovi o esistenti.</span><span class="sxs-lookup"><span data-stu-id="22e6c-133">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="22e6c-134">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="22e6c-134">How you can use this guide</span></span>

<span data-ttu-id="22e6c-135">Questa guida è stata condensata in un documento relativamente piccolo, incentrato sulla compilazione di applicazioni Web con tecnologie .NET moderne e Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22e6c-135">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="22e6c-136">Per questo motivo, può essere letta interamente per ottenere nozioni di base per la comprensione di tali applicazioni e delle considerazioni tecniche associate.</span><span class="sxs-lookup"><span data-stu-id="22e6c-136">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="22e6c-137">La guida, insieme all'applicazione di esempio, può essere usata anche come punto di partenza o riferimento.</span><span class="sxs-lookup"><span data-stu-id="22e6c-137">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="22e6c-138">Usare l'applicazione di esempio associata come modello per le applicazioni oppure per determinare come organizzare le parti che compongono l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="22e6c-138">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="22e6c-139">Tornare ai principi e alla trattazione di questa guida riguardo ad architettura, opzioni tecnologiche e considerazioni sulle decisioni per soppesare queste scelte per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="22e6c-139">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="22e6c-140">È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità.</span><span class="sxs-lookup"><span data-stu-id="22e6c-140">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="22e6c-141">Facendo sì che tutti usino un insieme comune di termini e di principi sottostanti, si garantisce l'applicazione coerente di modelli e procedure architetturali.</span><span class="sxs-lookup"><span data-stu-id="22e6c-141">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="22e6c-142">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="22e6c-142">References</span></span>
- <span data-ttu-id="22e6c-143">**Scelta di .NET Core o .NET Framework per le app server**</span><span class="sxs-lookup"><span data-stu-id="22e6c-143">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<span data-ttu-id="22e6c-144"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="22e6c-144"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="22e6c-145">[Avanti] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="22e6c-145">[Next] (modern-web-applications-characteristics.md)</span></span>
