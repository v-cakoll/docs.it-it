---
title: Progettare applicazioni Web moderne con ASP.NET Core e Azure
description: Una guida che offre linee guida end-to-end sulla compilazione di applicazioni Web monolitiche usando ASP.NET Core e Azure.
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 27212045d9870c9f2fc15509d76f3e9b07d8657f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62019349"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="bde38-103">Progettare applicazioni Web moderne con ASP.NET Core e Azure</span><span class="sxs-lookup"><span data-stu-id="bde38-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![Immagine della copertina della guida Progettare applicazioni Web moderne.](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="bde38-105">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="bde38-105">PUBLISHED BY</span></span>

<span data-ttu-id="bde38-106">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bde38-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="bde38-107">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bde38-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="bde38-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="bde38-108">One Microsoft Way</span></span>

<span data-ttu-id="bde38-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="bde38-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="bde38-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bde38-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="bde38-111">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="bde38-111">All rights reserved.</span></span> <span data-ttu-id="bde38-112">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="bde38-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="bde38-113">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="bde38-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="bde38-114">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="bde38-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="bde38-115">Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="bde38-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="bde38-116">Nessuna associazione o connessione reale è intenzionale o può essere presupposta.</span><span class="sxs-lookup"><span data-stu-id="bde38-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="bde38-117">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bde38-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="bde38-118">Mac e macOS sono marchi registrati di Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="bde38-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="bde38-119">Il logo Docker con la balena è un marchio registrato di Docker, Inc. Usato su autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="bde38-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="bde38-120">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="bde38-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="bde38-121">Autore:</span><span class="sxs-lookup"><span data-stu-id="bde38-121">Author:</span></span>

> <span data-ttu-id="bde38-122">**Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="bde38-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="bde38-123">Editor:</span><span class="sxs-lookup"><span data-stu-id="bde38-123">Editors:</span></span>

> <span data-ttu-id="bde38-124">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="bde38-124">**Maira Wenzel**</span></span>

## <a name="introduction"></a><span data-ttu-id="bde38-125">Introduzione</span><span class="sxs-lookup"><span data-stu-id="bde38-125">Introduction</span></span>

<span data-ttu-id="bde38-126">.NET Core e ASP.NET Core offrono diversi vantaggi rispetto allo sviluppo .NET tradizionale.</span><span class="sxs-lookup"><span data-stu-id="bde38-126">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="bde38-127">È consigliabile usare .NET Core per le applicazioni server se alcuni o tutti gli aspetti seguenti sono importanti per il successo dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="bde38-127">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="bde38-128">Supporto multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="bde38-128">Cross-platform support.</span></span>

- <span data-ttu-id="bde38-129">Uso di microservizi.</span><span class="sxs-lookup"><span data-stu-id="bde38-129">Use of microservices.</span></span>

- <span data-ttu-id="bde38-130">Uso di contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="bde38-130">Use of Docker containers.</span></span>

- <span data-ttu-id="bde38-131">Requisiti di scalabilità e prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="bde38-131">High performance and scalability requirements.</span></span>

- <span data-ttu-id="bde38-132">Controllo delle versioni side-by-side di .NET in base all'applicazione nello stesso server.</span><span class="sxs-lookup"><span data-stu-id="bde38-132">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="bde38-133">Le applicazioni .NET tradizionali possono supportare e supportano molti di questi requisiti, ma ASP.NET Core e .NET Core sono stati ottimizzati per offrire supporto migliorato per gli scenari elencati sopra.</span><span class="sxs-lookup"><span data-stu-id="bde38-133">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="bde38-134">Sempre più organizzazioni scelgono di ospitare le proprie applicazioni Web nel cloud usando servizi come Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="bde38-134">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="bde38-135">Prendere in considerazione di ospitare l'applicazione nel cloud se gli aspetti seguenti sono importanti per l'applicazione o l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="bde38-135">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="bde38-136">Riduzione dell'investimento nei costi del data center (hardware, software, spazio, utilità, gestione dei server e così via).</span><span class="sxs-lookup"><span data-stu-id="bde38-136">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="bde38-137">Prezzi flessibili (pagamento in base all'utilizzo, non per la capacità inattiva).</span><span class="sxs-lookup"><span data-stu-id="bde38-137">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="bde38-138">Affidabilità estrema.</span><span class="sxs-lookup"><span data-stu-id="bde38-138">Extreme reliability.</span></span>

- <span data-ttu-id="bde38-139">Mobilità delle app migliorata, con semplice modifica di come e dove distribuire l'app.</span><span class="sxs-lookup"><span data-stu-id="bde38-139">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="bde38-140">Capacità flessibile, con ridimensionamento in base alle effettive esigenze.</span><span class="sxs-lookup"><span data-stu-id="bde38-140">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="bde38-141">La compilazione di applicazioni Web con ASP.NET Core, ospitato in Azure, offre molti vantaggi competitivi rispetto alle alternative tradizionali.</span><span class="sxs-lookup"><span data-stu-id="bde38-141">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="bde38-142">ASP.NET Core è ottimizzato per procedure di sviluppo di applicazioni Web moderne e scenari di hosting sul cloud.</span><span class="sxs-lookup"><span data-stu-id="bde38-142">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="bde38-143">In questa guida viene descritto come progettare applicazioni ASP.NET Core per sfruttare al meglio i vantaggi di queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="bde38-143">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="bde38-144">Scopo</span><span class="sxs-lookup"><span data-stu-id="bde38-144">Purpose</span></span>

<span data-ttu-id="bde38-145">Questa guida offre linee guida end-to-end sulla compilazione di applicazioni Web *monolitiche* usando ASP.NET Core e Azure.</span><span class="sxs-lookup"><span data-stu-id="bde38-145">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="bde38-146">In questo contesto "monolitico" si riferisce al fatto che queste applicazioni vengono distribuite come una singola unità, non come una raccolta di applicazioni e servizi che interagiscono tra loro.</span><span class="sxs-lookup"><span data-stu-id="bde38-146">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="bde38-147">Questa guida è complementare per i ["_Microservizi .NET. Architettura per le applicazioni .NET incluse in contenitori_"](../microservices-architecture/index.md) incentrata principalmente su Docker, microservizi e distribuzione di contenitori per ospitare applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="bde38-147">This guide is complementary to the ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices-architecture/index.md) which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="bde38-148">Microservizi .NET.</span><span class="sxs-lookup"><span data-stu-id="bde38-148">.NET Microservices.</span></span> <span data-ttu-id="bde38-149">Architettura per le applicazioni .NET incluse in contenitori</span><span class="sxs-lookup"><span data-stu-id="bde38-149">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="bde38-150">**eBook**</span><span class="sxs-lookup"><span data-stu-id="bde38-150">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="bde38-151">**Applicazione di esempio**</span><span class="sxs-lookup"><span data-stu-id="bde38-151">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="bde38-152">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="bde38-152">Who should use this guide</span></span>

<span data-ttu-id="bde38-153">I destinatari di questa guida sono prevalentemente sviluppatori, responsabili dello sviluppo e progettisti di architetture interessati alla compilazione di applicazioni Web moderne con tecnologie e servizi Microsoft nel cloud.</span><span class="sxs-lookup"><span data-stu-id="bde38-153">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="bde38-154">Un'altra parte minore dei destinatari di questa guida è costituita da responsabili delle decisioni tecniche che hanno già familiarità con ASP.NET o Azure e vogliono ottenere informazioni sull'opportunità o meno di eseguire l'aggiornamento ad ASP.NET Core per progetti nuovi o esistenti.</span><span class="sxs-lookup"><span data-stu-id="bde38-154">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="bde38-155">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="bde38-155">How you can use this guide</span></span>

<span data-ttu-id="bde38-156">Questa guida è stata condensata in un documento relativamente piccolo, incentrato sulla compilazione di applicazioni Web con tecnologie .NET moderne e Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="bde38-156">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="bde38-157">Per questo motivo, può essere letta interamente per ottenere nozioni di base per la comprensione di tali applicazioni e delle considerazioni tecniche associate.</span><span class="sxs-lookup"><span data-stu-id="bde38-157">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="bde38-158">La guida, insieme all'applicazione di esempio, può essere usata anche come punto di partenza o riferimento.</span><span class="sxs-lookup"><span data-stu-id="bde38-158">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="bde38-159">Usare l'applicazione di esempio associata come modello per le applicazioni oppure per determinare come organizzare le parti che compongono l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bde38-159">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="bde38-160">Tornare ai principi e alla trattazione di questa guida riguardo ad architettura, opzioni tecnologiche e considerazioni sulle decisioni per soppesare queste scelte per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bde38-160">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="bde38-161">È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità.</span><span class="sxs-lookup"><span data-stu-id="bde38-161">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="bde38-162">Facendo sì che tutti usino un insieme comune di termini e di principi sottostanti, si garantisce l'applicazione coerente di modelli e procedure architetturali.</span><span class="sxs-lookup"><span data-stu-id="bde38-162">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="bde38-163">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="bde38-163">References</span></span>

- <span data-ttu-id="bde38-164">**Scelta di .NET Core o .NET Framework per le app server**</span><span class="sxs-lookup"><span data-stu-id="bde38-164">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="bde38-165">avanti</span><span class="sxs-lookup"><span data-stu-id="bde38-165">Next</span></span>](modern-web-applications-characteristics.md)