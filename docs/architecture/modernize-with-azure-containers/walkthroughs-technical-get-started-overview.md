---
title: Procedure dettagliate e panoramica introduttiva tecnica
description: Modernizza le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows Panoramica delle procedure dettagliate e delle informazioni tecniche
ms.date: 04/28/2018
ms.openlocfilehash: cff418d9b6e931a3082d8a2f8b818e7275139578
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987869"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="5606e-103">Procedure dettagliate e panoramica introduttiva tecnica</span><span class="sxs-lookup"><span data-stu-id="5606e-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="5606e-104">Per limitare le dimensioni di questo e-book, sono stati resi disponibili ulteriori documentazione tecnica e le procedure dettagliate complete in un repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="5606e-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="5606e-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span><span class="sxs-lookup"><span data-stu-id="5606e-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="5606e-106">Nelle sezioni seguenti viene illustrato il significato di ogni procedura dettagliata, i relativi obiettivi e la visione di alto livello e viene fornito un diagramma delle attività coinvolte.</span><span class="sxs-lookup"><span data-stu-id="5606e-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="5606e-107">È possibile ottenere le procedure dettagliate stessi nel *wiki eShopModernizing* apps GitHub repo in <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span><span class="sxs-lookup"><span data-stu-id="5606e-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="5606e-108">Elenco delle procedure dettagliate tecniche</span><span class="sxs-lookup"><span data-stu-id="5606e-108">Technical walkthrough list</span></span>

<span data-ttu-id="5606e-109">Le procedure dettagliate introduttive seguenti forniscono indicazioni tecniche coerenti e complete per le app di esempio che è possibile sollevare e spostare usando i contenitori e quindi spostarsi usando più opzioni di distribuzione in Azure.The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span><span class="sxs-lookup"><span data-stu-id="5606e-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="5606e-110">Ognuna delle procedure dettagliate seguenti usa le nuove app eShopLegacy ed eShopModernizing di esempio, disponibili su GitHub all'indirizzo <https://github.com/dotnet-architecture/eShopModernizing>.</span><span class="sxs-lookup"><span data-stu-id="5606e-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="5606e-111">**Presentazione delle app legacy di eShop (app di base da modernizzare)**</span><span class="sxs-lookup"><span data-stu-id="5606e-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="5606e-112">**Contenitore delle app Web di ASP.NET esistenti (WebForms & MVC) con contenitori Di WindowsContainerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span><span class="sxs-lookup"><span data-stu-id="5606e-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="5606e-113">**Contenitore dei servizi WCF esistenti (app a più livelli) con i contenitori di WindowsContainerize your existing WCF services (N-Tier apps) with Windows Containers**</span><span class="sxs-lookup"><span data-stu-id="5606e-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="5606e-114">**Distribuire l'app basata su contenitori di Windows nelle macchine virtuali di AzureDeploy your Windows Containers-based app to Azure VMs**</span><span class="sxs-lookup"><span data-stu-id="5606e-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="5606e-115">**Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di AzureDeploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span><span class="sxs-lookup"><span data-stu-id="5606e-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="5606e-116">Procedura dettagliata 1: Tour delle app legacy di eShop</span><span class="sxs-lookup"><span data-stu-id="5606e-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="5606e-117">Disponibilità della procedura dettagliata tecnica</span><span class="sxs-lookup"><span data-stu-id="5606e-117">Technical walkthrough availability</span></span>

<span data-ttu-id="5606e-118">La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="5606e-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="5606e-119">EShopModernizing procedure dettagliate wiki</span><span class="sxs-lookup"><span data-stu-id="5606e-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="5606e-120">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5606e-120">Overview</span></span>

<span data-ttu-id="5606e-121">In questa procedura dettagliata, è possibile esplorare l'implementazione iniziale di tre applicazioni legacy di esempio.</span><span class="sxs-lookup"><span data-stu-id="5606e-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="5606e-122">Le prime due app Web di esempio hanno un'architettura monolitica e sono state create usando ASP.NET classici.</span><span class="sxs-lookup"><span data-stu-id="5606e-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="5606e-123">Un'applicazione è basata su ASP.NET MVC 4.x; la seconda applicazione è basata su ASP.NET Web Form 4.x.</span><span class="sxs-lookup"><span data-stu-id="5606e-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="5606e-124">La terza app è un'app a 3 livelli composta da un'app WinForms client e da un servizio [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) lato server.</span><span class="sxs-lookup"><span data-stu-id="5606e-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="5606e-125">Tutte queste applicazioni sono disponibili presso il [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="5606e-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="5606e-126">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5606e-126">Goals</span></span>

<span data-ttu-id="5606e-127">L'obiettivo principale di questa procedura dettagliata è semplicemente quello di acquisire familiarità con queste app e con il codice e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5606e-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="5606e-128">È possibile configurare le app in modo che generino e utilizzino dati fittizi, senza usare il database SQL, a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="5606e-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="5606e-129">Questa configurazione facoltativa si basa sull'inserimento delle dipendenze, in modo disaccoppiato.</span><span class="sxs-lookup"><span data-stu-id="5606e-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="5606e-130">Scenario 1: ASP.NET di app Web</span><span class="sxs-lookup"><span data-stu-id="5606e-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="5606e-131">La figura seguente mostra lo scenario semplice delle applicazioni Web di ASP.NET legacy originali.</span><span class="sxs-lookup"><span data-stu-id="5606e-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Scenario di architettura semplice delle applicazioni Web ASP.NET legacy originali](./media/image5-1.png)

<span data-ttu-id="5606e-133">Dal punto di vista del dominio aziendale, entrambe le app offrono le stesse funzionalità di gestione del catalogo.</span><span class="sxs-lookup"><span data-stu-id="5606e-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="5606e-134">I membri del team aziendale di eShop utilizzerebbero l'app per visualizzare e modificare il catalogo prodotti.</span><span class="sxs-lookup"><span data-stu-id="5606e-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="5606e-135">La figura seguente mostra le schermate iniziali dell'app.</span><span class="sxs-lookup"><span data-stu-id="5606e-135">The next figure shows the initial app screenshots.</span></span>

![ASP.NET le applicazioni Web Form MVC e ASP.NET (tecnologie esistenti/legacy)](./media/image5-2.png)

<span data-ttu-id="5606e-137">Dipendenze in ASP.NET 4.x o versioni precedenti (per MVC o per Web Form) significa che queste applicazioni non verranno eseguite in .NET Core a meno che il codice non venga completamente riscritto utilizzando ASP.NET MVC principale.</span><span class="sxs-lookup"><span data-stu-id="5606e-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="5606e-138">Scenario 2: servizio WCF e app client WinForms (app a 3 livelli)Scenario 2: WCF service and WinForms client app (3-Tier app)</span><span class="sxs-lookup"><span data-stu-id="5606e-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="5606e-139">La figura seguente mostra lo scenario semplice dell'applicazione legacy a 3 livelli originale.</span><span class="sxs-lookup"><span data-stu-id="5606e-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Scenario di architettura semplice dell'app a 3 livelli legacy originale con un servizio WCF e un'app client WinForms](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="5606e-141">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="5606e-141">Benefits</span></span>

<span data-ttu-id="5606e-142">I vantaggi di questa procedura dettagliata sono semplici: è sufficiente acquisire familiarità con il codice e le app iniziali.</span><span class="sxs-lookup"><span data-stu-id="5606e-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="5606e-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5606e-143">Next steps</span></span>

<span data-ttu-id="5606e-144">Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:</span><span class="sxs-lookup"><span data-stu-id="5606e-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="5606e-145">Tour sulla linea di base ASP.NET le app MVC e Web Form "legacy"</span><span class="sxs-lookup"><span data-stu-id="5606e-145">Tour on the baseline ASP.NET MVC and Web Forms "legacy" apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="5606e-146">Tour sul servizio WCF di base e sull'app "legacy" di WindowsForms (3 livelli)</span><span class="sxs-lookup"><span data-stu-id="5606e-146">Tour on the baseline WCF service and WinForms (3-Tier) "legacy" app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="5606e-147">Procedura dettagliata 2: Containerize le applicazioni .NET esistenti con contenitori di WindowsWalkthrough 2: Containerize your existing .NET applications with Windows Containers</span><span class="sxs-lookup"><span data-stu-id="5606e-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="5606e-148">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5606e-148">Overview</span></span>

<span data-ttu-id="5606e-149">Usare i contenitori di Windows per migliorare la distribuzione di applicazioni .NET esistenti, come quelle basate su MVC, Web Form o WCF, in ambienti di produzione, sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="5606e-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="5606e-150">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5606e-150">Goals</span></span>

<span data-ttu-id="5606e-151">L'obiettivo di questa procedura dettagliata è illustrare diverse opzioni per il contenitore di un'applicazione .NET Framework esistente.</span><span class="sxs-lookup"><span data-stu-id="5606e-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="5606e-152">È possibile:</span><span class="sxs-lookup"><span data-stu-id="5606e-152">You can:</span></span>

- <span data-ttu-id="5606e-153">Containerize l'applicazione utilizzando [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="5606e-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="5606e-154">Contenitore dell'applicazione aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/), quindi utilizzando [l'interfaccia della riga di comando di Docker](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="5606e-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="5606e-155">Contenitore dell'applicazione utilizzando lo strumento [Img2Docker](https://github.com/docker/communitytools-image2docker-win) (uno strumento open source da Docker).</span><span class="sxs-lookup"><span data-stu-id="5606e-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="5606e-156">Questa procedura dettagliata è incentrata sull'approccio Visual Studio 2017 Tools for Docker, ma gli altri due approcci sono abbastanza simili per quanto riguarda l'utilizzo di Dockerfiles.This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the two approaches are fairly similar in regard to using Dockerfiles.</span><span class="sxs-lookup"><span data-stu-id="5606e-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="5606e-157">Scenario 1: app Web ASP.NET in contenitore</span><span class="sxs-lookup"><span data-stu-id="5606e-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="5606e-158">Figura seguente viene illustrato lo scenario per contenitori eShop applicazioni web legacy.</span><span class="sxs-lookup"><span data-stu-id="5606e-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Diagramma dell'architettura semplificato delle applicazioni in contenitore ASP.NET in un ambiente di sviluppo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="5606e-160">Scenario 2: servizio WCF con contenitoreScenario 2: Containerized WCF service</span><span class="sxs-lookup"><span data-stu-id="5606e-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="5606e-161">Figura seguente viene illustrato lo scenario per un'applicazione a 3 livelli con un servizio WCF contenitore.</span><span class="sxs-lookup"><span data-stu-id="5606e-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Diagramma dell'architettura semplificato del servizio WCF con contenitore in un ambiente di sviluppo](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="5606e-163">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="5606e-163">Benefits</span></span>

<span data-ttu-id="5606e-164">L'esecuzione dell'applicazione monolitica in un contenitore presenta dei vantaggi.</span><span class="sxs-lookup"><span data-stu-id="5606e-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="5606e-165">In primo luogo, si crea un'immagine per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5606e-165">First, you create an image for the application.</span></span> <span data-ttu-id="5606e-166">Da quel momento in everso, ogni distribuzione viene eseguita nello stesso ambiente.</span><span class="sxs-lookup"><span data-stu-id="5606e-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="5606e-167">Ogni contenitore usa la stessa versione del sistema operativo, ha la stessa versione delle dipendenze installata, usa la stessa versione di .NET Framework e viene compilato utilizzando lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="5606e-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="5606e-168">Fondamentalmente, è possibile controllare le dipendenze dell'applicazione utilizzando un'immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="5606e-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="5606e-169">Le dipendenze viaggiano con l'applicazione quando si distribuiscono i contenitori.</span><span class="sxs-lookup"><span data-stu-id="5606e-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="5606e-170">Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente coerente fornito dai contenitori di Windows.An additional vantaggio is that developers can run the application in the consistent environment that's provided by Windows Containers.</span><span class="sxs-lookup"><span data-stu-id="5606e-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="5606e-171">I problemi che appaiono solo con determinate versioni possono essere individuati immediatamente, anziché emergere in un ambiente di gestione temporanea o di produzione.</span><span class="sxs-lookup"><span data-stu-id="5606e-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="5606e-172">Le differenze negli ambienti di sviluppo utilizzati dai membri del team di sviluppo contano meno quando le applicazioni vengono eseguite in contenitori.</span><span class="sxs-lookup"><span data-stu-id="5606e-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="5606e-173">Le applicazioni containerizzate hanno anche una curva di scalabilità orizzontale più piatta.</span><span class="sxs-lookup"><span data-stu-id="5606e-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="5606e-174">Le app containerizzate consentono di avere più istanze di applicazioni e servizi (basate su contenitori) in una macchina virtuale o in una macchina fisica rispetto alle normali distribuzioni di applicazioni per computer.</span><span class="sxs-lookup"><span data-stu-id="5606e-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="5606e-175">Ciò si traduce in una maggiore densità e in un numero inferiore di risorse necessarie, soprattutto quando si utilizzano orchestratori come Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="5606e-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="5606e-176">La containerizzazione, in situazioni ideali, non richiede di\#apportare modifiche al codice dell'applicazione (C ).</span><span class="sxs-lookup"><span data-stu-id="5606e-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="5606e-177">Nella maggior parte degli scenari sono necessari solo i file di metadati di distribuzione Docker (file Dockerfiles e Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="5606e-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="5606e-178">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5606e-178">Next steps</span></span>

<span data-ttu-id="5606e-179">Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:</span><span class="sxs-lookup"><span data-stu-id="5606e-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="5606e-180">Come creare un contenitore delle app Web di .NET Framework con contenitori e Docker di Windows</span><span class="sxs-lookup"><span data-stu-id="5606e-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="5606e-181">Aggiunta del supporto Docker a un servizio WCFAdding Docker Support to a WCF service</span><span class="sxs-lookup"><span data-stu-id="5606e-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="5606e-182">Procedura dettagliata 3: Distribuire l'app basata su contenitori di Windows nelle macchine virtuali di AzureWalkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span><span class="sxs-lookup"><span data-stu-id="5606e-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="5606e-183">Disponibilità della procedura dettagliata tecnica</span><span class="sxs-lookup"><span data-stu-id="5606e-183">Technical walkthrough availability</span></span>

<span data-ttu-id="5606e-184">La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="5606e-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="5606e-185">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5606e-185">Overview</span></span>

<span data-ttu-id="5606e-186">La distribuzione in un host Docker in una macchina virtuale Windows Server 2016 (VM) in Azure consente di configurare rapidamente ambienti di sviluppo/test/gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="5606e-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="5606e-187">Fornisce inoltre un'area comune per i tester o gli utenti aziendali per convalidare l'app.</span><span class="sxs-lookup"><span data-stu-id="5606e-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="5606e-188">Le macchine virtuali possono anche essere ambienti di produzione IaaS (Infrastructure as a Service) validi.</span><span class="sxs-lookup"><span data-stu-id="5606e-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="5606e-189">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5606e-189">Goals</span></span>

<span data-ttu-id="5606e-190">L'obiettivo di questa procedura dettagliata è mostrare le alternative multiple disponibili quando si distribuiscono contenitori di Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="5606e-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="5606e-191">Scenari</span><span class="sxs-lookup"><span data-stu-id="5606e-191">Scenarios</span></span>

<span data-ttu-id="5606e-192">In questa procedura dettagliata vengono descritti diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="5606e-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="5606e-193">Scenario A: Distribuire in una macchina virtuale di Azure da un PC di sviluppo tramite la connessione a Docker EngineScenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span><span class="sxs-lookup"><span data-stu-id="5606e-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Distribuire in una macchina virtuale di Azure da un PC di sviluppo tramite una connessione del motore DockerDeploy to an Azure VM from a dev PC through a Docker Engine connection](./media/image5-4.png)

<span data-ttu-id="5606e-195">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="5606e-195">**Figure 5-4.**</span></span> <span data-ttu-id="5606e-196">Distribuire in una macchina virtuale di Azure da un PC di sviluppo tramite una connessione del motore DockerDeploy to an Azure VM from a dev PC through a Docker Engine connection</span><span class="sxs-lookup"><span data-stu-id="5606e-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="5606e-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span><span class="sxs-lookup"><span data-stu-id="5606e-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Distribuire in una macchina virtuale di Azure tramite un Registro di sistema DockerDeploy to an Azure VM through a Docker Registry](./media/image5-5.png)

<span data-ttu-id="5606e-199">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="5606e-199">**Figure 5-5.**</span></span> <span data-ttu-id="5606e-200">Distribuire in una macchina virtuale di Azure tramite un Registro di sistema DockerDeploy to an Azure VM through a Docker Registry</span><span class="sxs-lookup"><span data-stu-id="5606e-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="5606e-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="5606e-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Distribuire in una macchina virtuale di Azure da pipeline di CI/CD nei servizi DevOps di AzureDeploy to an Azure VM from CI/CD pipelines in Azure DevOps Services](./media/image5-6.png)

<span data-ttu-id="5606e-203">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="5606e-203">**Figure 5-6.**</span></span> <span data-ttu-id="5606e-204">Distribuire in una macchina virtuale di Azure da pipeline di CI/CD nei servizi DevOps di AzureDeploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="5606e-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="5606e-205">Azure VMs for Windows Containers</span><span class="sxs-lookup"><span data-stu-id="5606e-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="5606e-206">Le macchine virtuali di Azure per i contenitori di Windows sono macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambe con il motore Docker configurato.</span><span class="sxs-lookup"><span data-stu-id="5606e-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="5606e-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span><span class="sxs-lookup"><span data-stu-id="5606e-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="5606e-208">Azure fornisce attualmente una macchina virtuale denominata **Windows Server 2016 con contenitori.**</span><span class="sxs-lookup"><span data-stu-id="5606e-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="5606e-209">È possibile utilizzare questa macchina virtuale per provare la nuova funzionalità Contenitore Windows Server, con Windows Server Core o Windows Nano Server.You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="5606e-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="5606e-210">Vengono installate le immagini del sistema operativo contenitore e quindi la macchina virtuale è pronta per l'uso con Docker.Container OS images are installed, and then the VM is ready to use with Docker.</span><span class="sxs-lookup"><span data-stu-id="5606e-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="5606e-211">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="5606e-211">Benefits</span></span>

<span data-ttu-id="5606e-212">Anche se i contenitori di Windows possono essere distribuiti nelle macchine virtuali Windows Server 2016 locali, quando si distribuisce in Azure, si ottiene un modo più semplice per iniziare, con macchine virtuali Windows Server Container pronte all'uso.</span><span class="sxs-lookup"><span data-stu-id="5606e-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="5606e-213">Si ottiene anche una posizione online comune accessibile ai tester e scalabilità automatica tramite i set di scalabilità delle macchine virtuali di Azure.You also get a common online location that's accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span><span class="sxs-lookup"><span data-stu-id="5606e-213">You also get a common online location that's accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="5606e-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5606e-214">Next steps</span></span>

<span data-ttu-id="5606e-215">Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:</span><span class="sxs-lookup"><span data-stu-id="5606e-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="5606e-216">Procedura dettagliata 4: Distribuire le app basate su contenitori di Windows in istanze di contenitori di Azure</span><span class="sxs-lookup"><span data-stu-id="5606e-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="5606e-217">Disponibilità della procedura dettagliata tecnica</span><span class="sxs-lookup"><span data-stu-id="5606e-217">Technical walkthrough availability</span></span>

<span data-ttu-id="5606e-218">La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="5606e-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="5606e-219">[Distribuzione delle app in ACI (istanze del contenitore di Azure)Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="5606e-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="5606e-220">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5606e-220">Overview</span></span>

<span data-ttu-id="5606e-221">[Le istanze del contenitore di Azure (ACI)](https://docs.microsoft.com/azure/container-instances/) è il modo più rapido per avere un ambiente di sviluppo/test/staging per i contenitori in cui è possibile distribuire singole istanze di contenitori.</span><span class="sxs-lookup"><span data-stu-id="5606e-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="5606e-222">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5606e-222">Goals</span></span>

<span data-ttu-id="5606e-223">Questa procedura dettagliata illustra gli scenari principali per la distribuzione di contenitori di Windows in istanze di contenitori di Azure (ACI) e come è possibile distribuire le app eShopModernizing in ACI.</span><span class="sxs-lookup"><span data-stu-id="5606e-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="5606e-224">Scenari</span><span class="sxs-lookup"><span data-stu-id="5606e-224">Scenarios</span></span>

<span data-ttu-id="5606e-225">Possono esserci variazioni sulla distribuzione delle app eShopModernizing in ACI, ad esempio la distribuzione di una o tutte le app (app MVC, app WebForms o servizio WCF).</span><span class="sxs-lookup"><span data-stu-id="5606e-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="5606e-226">Nello scenario seguente illustrato di seguito è possibile visualizzare l'app MVC ASP.NET più il contenitore SQL Server entrambi distribuiti come contenitori in aCI (istanze del contenitore di Azure).</span><span class="sxs-lookup"><span data-stu-id="5606e-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Distribuire in ACI da un ambiente di sviluppoDeploy to ACI from a development environment](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="5606e-228">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="5606e-228">Benefits</span></span>

<span data-ttu-id="5606e-229">Istanze di Azure Container semplifica la creazione e gestione di contenitori Docker in Azure, senza dover eseguire il provisioning di macchine virtuali o di adottare un servizio di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="5606e-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="5606e-230">Con ACI, è possibile distribuire direttamente un contenitore Windows in Azure ed esporlo a Internet con un nome di dominio completo (FQDN) in pochi secondi (a condizione che l'immagine del contenitore Di Windows sia pronta in un Registro di sistema Docker come Docker Hub o Registro di sistema del contenitore di Azure).</span><span class="sxs-lookup"><span data-stu-id="5606e-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="5606e-231">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="5606e-231">Considerations</span></span>

<span data-ttu-id="5606e-232">La distribuzione di contenitori di Windows con .NET Framework / ASP.NET completi o SQL Server in istanze di contenitori di Azure (ACI) non è così veloce quanto la distribuzione in un normale host Docker (ad esempio Windows Server 2016 con contenitori di Windows) perché l'immagine Docker deve essere scaricata (estratta dal Registro di sistema Docker) ogni volta e le dimensioni dell'immagine del contenitore SQL (15,1 GB) e l'immagine del contenitore di ASP.NET (13,9 GB) sono significativamente in grandi dimensioni, e le dimensioni dell'immagine del contenitore SQL (15,1 GB) e l'immagine del contenitore di ASP.NET (13,9 GB) sono in genere, ovvero le dimensioni dell'immagine del contenitore SQL (15,1 GB) e l'immagine del contenitore di ASP.NET (13,9 GB) tuttavia è molto più economico che mantenere il proprio host docker (in modo permanente on-line Windows Server 2016 con Windows Containers VM in Azure) per non parlare di un intero orchestrator come Kubernetes in Azure (AKS) che è, d'altra parte, un'ottima scelta per le distribuzioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="5606e-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="5606e-233">Come conclusione principale, l'uso delle istanze di Azure Container è un'opzione molto interessante per gli scenari di sviluppo/test e per le pipeline CI/CD.</span><span class="sxs-lookup"><span data-stu-id="5606e-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5606e-234">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5606e-234">Next steps</span></span>

<span data-ttu-id="5606e-235">Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:</span><span class="sxs-lookup"><span data-stu-id="5606e-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="5606e-236">Procedura dettagliata 5: Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di AzureWalkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span><span class="sxs-lookup"><span data-stu-id="5606e-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="5606e-237">Disponibilità della procedura dettagliata tecnica</span><span class="sxs-lookup"><span data-stu-id="5606e-237">Technical walkthrough availability</span></span>

<span data-ttu-id="5606e-238">La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="5606e-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="5606e-239">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5606e-239">Overview</span></span>

<span data-ttu-id="5606e-240">Un'applicazione basata su contenitori Windows dovrà rapidamente usare le piattaforme, allontanandosi ancora di più dalle macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="5606e-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="5606e-241">Ciò è necessario per ottenere facilmente un'elevata scalabilità e una migliore scalabilità automatizzata e per un miglioramento significativo nelle distribuzioni automatizzate e nel controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="5606e-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="5606e-242">È possibile raggiungere questi obiettivi usando l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile in [Servizi contenitore](https://azure.microsoft.com/services/container-service/)di Azure .</span><span class="sxs-lookup"><span data-stu-id="5606e-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="5606e-243">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5606e-243">Goals</span></span>

<span data-ttu-id="5606e-244">L'obiettivo di questa procedura dettagliata è imparare a distribuire un'applicazione basata su contenitore Windows a Kubernetes (denominata anche *K8s*) nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="5606e-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="5606e-245">La distribuzione a Kubernetes da zero è un processo in due fasi:</span><span class="sxs-lookup"><span data-stu-id="5606e-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="5606e-246">Distribuire un cluster Kubernetes nel servizio contenitore di Azure.Deploy a Kubernetes cluster to Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="5606e-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="5606e-247">Distribuire l'applicazione e le risorse correlate nel cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="5606e-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="5606e-248">Scenari</span><span class="sxs-lookup"><span data-stu-id="5606e-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="5606e-249">Scenario A: Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppoScenario A: Deploy directly to a Kubernetes cluster from a dev environment</span><span class="sxs-lookup"><span data-stu-id="5606e-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppoDeploy directly to a Kubernetes cluster from a development environment](./media/image5-7.png)

<span data-ttu-id="5606e-251">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="5606e-251">**Figure 5-7.**</span></span> <span data-ttu-id="5606e-252">Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppoDeploy directly to a Kubernetes cluster from a development environment</span><span class="sxs-lookup"><span data-stu-id="5606e-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="5606e-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="5606e-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Distribuire in un cluster Kubernetes da pipeline DI CI/CD nei servizi DevOps di AzureDeploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services](./media/image5-8.png)

<span data-ttu-id="5606e-255">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="5606e-255">**Figure 5-8.**</span></span> <span data-ttu-id="5606e-256">Distribuire in un cluster Kubernetes da pipeline DI CI/CD nei servizi DevOps di AzureDeploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="5606e-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="5606e-257">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="5606e-257">Benefits</span></span>

<span data-ttu-id="5606e-258">La distribuzione in un cluster in Kubernetes offre numerosi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="5606e-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="5606e-259">Il vantaggio principale è che si ottiene un ambiente pronto per la produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze del contenitore che si desidera utilizzare (scalabilità interna nei nodi esistenti) e in base al numero di nodi o macchine virtuali nel cluster (scalabilità globale del cluster).</span><span class="sxs-lookup"><span data-stu-id="5606e-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="5606e-260">Il servizio contenitore di Azure ottimizza gli strumenti e le tecnologie open source più diffusi in modo specifico per Azure.Azure Container Service optimizes popular open source tools and technologies specifically for Azure.</span><span class="sxs-lookup"><span data-stu-id="5606e-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="5606e-261">Si ottiene una soluzione aperta che offre portabilità, sia per i contenitori che per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5606e-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="5606e-262">Selezionare la dimensione, il numero di host e gli strumenti dell'agente di orchestrazione-servizio contenitore gestisce tutto il resto.</span><span class="sxs-lookup"><span data-stu-id="5606e-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="5606e-263">Con Kubernetes, gli sviluppatori possono passare dal pensare alle macchine fisiche e virtuali, alla pianificazione di un'infrastruttura incentrata sui contenitori che facilita le seguenti funzionalità, tra le altre:</span><span class="sxs-lookup"><span data-stu-id="5606e-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="5606e-264">Applicazioni basate su più contenitori</span><span class="sxs-lookup"><span data-stu-id="5606e-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="5606e-265">Replica delle istanze del contenitore e ridimensionamento automatico orizzontaleReplicating container instances and horizontal autoscaling</span><span class="sxs-lookup"><span data-stu-id="5606e-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="5606e-266">Denominazione e individuazione (ad esempio, DNS interno)</span><span class="sxs-lookup"><span data-stu-id="5606e-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="5606e-267">Bilanciamento dei carichi</span><span class="sxs-lookup"><span data-stu-id="5606e-267">Balancing loads</span></span>

- <span data-ttu-id="5606e-268">Aggiornamenti in sequenza</span><span class="sxs-lookup"><span data-stu-id="5606e-268">Rolling updates</span></span>

- <span data-ttu-id="5606e-269">Distribuzione di segreti</span><span class="sxs-lookup"><span data-stu-id="5606e-269">Distributing secrets</span></span>

- <span data-ttu-id="5606e-270">Controlli di integrità delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="5606e-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="5606e-271">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5606e-271">Next steps</span></span>

<span data-ttu-id="5606e-272">Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="5606e-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="5606e-273">Procedura dettagliata 6: Distribuire le app basate su contenitori di Windows nel servizio app di Azure per i contenitoriWalkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span><span class="sxs-lookup"><span data-stu-id="5606e-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="5606e-274">Disponibilità della procedura dettagliata tecnica</span><span class="sxs-lookup"><span data-stu-id="5606e-274">Technical walkthrough availability</span></span>

<span data-ttu-id="5606e-275">La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="5606e-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="5606e-276">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5606e-276">Overview</span></span>

<span data-ttu-id="5606e-277">Una semplice applicazione in contenitori che usa i contenitori di Windows può essere facilmente distribuita nel servizio app di Azure per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="5606e-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="5606e-278">Questo è l'approccio consigliato per la maggior parte delle applicazioni basate su contenitori di Windows.This is the recommended approach for most Windows Container-based applications.</span><span class="sxs-lookup"><span data-stu-id="5606e-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="5606e-279">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="5606e-279">Goals</span></span>

<span data-ttu-id="5606e-280">L'obiettivo di questa procedura dettagliata è imparare a distribuire un'applicazione basata su Contenitore di Windows al servizio app di Azure per i contenitori da un Registro di sistema (Docker Hub o Registro contenitori di Azure).</span><span class="sxs-lookup"><span data-stu-id="5606e-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="5606e-281">Scenario</span><span class="sxs-lookup"><span data-stu-id="5606e-281">Scenario</span></span>

![Distribuire l'app basata su contenitori di Windows nel servizio app di Azure per i contenitoriDeploy Windows Container-based app to Azure App Service for Containers](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="5606e-283">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="5606e-283">Benefits</span></span>

<span data-ttu-id="5606e-284">La distribuzione nel servizio app di Azure per i contenitori offre i vantaggi dei contenitori associati ai vantaggi DiAS del servizio app di Azure.Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="5606e-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="5606e-285">Il servizio app può essere facilmente ridimensionato sia verticalmente che orizzontalmente e può essere configurato per la scalabilità automatica per soddisfare le mutevoli esigenze.</span><span class="sxs-lookup"><span data-stu-id="5606e-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="5606e-286">Gli aggiornamenti possono essere eseguiti senza tempi di inattività e la configurazione della distribuzione continua da un Registro di sistema è facilmente configurabile.</span><span class="sxs-lookup"><span data-stu-id="5606e-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5606e-287">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5606e-287">Next steps</span></span>

<span data-ttu-id="5606e-288">Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="5606e-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="5606e-289">[Successivo](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [precedente](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="5606e-289">[Previous](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span> <!-- Next Chapter -->
