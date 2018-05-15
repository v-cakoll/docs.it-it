---
title: Procedure dettagliate e technical Panoramica avviata
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows | Procedure dettagliate e technical Panoramica avviata
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 27de9d1c5475855a22f2d8a3518982605277f6d9
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="99159-103">Procedure dettagliate e technical Panoramica avviata</span><span class="sxs-lookup"><span data-stu-id="99159-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="99159-104">Per limitare le dimensioni di questo e-book, documentazione tecnica aggiuntiva e le procedure dettagliate di complete sono stati resi disponibili in un repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="99159-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="99159-105">La serie in linea di procedure dettagliate in cui sono descritto in questo capitolo descrive la procedura di configurazione di più ambienti basati su contenitori di Windows e la distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="99159-106">Le sezioni seguenti illustrano ciò che ogni procedura dettagliata è sui relativi obiettivi e degli obiettivi di alto livello e un diagramma di attività che sono coinvolti.</span><span class="sxs-lookup"><span data-stu-id="99159-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="99159-107">È possibile ottenere le procedure dettagliate autonomamente nel *eShopModernizing* wiki repository GitHub di App in [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span><span class="sxs-lookup"><span data-stu-id="99159-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="99159-108">Elenco di istruzioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="99159-108">Technical walkthrough list</span></span>

<span data-ttu-id="99159-109">Le procedure dettagliate seguenti avviato get forniscono linee guida tecnica completa e coerenza per le app di esempio che è possibile sollevare e spostare usando i contenitori e quindi spostare utilizzando più opzioni di distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="99159-110">Ognuna delle procedure dettagliate seguenti utilizza il nuovo esempio eShopLegacy eShopModernizing le App e quali sono disponibili in GitHub all'indirizzo [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="99159-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="99159-111">**Presentazione di eShop legacy (app linea di base per modernizzare)**</span><span class="sxs-lookup"><span data-stu-id="99159-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="99159-112">**Containerize le app web ASP.NET esistenti (Web Form e MVC) con i contenitori di Windows**</span><span class="sxs-lookup"><span data-stu-id="99159-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="99159-113">**Containerize i servizi WCF esistenti (applicazioni a più livelli) con i contenitori di Windows**</span><span class="sxs-lookup"><span data-stu-id="99159-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="99159-114">**Distribuire l'app basata su contenitori di Windows in macchine virtuali di Azure**</span><span class="sxs-lookup"><span data-stu-id="99159-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="99159-115">**Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di Azure**</span><span class="sxs-lookup"><span data-stu-id="99159-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="99159-116">**Distribuire le app basate su contenitori di Windows Azure Service Fabric**</span><span class="sxs-lookup"><span data-stu-id="99159-116">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>


## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="99159-117">Procedura dettagliata 1: Panoramica delle applicazioni legacy eShop</span><span class="sxs-lookup"><span data-stu-id="99159-117">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="99159-118">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="99159-118">Technical walkthrough availability</span></span>

<span data-ttu-id="99159-119">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="99159-119">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="99159-120">procedure dettagliate di wiki eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="99159-120">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)


### <a name="overview"></a><span data-ttu-id="99159-121">Panoramica</span><span class="sxs-lookup"><span data-stu-id="99159-121">Overview</span></span>

<span data-ttu-id="99159-122">In questa procedura dettagliata, è possibile esplorare l'implementazione iniziale tre applicazioni di esempio legacy.</span><span class="sxs-lookup"><span data-stu-id="99159-122">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="99159-123">Le prime due App web di esempio hanno un'architettura monolitica e sono state create tramite ASP.NET classico.</span><span class="sxs-lookup"><span data-stu-id="99159-123">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="99159-124">Un'applicazione basata su ASP.NET 4. x MVC; la seconda applicazione è basata su Web Form ASP.NET 4. x.</span><span class="sxs-lookup"><span data-stu-id="99159-124">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="99159-125">La terza applicazione è un'applicazione a 3 livelli composta da un'app di Windows Form client e lato server [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) servizio.</span><span class="sxs-lookup"><span data-stu-id="99159-125">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="99159-126">Tutte queste applicazioni sono disponibili nel [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="99159-126">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="99159-127">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="99159-127">Goals</span></span>

<span data-ttu-id="99159-128">L'obiettivo principale di questa procedura dettagliata è semplicemente per acquisire familiarità con queste App e con il codice e configurazione.</span><span class="sxs-lookup"><span data-stu-id="99159-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="99159-129">È possibile configurare le App in modo che possano generare e utilizzare dati fittizi, senza l'utilizzo del database SQL, a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="99159-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="99159-130">Questa configurazione facoltativa è basata sul inserimento di dipendenze, in modo separato.</span><span class="sxs-lookup"><span data-stu-id="99159-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="99159-131">Scenario 1: App Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="99159-131">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="99159-132">Nella figura seguente viene illustrato un semplice scenario delle applicazioni web ASP.NET legacy originale.</span><span class="sxs-lookup"><span data-stu-id="99159-132">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

> ![Scenario semplice architettura delle applicazioni web originale legacy ASP.NET](./media/image5-1.png)
>

<span data-ttu-id="99159-134">Da una prospettiva di dominio aziendale, entrambe le app offrono lo stesso catalogo le funzionalità di gestione.</span><span class="sxs-lookup"><span data-stu-id="99159-134">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="99159-135">I membri del team enterprise eShop utilizzerebbe l'app per visualizzare e modificare il catalogo dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="99159-135">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> 

<span data-ttu-id="99159-136">La figura seguente mostra la schermata iniziale di app.</span><span class="sxs-lookup"><span data-stu-id="99159-136">The next figure shows the initial app screenshots.</span></span>

![Applicazioni ASP.NET MVC e Web Form ASP.NET (le tecnologie esistenti/legacy)](./media/image5-2.png)

<span data-ttu-id="99159-138">Le dipendenze in ASP.NET 4. x o versioni precedenti (una per MVC o Web Form) significa che queste applicazioni non vengono eseguito su .NET Core, a meno che il codice è stata completamente riscritta utilizzando ASP.NET MVC di base.</span><span class="sxs-lookup"><span data-stu-id="99159-138">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> 

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="99159-139">Scenario 2: Servizio WCF e app di Windows Form client (applicazione di livello 3)</span><span class="sxs-lookup"><span data-stu-id="99159-139">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="99159-140">Nella figura seguente viene illustrato un semplice scenario dell'applicazione legacy a 3 livelli originale.</span><span class="sxs-lookup"><span data-stu-id="99159-140">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

> ![Scenario semplice architettura dell'app a 3 livelli legacy originale con un servizio WCF e un'app client di Windows Form](./media/image5-1.5.png)
>

### <a name="benefits"></a><span data-ttu-id="99159-142">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="99159-142">Benefits</span></span>

<span data-ttu-id="99159-143">I vantaggi di questa procedura dettagliata sono semplici: semplicemente acquisire familiarità con il codice e App iniziale.</span><span class="sxs-lookup"><span data-stu-id="99159-143">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="99159-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99159-144">Next steps</span></span>

<span data-ttu-id="99159-145">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="99159-145">Explore this content more in-depth on the GitHub wiki:</span></span>

  - [<span data-ttu-id="99159-146">Panoramica sulla linea di base ASP.NET MVC e Web Form "legacy" app</span><span class="sxs-lookup"><span data-stu-id="99159-146">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
  - [<span data-ttu-id="99159-147">Panoramica sul servizio WCF di base e "legacy" app di Windows Form (livello 3)</span><span class="sxs-lookup"><span data-stu-id="99159-147">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)


## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="99159-148">Procedura dettagliata 2: Inserita in un contenitore le applicazioni .NET esistenti con i contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="99159-148">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="99159-149">Panoramica</span><span class="sxs-lookup"><span data-stu-id="99159-149">Overview</span></span>

<span data-ttu-id="99159-150">Utilizzare i contenitori di Windows per migliorare la distribuzione di applicazioni .NET esistenti, ad esempio quelle basate su WCF, MVC o Web Form per gli ambienti di test, sviluppo e produzione.</span><span class="sxs-lookup"><span data-stu-id="99159-150">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="99159-151">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="99159-151">Goals</span></span>

<span data-ttu-id="99159-152">L'obiettivo di questa procedura dettagliata è descrivere le diverse opzioni per containerizing un'applicazione esistente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99159-152">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="99159-153">È possibile:</span><span class="sxs-lookup"><span data-stu-id="99159-153">You can:</span></span>

- <span data-ttu-id="99159-154">L'applicazione inserita in un contenitore utilizzando [Visual Studio 2017 Tools per Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="99159-154">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="99159-155">L'applicazione inserita in un contenitore aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)e quindi utilizzando il [CLI di Docker](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="99159-155">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="99159-156">L'applicazione inserita in un contenitore utilizzando il [Img2Docker](https://github.com/docker/communitytools-image2docker-win) strumento (uno strumento open source da Docker).</span><span class="sxs-lookup"><span data-stu-id="99159-156">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="99159-157">Questa procedura dettagliata si concentra sugli strumenti di Visual Studio 2017 per approccio Docker, ma gli altri due approcci sono piuttosto simili per quanto riguarda utilizzo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="99159-157">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="99159-158">Scenario 1: Le app web ASP.NET nei contenitori</span><span class="sxs-lookup"><span data-stu-id="99159-158">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="99159-159">Nella figura seguente viene illustrato lo scenario per le applicazioni di App web legacy eShop nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="99159-159">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

> ![Diagramma dell'architettura semplificata di contenitore applicazioni ASP.NET in un ambiente di sviluppo](./media/image5-3.png)
>


### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="99159-161">Scenario 2: Servizio WCF nei contenitori</span><span class="sxs-lookup"><span data-stu-id="99159-161">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="99159-162">Nella figura seguente viene illustrato lo scenario per un'applicazione a 3 livelli con un servizio WCF nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="99159-162">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span> 

> ![Diagramma dell'architettura del servizio WCF nei contenitori in un ambiente di sviluppo semplificato](./media/image5-3.5.png)
>

### <a name="benefits"></a><span data-ttu-id="99159-164">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="99159-164">Benefits</span></span>

<span data-ttu-id="99159-165">Esistono vantaggi rispetto all'esecuzione dell'applicazione monolitica in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="99159-165">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="99159-166">Creare un'immagine per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="99159-166">First, you create an image for the application.</span></span> <span data-ttu-id="99159-167">Da quel momento in poi, ogni distribuzione viene eseguito nello stesso ambiente.</span><span class="sxs-lookup"><span data-stu-id="99159-167">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="99159-168">Ogni contenitore Usa la stessa versione del sistema operativo, ha la stessa versione di dipendenze installata, Usa la stessa versione di .NET framework e viene compilato con lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="99159-168">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="99159-169">In pratica, controllare le dipendenze dell'applicazione tramite un'immagine di Docker.</span><span class="sxs-lookup"><span data-stu-id="99159-169">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="99159-170">Quando si distribuiscono i contenitori, le dipendenze viaggiano con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="99159-170">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="99159-171">Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente di coerente fornito dai contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="99159-171">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="99159-172">I problemi che vengono visualizzati solo con alcune versioni possono essere rilevati immediatamente, invece di replica in un ambiente di gestione temporanea o produzione.</span><span class="sxs-lookup"><span data-stu-id="99159-172">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="99159-173">Differenze in ambienti di sviluppo utilizzati dai membri del team di sviluppo è importante minore quando le applicazioni eseguite nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="99159-173">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="99159-174">Le applicazioni nei contenitori hanno anche una curva di scalabilità orizzontale più semplice.</span><span class="sxs-lookup"><span data-stu-id="99159-174">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="99159-175">Le applicazioni nei contenitori consentono di disporre di altre applicazioni e le istanze del servizio (basate su contenitori) in una macchina virtuale o un computer fisico rispetto alle distribuzioni applicazione regolare per ogni macchina.</span><span class="sxs-lookup"><span data-stu-id="99159-175">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="99159-176">Questo si traduce in maggiore densità e meno necessarie risorse, soprattutto quando si utilizzano orchestrators come Kubernetes o Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="99159-176">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="99159-177">Creazione dei contenitori, in situazioni ideali, non è necessario apportare modifiche al codice dell'applicazione (C\#).</span><span class="sxs-lookup"><span data-stu-id="99159-177">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="99159-178">Nella maggior parte degli scenari, è necessario solo i file di metadati di distribuzione (file Dockerfile e Docker Compose) Docker.</span><span class="sxs-lookup"><span data-stu-id="99159-178">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="99159-179">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99159-179">Next steps</span></span>

<span data-ttu-id="99159-180">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="99159-180">Explore this content more in-depth on the GitHub wiki:</span></span>

  - [<span data-ttu-id="99159-181">Come containerize le app web di .NET Framework con i contenitori di Windows e Docker</span><span class="sxs-lookup"><span data-stu-id="99159-181">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
  - [<span data-ttu-id="99159-182">Aggiunta del supporto di Docker a un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="99159-182">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)



## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="99159-183">Procedura dettagliata 3: Distribuire l'app basata su contenitori di Windows in macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="99159-183">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="99159-184">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="99159-184">Technical walkthrough availability</span></span>

<span data-ttu-id="99159-185">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="99159-185">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="99159-186">Panoramica</span><span class="sxs-lookup"><span data-stu-id="99159-186">Overview</span></span>

<span data-ttu-id="99159-187">La distribuzione in un host Docker in un Windows Server 2016 macchina virtuale (VM) in Azure consente di configurare rapidamente gli ambienti di sviluppo/test/staging.</span><span class="sxs-lookup"><span data-stu-id="99159-187">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="99159-188">Offre inoltre una posizione comune per i tester o gli utenti di business convalidare l'app.</span><span class="sxs-lookup"><span data-stu-id="99159-188">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="99159-189">Macchine virtuali anche possono essere modalità valido come ambienti di produzione un servizio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="99159-189">VMs also can be valid Infrastucture as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="99159-190">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="99159-190">Goals</span></span>

<span data-ttu-id="99159-191">L'obiettivo di questa procedura dettagliata è di illustrare le alternative più, che è necessario quando si distribuiscono i contenitori di Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="99159-191">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="99159-192">Scenari</span><span class="sxs-lookup"><span data-stu-id="99159-192">Scenarios</span></span>

<span data-ttu-id="99159-193">In questa procedura dettagliata sono illustrati i diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="99159-193">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="99159-194">Scenario a: distribuire una macchina virtuale di Azure da un PC di sviluppo tramite una connessione al motore Docker</span><span class="sxs-lookup"><span data-stu-id="99159-194">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Distribuire in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker](./media/image5-4.png)

> <span data-ttu-id="99159-196">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="99159-196">**Figure 5-4.**</span></span> <span data-ttu-id="99159-197">Distribuire in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker</span><span class="sxs-lookup"><span data-stu-id="99159-197">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="99159-198">Scenario b: distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker</span><span class="sxs-lookup"><span data-stu-id="99159-198">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker](./media/image5-5.png)

> <span data-ttu-id="99159-200">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="99159-200">**Figure 5-5.**</span></span> <span data-ttu-id="99159-201">Distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker</span><span class="sxs-lookup"><span data-stu-id="99159-201">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="99159-202">Scenario c: distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="99159-202">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services](./media/image5-6.png)

> <span data-ttu-id="99159-204">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="99159-204">**Figure 5-6.**</span></span> <span data-ttu-id="99159-205">Distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="99159-205">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="99159-206">Macchine virtuali di Azure per i contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="99159-206">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="99159-207">Macchine virtuali di Azure per i contenitori di Windows sono le macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambi con il motore Docker impostato.</span><span class="sxs-lookup"><span data-stu-id="99159-207">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="99159-208">Nella maggior parte dei casi, viene utilizzato Windows Server 2016 in macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-208">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="99159-209">Azure offre attualmente di una macchina virtuale denominata **Windows Server 2016 con contenitori**.</span><span class="sxs-lookup"><span data-stu-id="99159-209">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="99159-210">È possibile utilizzare questa macchina virtuale per provare la nuova funzionalità di contenitore di Windows Server, con Windows Server Core o Nano Server di Windows.</span><span class="sxs-lookup"><span data-stu-id="99159-210">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="99159-211">Immagini del sistema operativo contenitore vengono installate e quindi la macchina virtuale è pronta all'uso con Docker.</span><span class="sxs-lookup"><span data-stu-id="99159-211">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="99159-212">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="99159-212">Benefits</span></span>

<span data-ttu-id="99159-213">Sebbene i contenitori di Windows possono essere distribuiti a macchine virtuali in locale Windows Server 2016, quando si distribuiscono in Azure, è possibile ottenere un modo più semplice per iniziare, con macchine virtuali di contenitore pronto all'uso Windows Server.</span><span class="sxs-lookup"><span data-stu-id="99159-213">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="99159-214">Anche possibile ottenere un percorso online comune che è accessibile ai tester e la scalabilità automatica tramite il set di scalabilità di macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-214">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="99159-215">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99159-215">Next steps</span></span>

<span data-ttu-id="99159-216">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="99159-216">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="99159-217">Procedura dettagliata 4: Distribuire le app basate su contenitori di Windows per le istanze di contenitore di Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="99159-217">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="99159-218">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="99159-218">Technical walkthrough availability</span></span>

<span data-ttu-id="99159-219">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="99159-219">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="99159-220">[Distribuire le App per ACI (istanze del contenitore di Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="99159-220">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="99159-221">Panoramica</span><span class="sxs-lookup"><span data-stu-id="99159-221">Overview</span></span>

<span data-ttu-id="99159-222">[Le istanze di contenitore di Azure (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) è il modo più rapido per dispone di un ambiente di sviluppo/test/gestione temporanea di contenitori in cui è possibile distribuire singole istanze di contenitori.</span><span class="sxs-lookup"><span data-stu-id="99159-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="99159-223">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="99159-223">Goals</span></span>

<span data-ttu-id="99159-224">Quando si distribuiscono i contenitori di Windows Azure contenitore istanze ACI () e come è possibile distribuire le app eShopModernizing in ACI, questa procedura dettagliata illustra gli scenari principali.</span><span class="sxs-lookup"><span data-stu-id="99159-224">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="99159-225">Scenari</span><span class="sxs-lookup"><span data-stu-id="99159-225">Scenarios</span></span>

<span data-ttu-id="99159-226">Possono esistere variazioni su come distribuire le app eShopModernizing in ACI quali la distribuzione di una o tutte le App (app MVC, Web Form app o un servizio WCF).</span><span class="sxs-lookup"><span data-stu-id="99159-226">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="99159-227">Nel seguente scenario illustrato di seguito è possibile visualizzare l'app ASP.NET MVC e il contenitore di SQL Server distribuiti entrambi i parametri come contenitori in ACI (istanze di contenitori di Azure).</span><span class="sxs-lookup"><span data-stu-id="99159-227">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Distribuire in ACI da un ambiente di sviluppo](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="99159-229">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="99159-229">Benefits</span></span>

<span data-ttu-id="99159-230">Istanze di contenitore di Azure semplifica creare e gestire i contenitori di Docker in Azure, senza dover eseguire il provisioning di macchine virtuali o adottare un servizio di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="99159-230">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="99159-231">Con ACI, è possibile distribuire un contenitore di Windows in Azure direttamente ed esporla a internet con un nome di dominio completo (FQDN) in pochi secondi (purché si disponga dell'immagine di contenitore di Windows pronto nel Registro di sistema Docker come Hub Docker o contenitore di Azure Registro di sistema).</span><span class="sxs-lookup"><span data-stu-id="99159-231">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="99159-232">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="99159-232">Considerations</span></span>

<span data-ttu-id="99159-233">Distribuzione di contenitori di Windows con una versione completa di .NET Framework / ASP.NET o SQL Server in Azure contenitore istanze ACI () non è abbastanza veloce per la distribuzione in un Host Docker regolari (ad esempio, Windows Server 2016 con i contenitori di Windows) perché è necessario che l'immagine di Docker scaricato (estratta dal Registro di sistema Docker) ogni volta e le dimensioni dell'immagine contenitore SQL (15.1 GB) e l'immagine di contenitore ASP.NET (13.9 GB) vengono significativamente grandi, tuttavia, è molto più economica rispetto a mantenere il proprio host docker (in modo permanente in linea Windows Server 2016 con macchina virtuale di contenitori di Windows in Azure) per non parlare di un intero agente di orchestrazione, ad esempio Kubernetes in Azure (AKS/ACS) o Azure Service Fabric che, invece, sono un'ottima scelta per le distribuzioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="99159-233">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS/ACS) or Azure Service Fabric which are, on the other hand, great choices for production deployments.</span></span>

<span data-ttu-id="99159-234">Come principale conclusione, utilizzando istanze di contenitori di Azure è un'opzione molto interessante per gli scenari di sviluppo/Test e per le pipeline CI/CD-ROM.</span><span class="sxs-lookup"><span data-stu-id="99159-234">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="99159-235">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99159-235">Next steps</span></span>

<span data-ttu-id="99159-236">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="99159-236">Explore this content more in-depth on the GitHub wiki:</span></span> 

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)


## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="99159-237">Procedura dettagliata 5: Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="99159-237">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="99159-238">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="99159-238">Technical walkthrough availability</span></span>

<span data-ttu-id="99159-239">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="99159-239">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="99159-240">Panoramica</span><span class="sxs-lookup"><span data-stu-id="99159-240">Overview</span></span>

<span data-ttu-id="99159-241">Un'applicazione che si basa sui contenitori di Windows, rapidamente è necessario utilizzare le piattaforme, spostando ulteriormente da macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="99159-241">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="99159-242">Questo è necessario per ottenere facilmente la scalabilità elevata meglio la scalabilità automatica e per un miglioramento significativo automaticamente le distribuzioni e controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="99159-242">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="99159-243">È possibile raggiungere questi obiettivi tramite l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile in [servizi contenitore Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="99159-243">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="99159-244">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="99159-244">Goals</span></span>

<span data-ttu-id="99159-245">L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su contenitore di Windows per Kubernetes (chiamato anche *K8s*) nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-245">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="99159-246">La distribuzione in Kubernetes da zero è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="99159-246">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="99159-247">Distribuire un cluster Kubernetes al servizio di contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-247">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="99159-248">Distribuire l'applicazione e le relative risorse nel cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="99159-248">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="99159-249">Scenari</span><span class="sxs-lookup"><span data-stu-id="99159-249">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="99159-250">Scenario a: distribuire direttamente a un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="99159-250">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo](./media/image5-7.png)

> <span data-ttu-id="99159-252">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="99159-252">**Figure 5-7.**</span></span> <span data-ttu-id="99159-253">Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="99159-253">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="99159-254">Scenario b: distribuire a un cluster Kubernetes CI/CD pipeline in Team Services</span><span class="sxs-lookup"><span data-stu-id="99159-254">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Distribuire un cluster Kubernetes dalla pipeline CI/CD-ROM in Team Services](./media/image5-8.png)

> <span data-ttu-id="99159-256">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="99159-256">**Figure 5-8.**</span></span> <span data-ttu-id="99159-257">Distribuire un cluster Kubernetes dalla pipeline CI/CD-ROM in Team Services</span><span class="sxs-lookup"><span data-stu-id="99159-257">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="99159-258">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="99159-258">Benefits</span></span>

<span data-ttu-id="99159-259">Esistono numerosi vantaggi per la distribuzione a un cluster in Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="99159-259">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="99159-260">Il vantaggio più importante è che si ottiene un ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitori, si desidera utilizzare (scalabilità interna in nodi esistenti) e in base al numero di nodi o le macchine virtuali in (il cluster scalabilità globale del cluster).</span><span class="sxs-lookup"><span data-stu-id="99159-260">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="99159-261">Il servizio contenitore di Azure consente di ottimizzare tecnologie e strumenti open source più diffusi in particolare per Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-261">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="99159-262">È possibile ottenere una soluzione aperta che offre la portabilità, per i contenitori e per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="99159-262">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="99159-263">Selezionare la dimensione, il numero di host, e orchestrator strumenti-Container servizio gestisce tutti gli altri elementi.</span><span class="sxs-lookup"><span data-stu-id="99159-263">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="99159-264">Con Kubernetes, gli sviluppatori possono sullo stato da considerare macchine fisiche e virtuali, per la pianificazione di un'infrastruttura incentrato sul contenitore che facilita le seguenti funzionalità, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="99159-264">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="99159-265">In base a più contenitori di applicazioni</span><span class="sxs-lookup"><span data-stu-id="99159-265">Applications based on multiple containers</span></span>

- <span data-ttu-id="99159-266">La replica delle istanze di contenitori e il ridimensionamento orizzontale</span><span class="sxs-lookup"><span data-stu-id="99159-266">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="99159-267">Denominazione e individuazione (ad esempio, DNS interno)</span><span class="sxs-lookup"><span data-stu-id="99159-267">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="99159-268">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="99159-268">Balancing loads</span></span>

- <span data-ttu-id="99159-269">Gli aggiornamenti in sequenza</span><span class="sxs-lookup"><span data-stu-id="99159-269">Rolling updates</span></span>

- <span data-ttu-id="99159-270">Distribuzione di segreti</span><span class="sxs-lookup"><span data-stu-id="99159-270">Distributing secrets</span></span>

- <span data-ttu-id="99159-271">Controlli di integrità dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="99159-271">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="99159-272">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99159-272">Next steps</span></span>

<span data-ttu-id="99159-273">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="99159-273">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="99159-274">Procedura dettagliata 6: Distribuire le app basate su contenitori di Windows Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="99159-274">Walkthrough 6: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="99159-275">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="99159-275">Technical walkthrough availability</span></span>

<span data-ttu-id="99159-276">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="99159-276">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="99159-277">Panoramica</span><span class="sxs-lookup"><span data-stu-id="99159-277">Overview</span></span>

<span data-ttu-id="99159-278">Un'applicazione basata su contenitori di Windows rapidamente deve utilizzare le piattaforme, spostando ulteriormente da macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="99159-278">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="99159-279">Questo è necessario per ottenere facilmente la scalabilità elevata meglio la scalabilità automatica e per un miglioramento significativo automaticamente le distribuzioni e controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="99159-279">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="99159-280">È possibile raggiungere questi obiettivi tramite orchestrator Azure Service Fabric è disponibile nel cloud di Azure, ma è anche disponibile per l'utilizzo di on-premise, o anche in un cloud pubblico diverso.</span><span class="sxs-lookup"><span data-stu-id="99159-280">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="99159-281">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="99159-281">Goals</span></span>

<span data-ttu-id="99159-282">L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su Windows contenitore a un cluster di Service Fabric in Azure.</span><span class="sxs-lookup"><span data-stu-id="99159-282">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="99159-283">Distribuzione di Service Fabric da zero è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="99159-283">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="99159-284">Distribuire un cluster di Service Fabric in Azure (o in un ambiente diverso).</span><span class="sxs-lookup"><span data-stu-id="99159-284">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="99159-285">Distribuire l'applicazione e le relative risorse nel cluster di Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="99159-285">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="99159-286">Scenari</span><span class="sxs-lookup"><span data-stu-id="99159-286">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="99159-287">Scenario a: distribuire direttamente a un cluster di Service Fabric da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="99159-287">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo](./media/image5-9.png)

> <span data-ttu-id="99159-289">**Figura 5-9.**</span><span class="sxs-lookup"><span data-stu-id="99159-289">**Figure 5-9.**</span></span> <span data-ttu-id="99159-290">Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="99159-290">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="99159-291">Scenario b: distribuire a un cluster di Service Fabric dal CI/CD-ROM pipeline in Team Services</span><span class="sxs-lookup"><span data-stu-id="99159-291">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Distribuire un cluster di Service Fabric dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services](./media/image5-10.png)

> <span data-ttu-id="99159-293">**Figura 5-10.**</span><span class="sxs-lookup"><span data-stu-id="99159-293">**Figure 5-10.**</span></span> <span data-ttu-id="99159-294">Distribuire un cluster di Service Fabric dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="99159-294">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="99159-295">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="99159-295">Benefits</span></span>

<span data-ttu-id="99159-296">I vantaggi della distribuzione a un cluster nell'infrastruttura del servizio sono simili ai vantaggi dell'utilizzo Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="99159-296">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="99159-297">Una differenza, tuttavia, è che Service Fabric è un ambiente di produzione più avanzato per le applicazioni di Windows rispetto a Kubernetes, ovvero in una fase beta per i contenitori di Windows nella Kubernetes versione 1.9 (2017 dicembre).</span><span class="sxs-lookup"><span data-stu-id="99159-297">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="99159-298">Kubernetes è un ambiente più avanzato per Linux.</span><span class="sxs-lookup"><span data-stu-id="99159-298">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="99159-299">Il principale vantaggio dell'utilizzo di Azure Service Fabric è che si dispone di un ambiente di ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitori, si desidera utilizzare (scalabilità interna in nodi esistenti) e in base al numero di i nodi o macchine virtuali in cluster (scalabilità globale del cluster).</span><span class="sxs-lookup"><span data-stu-id="99159-299">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="99159-300">Azure Service Fabric offre portabilità per i contenitori e per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="99159-300">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="99159-301">È un'infrastruttura del servizio cluster in Azure oppure installarlo in locale nel proprio Data Center.</span><span class="sxs-lookup"><span data-stu-id="99159-301">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="99159-302">È anche possibile installare un cluster di Service Fabric in un cloud diverso, ad esempio [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="99159-302">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="99159-303">Con Service Fabric, gli sviluppatori possono sullo stato da considerare macchine fisiche e virtuali per la pianificazione di un'infrastruttura incentrato sul contenitore che facilita le seguenti funzionalità, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="99159-303">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="99159-304">Applicazioni basate su più contenitori.</span><span class="sxs-lookup"><span data-stu-id="99159-304">Applications based on multiple containers.</span></span>

- <span data-ttu-id="99159-305">La replica di istanze di contenitori e scalabilità orizzontale automatica.</span><span class="sxs-lookup"><span data-stu-id="99159-305">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="99159-306">Denominazione e individuazione (ad esempio, DNS interno).</span><span class="sxs-lookup"><span data-stu-id="99159-306">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="99159-307">Bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="99159-307">Balancing loads.</span></span>

- <span data-ttu-id="99159-308">Aggiornamenti in sequenza.</span><span class="sxs-lookup"><span data-stu-id="99159-308">Rolling updates.</span></span>

- <span data-ttu-id="99159-309">Distribuire i segreti.</span><span class="sxs-lookup"><span data-stu-id="99159-309">Distributing secrets.</span></span>

- <span data-ttu-id="99159-310">Controlla l'integrità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="99159-310">Application health checks.</span></span>

<span data-ttu-id="99159-311">Le seguenti funzionalità sono esclusive nell'infrastruttura di servizio (rispetto a altro orchestrators):</span><span class="sxs-lookup"><span data-stu-id="99159-311">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="99159-312">Funzionalità di servizi con stato, tramite il modello applicazione servizi affidabili.</span><span class="sxs-lookup"><span data-stu-id="99159-312">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="99159-313">Modello di attori, tramite il modello di applicazione Reliable Actors.</span><span class="sxs-lookup"><span data-stu-id="99159-313">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="99159-314">Distribuire processi ossa bare, oltre ai contenitori di Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="99159-314">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="99159-315">Gli aggiornamenti in sequenza e controlli di integrità avanzati.</span><span class="sxs-lookup"><span data-stu-id="99159-315">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="99159-316">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99159-316">Next steps</span></span>

<span data-ttu-id="99159-317">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="99159-317">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
<span data-ttu-id="99159-318">[Precedente](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Successivo](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="99159-318">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
