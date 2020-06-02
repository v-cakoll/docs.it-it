---
title: Progettare applicazioni Web moderne con ASP.NET Core e Azure
description: Una guida che offre linee guida end-to-end sulla compilazione di applicazioni Web monolitiche usando ASP.NET Core e Azure.
author: ardalis
ms.author: wiwagn
ms.date: 5/25/2020
ms.openlocfilehash: 7be03ea8edb763096b0684a62e71826f1cfcd42f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284455"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="32760-103">Progettare applicazioni Web moderne con ASP.NET Core e Azure</span><span class="sxs-lookup"><span data-stu-id="32760-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![Book Cover image of the Architect Modern Web Applications guide.](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="32760-105">**Edizione v 3.1** -aggiornata alla ASP.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="32760-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="32760-106">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="32760-106">PUBLISHED BY</span></span>

<span data-ttu-id="32760-107">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="32760-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="32760-108">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="32760-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="32760-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="32760-109">One Microsoft Way</span></span>

<span data-ttu-id="32760-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="32760-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="32760-111">Copyright © 2020 di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="32760-111">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="32760-112">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="32760-112">All rights reserved.</span></span> <span data-ttu-id="32760-113">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="32760-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="32760-114">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="32760-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="32760-115">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="32760-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="32760-116"> Alcuni esempi usati in questo documento vengono forniti a scopo puramente illustrativo e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="32760-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="32760-117">Nessuna associazione reale o connessione è intenzionale o può essere desunta.</span><span class="sxs-lookup"><span data-stu-id="32760-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="32760-118">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32760-118">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="32760-119">Mac e macOS sono marchi registrati di Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="32760-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="32760-120">Il logo Docker Whale è un marchio registrato di Docker, Inc. usato dall'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="32760-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="32760-121">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="32760-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="32760-122">Author (Autore):</span><span class="sxs-lookup"><span data-stu-id="32760-122">Author:</span></span>

> <span data-ttu-id="32760-123">**Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="32760-123">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="32760-124">Editor:</span><span class="sxs-lookup"><span data-stu-id="32760-124">Editors:</span></span>

> <span data-ttu-id="32760-125">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="32760-125">**Maira Wenzel**</span></span>

## <a name="action-links"></a><span data-ttu-id="32760-126">Collegamenti all'azione</span><span class="sxs-lookup"><span data-stu-id="32760-126">Action links</span></span>

- <span data-ttu-id="32760-127">Questo e-book è disponibile anche in formato PDF (solo versione in lingua inglese [)](https://aka.ms/webappebook)</span><span class="sxs-lookup"><span data-stu-id="32760-127">This e-book is also available in a PDF format (English version only) [Download](https://aka.ms/webappebook)</span></span>

- <span data-ttu-id="32760-128">Clonare/biforcare l'applicazione [di riferimento eShopOnWeb su GitHub](https://github.com/dotnet-architecture/eShopOnWeb)</span><span class="sxs-lookup"><span data-stu-id="32760-128">Clone/Fork the reference application [eShopOnWeb on GitHub](https://github.com/dotnet-architecture/eShopOnWeb)</span></span>

## <a name="introduction"></a><span data-ttu-id="32760-129">Introduzione</span><span class="sxs-lookup"><span data-stu-id="32760-129">Introduction</span></span>

<span data-ttu-id="32760-130">.NET Core e ASP.NET Core offrono diversi vantaggi rispetto allo sviluppo .NET tradizionale.</span><span class="sxs-lookup"><span data-stu-id="32760-130">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="32760-131">È consigliabile usare .NET Core per le applicazioni server se alcuni o tutti gli aspetti seguenti sono importanti per il successo dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="32760-131">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="32760-132">Supporto multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="32760-132">Cross-platform support.</span></span>

- <span data-ttu-id="32760-133">Uso di microservizi.</span><span class="sxs-lookup"><span data-stu-id="32760-133">Use of microservices.</span></span>

- <span data-ttu-id="32760-134">Uso di contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="32760-134">Use of Docker containers.</span></span>

- <span data-ttu-id="32760-135">Requisiti di scalabilità e prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="32760-135">High performance and scalability requirements.</span></span>

- <span data-ttu-id="32760-136">Controllo delle versioni side-by-side di .NET in base all'applicazione nello stesso server.</span><span class="sxs-lookup"><span data-stu-id="32760-136">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="32760-137">Le applicazioni .NET tradizionali possono supportare e supportano molti di questi requisiti, ma ASP.NET Core e .NET Core sono stati ottimizzati per offrire supporto migliorato per gli scenari elencati sopra.</span><span class="sxs-lookup"><span data-stu-id="32760-137">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="32760-138">Sempre più organizzazioni scelgono di ospitare le proprie applicazioni Web nel cloud usando servizi come Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="32760-138">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="32760-139">Prendere in considerazione di ospitare l'applicazione nel cloud se gli aspetti seguenti sono importanti per l'applicazione o l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="32760-139">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="32760-140">Riduzione dell'investimento nei costi del data center (hardware, software, spazio, utilità, gestione dei server e così via).</span><span class="sxs-lookup"><span data-stu-id="32760-140">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="32760-141">Prezzi flessibili (pagamento in base all'utilizzo, non per la capacità inattiva).</span><span class="sxs-lookup"><span data-stu-id="32760-141">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="32760-142">Affidabilità estrema.</span><span class="sxs-lookup"><span data-stu-id="32760-142">Extreme reliability.</span></span>

- <span data-ttu-id="32760-143">Mobilità delle app migliorata, con semplice modifica di come e dove distribuire l'app.</span><span class="sxs-lookup"><span data-stu-id="32760-143">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="32760-144">Capacità flessibile, con ridimensionamento in base alle effettive esigenze.</span><span class="sxs-lookup"><span data-stu-id="32760-144">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="32760-145">La compilazione di applicazioni Web con ASP.NET Core, ospitato in Azure, offre molti vantaggi competitivi rispetto alle alternative tradizionali.</span><span class="sxs-lookup"><span data-stu-id="32760-145">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="32760-146">ASP.NET Core è ottimizzato per procedure di sviluppo di applicazioni Web moderne e scenari di hosting sul cloud.</span><span class="sxs-lookup"><span data-stu-id="32760-146">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="32760-147">In questa guida viene descritto come progettare applicazioni ASP.NET Core per sfruttare al meglio i vantaggi di queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="32760-147">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="version"></a><span data-ttu-id="32760-148">Versione</span><span class="sxs-lookup"><span data-stu-id="32760-148">Version</span></span>

<span data-ttu-id="32760-149">Questa guida è stata modificata per coprire la versione di **.net core 3,1** insieme a molti aggiornamenti aggiuntivi relativi alla stessa "Wave" delle tecnologie (ovvero Azure e altre tecnologie di terze parti) in concomitanza con la versione di .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="32760-149">This guide has been revised to cover **.NET Core 3.1** version along with many additional updates related to the same "wave" of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span> <span data-ttu-id="32760-150">Per questo motivo la versione del libro è stata aggiornata anche alla versione **3,1**.</span><span class="sxs-lookup"><span data-stu-id="32760-150">That's why the book version has also been updated to version **3.1**.</span></span>

## <a name="purpose"></a><span data-ttu-id="32760-151">Scopo</span><span class="sxs-lookup"><span data-stu-id="32760-151">Purpose</span></span>

<span data-ttu-id="32760-152">Questa guida fornisce indicazioni end-to-end sulla creazione di applicazioni Web *monolitiche* con ASP.NET Core e Azure.</span><span class="sxs-lookup"><span data-stu-id="32760-152">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="32760-153">In questo contesto "monolitico" si riferisce al fatto che queste applicazioni vengono distribuite come una singola unità, non come una raccolta di applicazioni e servizi che interagiscono tra loro.</span><span class="sxs-lookup"><span data-stu-id="32760-153">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="32760-154">Questa guida è complementare [ai_microservizi .NET. Architettura per le applicazioni .NET in contenitori_"](../microservices/index.md), che è incentrata su Docker, microservizi e sulla distribuzione di contenitori per ospitare le applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="32760-154">This guide is complementary to ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices/index.md), which focuses more on Docker, microservices, and deployment of containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="32760-155">Microservizi .NET.</span><span class="sxs-lookup"><span data-stu-id="32760-155">.NET Microservices.</span></span> <span data-ttu-id="32760-156">Architettura per le applicazioni .NET incluse in contenitori</span><span class="sxs-lookup"><span data-stu-id="32760-156">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="32760-157">**e-book**</span><span class="sxs-lookup"><span data-stu-id="32760-157">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="32760-158">**Applicazione di esempio**</span><span class="sxs-lookup"><span data-stu-id="32760-158">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="32760-159">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="32760-159">Who should use this guide</span></span>

<span data-ttu-id="32760-160">I destinatari di questa guida sono prevalentemente sviluppatori, responsabili dello sviluppo e progettisti di architetture interessati alla compilazione di applicazioni Web moderne con tecnologie e servizi Microsoft nel cloud.</span><span class="sxs-lookup"><span data-stu-id="32760-160">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="32760-161">Un'altra parte minore dei destinatari di questa guida è costituita da responsabili delle decisioni tecniche che hanno già familiarità con ASP.NET o Azure e vogliono ottenere informazioni sull'opportunità o meno di eseguire l'aggiornamento ad ASP.NET Core per progetti nuovi o esistenti.</span><span class="sxs-lookup"><span data-stu-id="32760-161">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="32760-162">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="32760-162">How you can use this guide</span></span>

<span data-ttu-id="32760-163">Questa guida è stata ridotta in un documento relativamente piccolo incentrato sulla creazione di applicazioni Web con tecnologie .NET moderne e Azure.</span><span class="sxs-lookup"><span data-stu-id="32760-163">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Azure.</span></span> <span data-ttu-id="32760-164">Per questo motivo, può essere letta interamente per ottenere nozioni di base per la comprensione di tali applicazioni e delle considerazioni tecniche associate.</span><span class="sxs-lookup"><span data-stu-id="32760-164">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="32760-165">La guida, insieme all'applicazione di esempio, può essere usata anche come punto di partenza o riferimento.</span><span class="sxs-lookup"><span data-stu-id="32760-165">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="32760-166">Usare l'applicazione di esempio associata come modello per le applicazioni oppure per determinare come organizzare le parti che compongono l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="32760-166">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="32760-167">Tornare ai principi e alla trattazione di questa guida riguardo ad architettura, opzioni tecnologiche e considerazioni sulle decisioni per soppesare queste scelte per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="32760-167">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="32760-168">È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità.</span><span class="sxs-lookup"><span data-stu-id="32760-168">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="32760-169">Facendo sì che tutti usino un insieme comune di termini e di principi sottostanti, si garantisce l'applicazione coerente di modelli e procedure architetturali.</span><span class="sxs-lookup"><span data-stu-id="32760-169">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="32760-170">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="32760-170">References</span></span>

- <span data-ttu-id="32760-171">**Scelta di .NET Core o .NET Framework per le app server**</span><span class="sxs-lookup"><span data-stu-id="32760-171">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../../standard/choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="32760-172">Avanti</span><span class="sxs-lookup"><span data-stu-id="32760-172">Next</span></span>](modern-web-applications-characteristics.md)
