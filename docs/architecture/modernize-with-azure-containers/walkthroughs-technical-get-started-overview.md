---
title: Procedure dettagliate e panoramica introduttiva tecnica
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Procedure dettagliate e panoramica introduttiva tecnica
ms.date: 04/28/2018
ms.openlocfilehash: 81f7d9fbf596a23b83e2dc9251788b33a8817e16
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577854"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="10876-103">Procedure dettagliate e panoramica introduttiva tecnica</span><span class="sxs-lookup"><span data-stu-id="10876-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="10876-104">Per limitare le dimensioni di questo e-book, la documentazione tecnica aggiuntiva e le procedure dettagliate complete sono state rese disponibili in un repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="10876-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="10876-105">La serie online di procedure dettagliate descritte in questo capitolo illustra la configurazione dettagliata dei diversi ambienti basati sui contenitori di Windows e la distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="10876-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="10876-106">Le sezioni seguenti illustrano le informazioni su ogni procedura dettagliata, gli obiettivi e la visione di alto livello e forniscono un diagramma delle attività che interessano.</span><span class="sxs-lookup"><span data-stu-id="10876-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="10876-107">È possibile ottenere le procedure dettagliate nel repository <https://github.com/dotnet-architecture/eShopModernizing/wiki>GitHub delle app *eShopModernizing* in.</span><span class="sxs-lookup"><span data-stu-id="10876-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="10876-108">Elenco di procedure tecniche</span><span class="sxs-lookup"><span data-stu-id="10876-108">Technical walkthrough list</span></span>

<span data-ttu-id="10876-109">Le procedure dettagliate introduttive riportate di seguito forniscono indicazioni tecniche coerenti e complete per le app di esempio che è possibile spostare e spostare usando i contenitori e quindi spostarsi usando più opzioni di distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="10876-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="10876-110">Ogni procedura dettagliata seguente usa le nuove app eShopLegacy e eShopModernizing di esempio, disponibili su GitHub all'indirizzo <https://github.com/dotnet-architecture/eShopModernizing>.</span><span class="sxs-lookup"><span data-stu-id="10876-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="10876-111">**Panoramica delle app legacy di eShop (app di base per la modernizzazione)**</span><span class="sxs-lookup"><span data-stu-id="10876-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="10876-112">**Distribuire le app Web ASP.NET esistenti (Web Form & MVC) con i contenitori di Windows**</span><span class="sxs-lookup"><span data-stu-id="10876-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="10876-113">**Distribuire i servizi WCF esistenti (app a più livelli) con i contenitori di Windows**</span><span class="sxs-lookup"><span data-stu-id="10876-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="10876-114">**Distribuire l'app basata su contenitori Windows in macchine virtuali di Azure**</span><span class="sxs-lookup"><span data-stu-id="10876-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="10876-115">**Distribuire le app basate su contenitori Windows in Kubernetes nel servizio contenitore di Azure**</span><span class="sxs-lookup"><span data-stu-id="10876-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="10876-116">Procedura dettagliata 1: Panoramica delle app legacy di eShop</span><span class="sxs-lookup"><span data-stu-id="10876-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="10876-117">Procedura dettagliata relativa alla disponibilità</span><span class="sxs-lookup"><span data-stu-id="10876-117">Technical walkthrough availability</span></span>

<span data-ttu-id="10876-118">La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="10876-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="10876-119">procedure dettagliate del wiki eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="10876-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="10876-120">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10876-120">Overview</span></span>

<span data-ttu-id="10876-121">In questa procedura dettagliata è possibile esplorare l'implementazione iniziale di tre applicazioni legacy di esempio.</span><span class="sxs-lookup"><span data-stu-id="10876-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="10876-122">Le prime due app Web di esempio hanno un'architettura monolitica e sono state create usando ASP.NET classiche.</span><span class="sxs-lookup"><span data-stu-id="10876-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="10876-123">Un'applicazione è basata su ASP.NET 4. x MVC; la seconda applicazione è basata su Web Form ASP.NET 4. x.</span><span class="sxs-lookup"><span data-stu-id="10876-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="10876-124">La terza app è un'app a tre livelli composta da un'app client WinForms e un servizio Windows Communication Foundation lato server [(WCF)](../../framework/wcf/whats-wcf.md) .</span><span class="sxs-lookup"><span data-stu-id="10876-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="10876-125">Tutte queste applicazioni sono disponibili nel [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="10876-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="10876-126">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="10876-126">Goals</span></span>

<span data-ttu-id="10876-127">L'obiettivo principale di questa procedura dettagliata è semplicemente acquisire familiarità con queste app e con il codice e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="10876-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="10876-128">È possibile configurare le app in modo che generino e usino dati fittizi, senza usare il database SQL, a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="10876-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="10876-129">Questa configurazione facoltativa è basata sull'inserimento delle dipendenze, in modo separato.</span><span class="sxs-lookup"><span data-stu-id="10876-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="10876-130">Scenario 1: App Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="10876-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="10876-131">La figura seguente illustra lo scenario semplice delle applicazioni Web ASP.NET legacy originali.</span><span class="sxs-lookup"><span data-stu-id="10876-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Scenario di architettura semplice delle applicazioni Web ASP.NET legacy originali](./media/image5-1.png)

<span data-ttu-id="10876-133">Dal punto di vista del dominio aziendale, entrambe le app offrono le stesse funzionalità di gestione del catalogo.</span><span class="sxs-lookup"><span data-stu-id="10876-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="10876-134">I membri del team di eShop Enterprise useranno l'app per visualizzare e modificare il catalogo prodotti.</span><span class="sxs-lookup"><span data-stu-id="10876-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="10876-135">Nella figura seguente sono illustrate le schermate iniziali dell'app.</span><span class="sxs-lookup"><span data-stu-id="10876-135">The next figure shows the initial app screenshots.</span></span>

![Applicazioni Web Form ASP.NET MVC e ASP.NET (tecnologie esistenti/legacy)](./media/image5-2.png)

<span data-ttu-id="10876-137">Le dipendenze in ASP.NET 4. x o versioni precedenti (per MVC o per Web Form) indicano che queste applicazioni non vengono eseguite in .NET Core, a meno che il codice non venga completamente riscritto usando ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="10876-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="10876-138">Scenario 2: Servizio WCF e app client WinForms (app a 3 livelli)</span><span class="sxs-lookup"><span data-stu-id="10876-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="10876-139">La figura seguente illustra lo scenario semplice dell'applicazione legacy a 3 livelli originale.</span><span class="sxs-lookup"><span data-stu-id="10876-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Scenario di architettura semplice dell'app a 3 livelli originale legacy con un servizio WCF e un'app client WinForms](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="10876-141">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="10876-141">Benefits</span></span>

<span data-ttu-id="10876-142">I vantaggi di questa procedura dettagliata sono semplici: Basta acquisire familiarità con il codice e le app iniziali.</span><span class="sxs-lookup"><span data-stu-id="10876-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="10876-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="10876-143">Next steps</span></span>

<span data-ttu-id="10876-144">Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="10876-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="10876-145">Panoramica sulle app ASP.NET MVC e Web Forms "Legacy" di base</span><span class="sxs-lookup"><span data-stu-id="10876-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="10876-146">Presentazione del servizio WCF di base e dell'app Windows Forms (a 3 livelli) "Legacy"</span><span class="sxs-lookup"><span data-stu-id="10876-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="10876-147">Procedura dettagliata 2: Distribuire le applicazioni .NET esistenti con i contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="10876-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="10876-148">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10876-148">Overview</span></span>

<span data-ttu-id="10876-149">Usare i contenitori di Windows per migliorare la distribuzione di applicazioni .NET esistenti, come quelle basate su MVC, Web Form o WCF, in ambienti di produzione, sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="10876-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="10876-150">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="10876-150">Goals</span></span>

<span data-ttu-id="10876-151">L'obiettivo di questa procedura dettagliata è mostrare diverse opzioni per inserimento un'applicazione .NET Framework esistente.</span><span class="sxs-lookup"><span data-stu-id="10876-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="10876-152">È possibile:</span><span class="sxs-lookup"><span data-stu-id="10876-152">You can:</span></span>

- <span data-ttu-id="10876-153">Distribuire l'applicazione con [Visual studio 2017 Tools per Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (visual studio 2017 o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="10876-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="10876-154">Distribuire l'applicazione aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)e quindi usando l' [interfaccia](https://docs.docker.com/engine/reference/commandline/cli/)della riga di comando di Docker.</span><span class="sxs-lookup"><span data-stu-id="10876-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="10876-155">Distribuire l'applicazione usando lo strumento [Img2Docker](https://github.com/docker/communitytools-image2docker-win) (uno strumento open source di Docker).</span><span class="sxs-lookup"><span data-stu-id="10876-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="10876-156">Questa procedura dettagliata è incentrata sull'approccio di Visual Studio 2017 Tools per Docker, ma gli altri due approcci sono piuttosto simili per quanto riguarda l'uso di Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="10876-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="10876-157">Scenario 1: App Web ASP.NET in contenitori</span><span class="sxs-lookup"><span data-stu-id="10876-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="10876-158">La figura seguente illustra lo scenario per le applicazioni di app Web legacy del eShop in contenitori.</span><span class="sxs-lookup"><span data-stu-id="10876-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Diagramma dell'architettura semplificato di applicazioni ASP.NET in contenitori in un ambiente di sviluppo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="10876-160">Scenario 2: Servizio WCF in contenitori</span><span class="sxs-lookup"><span data-stu-id="10876-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="10876-161">La figura seguente illustra lo scenario per un'applicazione a 3 livelli con un servizio WCF in contenitori.</span><span class="sxs-lookup"><span data-stu-id="10876-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Diagramma dell'architettura semplificato del servizio WCF in contenitori in un ambiente di sviluppo](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="10876-163">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="10876-163">Benefits</span></span>

<span data-ttu-id="10876-164">L'esecuzione di un'applicazione monolitica in un contenitore presenta alcuni vantaggi.</span><span class="sxs-lookup"><span data-stu-id="10876-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="10876-165">Prima di tutto, creare un'immagine per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="10876-165">First, you create an image for the application.</span></span> <span data-ttu-id="10876-166">Da quel momento in poi, ogni distribuzione viene eseguita nello stesso ambiente.</span><span class="sxs-lookup"><span data-stu-id="10876-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="10876-167">Ogni contenitore usa la stessa versione del sistema operativo, è installata la stessa versione delle dipendenze, usa la stessa versione di .NET Framework e viene compilata utilizzando lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="10876-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="10876-168">In pratica, è possibile controllare le dipendenze dell'applicazione usando un'immagine docker.</span><span class="sxs-lookup"><span data-stu-id="10876-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="10876-169">Le dipendenze viaggiano con l'applicazione quando si distribuiscono i contenitori.</span><span class="sxs-lookup"><span data-stu-id="10876-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="10876-170">Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente coerente fornito dai contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="10876-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="10876-171">I problemi che si verificano solo con determinate versioni possono essere individuati immediatamente, anziché essere visualizzati in un ambiente di gestione temporanea o di produzione.</span><span class="sxs-lookup"><span data-stu-id="10876-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="10876-172">Le differenze negli ambienti di sviluppo usati dai membri del team di sviluppo sono meno importanti quando le applicazioni vengono eseguite nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="10876-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="10876-173">Le applicazioni incluse in contenitori hanno anche una curva con scalabilità orizzontale più piatta.</span><span class="sxs-lookup"><span data-stu-id="10876-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="10876-174">Le app in contenitori consentono di avere più istanze di applicazioni e servizi (basate sui contenitori) in una macchina virtuale o in un computer fisico rispetto alle distribuzioni di applicazioni normali per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="10876-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="10876-175">Questo si traduce in una maggiore densità e meno risorse necessarie, soprattutto quando si usano agenti di orchestrazione come Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="10876-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="10876-176">La creazione di contenitori, in situazioni ideali, non richiede alcuna modifica al codice dell'applicazione (C\#).</span><span class="sxs-lookup"><span data-stu-id="10876-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="10876-177">Nella maggior parte degli scenari sono necessari solo i file di metadati di distribuzione Docker (Dockerfile e file di Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="10876-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="10876-178">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="10876-178">Next steps</span></span>

<span data-ttu-id="10876-179">Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="10876-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="10876-180">Come distribuire le app Web di .NET Framework con i contenitori di Windows e Docker</span><span class="sxs-lookup"><span data-stu-id="10876-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="10876-181">Aggiunta del supporto Docker a un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="10876-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="10876-182">Procedura dettagliata 3: Distribuire l'app basata su contenitori Windows in macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="10876-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="10876-183">Procedura dettagliata relativa alla disponibilità</span><span class="sxs-lookup"><span data-stu-id="10876-183">Technical walkthrough availability</span></span>

<span data-ttu-id="10876-184">La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="10876-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="10876-185">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10876-185">Overview</span></span>

<span data-ttu-id="10876-186">La distribuzione in un host Docker in una macchina virtuale Windows Server 2016 (VM) in Azure consente di configurare rapidamente ambienti di sviluppo/test/gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="10876-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="10876-187">Fornisce inoltre un posto comune a tester o utenti aziendali per convalidare l'app.</span><span class="sxs-lookup"><span data-stu-id="10876-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="10876-188">Le macchine virtuali possono anche essere ambienti di produzione di infrastruttura distribuita come servizio (IaaS) validi.</span><span class="sxs-lookup"><span data-stu-id="10876-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="10876-189">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="10876-189">Goals</span></span>

<span data-ttu-id="10876-190">L'obiettivo di questa procedura dettagliata è mostrare le diverse alternative disponibili quando si distribuiscono i contenitori di Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="10876-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="10876-191">Scenari</span><span class="sxs-lookup"><span data-stu-id="10876-191">Scenarios</span></span>

<span data-ttu-id="10876-192">In questa procedura dettagliata sono descritti diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="10876-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="10876-193">Scenario A: Eseguire la distribuzione in una macchina virtuale di Azure da un computer di sviluppo tramite la connessione al motore Docker</span><span class="sxs-lookup"><span data-stu-id="10876-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Eseguire la distribuzione in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker](./media/image5-4.png)

<span data-ttu-id="10876-195">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="10876-195">**Figure 5-4.**</span></span> <span data-ttu-id="10876-196">Eseguire la distribuzione in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker</span><span class="sxs-lookup"><span data-stu-id="10876-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="10876-197">Scenario B: Eseguire la distribuzione in una macchina virtuale di Azure tramite un registro Docker</span><span class="sxs-lookup"><span data-stu-id="10876-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Eseguire la distribuzione in una macchina virtuale di Azure tramite un registro Docker](./media/image5-5.png)

<span data-ttu-id="10876-199">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="10876-199">**Figure 5-5.**</span></span> <span data-ttu-id="10876-200">Eseguire la distribuzione in una macchina virtuale di Azure tramite un registro Docker</span><span class="sxs-lookup"><span data-stu-id="10876-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="10876-201">Scenario C: Eseguire la distribuzione in una macchina virtuale di Azure da pipeline CI/CD in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="10876-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Eseguire la distribuzione in una macchina virtuale di Azure da pipeline CI/CD in Azure DevOps Services](./media/image5-6.png)

<span data-ttu-id="10876-203">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="10876-203">**Figure 5-6.**</span></span> <span data-ttu-id="10876-204">Eseguire la distribuzione in una macchina virtuale di Azure da pipeline CI/CD in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="10876-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="10876-205">VM di Azure per i contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="10876-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="10876-206">Le macchine virtuali di Azure per i contenitori di Windows sono macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambe con il motore Docker configurato.</span><span class="sxs-lookup"><span data-stu-id="10876-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="10876-207">Nella maggior parte dei casi, Windows Server 2016 viene usato nelle VM di Azure.</span><span class="sxs-lookup"><span data-stu-id="10876-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="10876-208">Azure fornisce attualmente una macchina virtuale denominata **Windows Server 2016 con i contenitori**.</span><span class="sxs-lookup"><span data-stu-id="10876-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="10876-209">È possibile usare questa macchina virtuale per provare la nuova funzionalità contenitore di Windows Server, con Windows Server Core o Windows nano server.</span><span class="sxs-lookup"><span data-stu-id="10876-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="10876-210">Le immagini del sistema operativo del contenitore sono installate, quindi la macchina virtuale è pronta per l'uso con Docker.</span><span class="sxs-lookup"><span data-stu-id="10876-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="10876-211">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="10876-211">Benefits</span></span>

<span data-ttu-id="10876-212">Sebbene i contenitori di Windows possano essere distribuiti in macchine virtuali Windows Server 2016 locali, quando si esegue la distribuzione in Azure, si ottiene un modo più semplice per iniziare, con macchine virtuali contenitore Windows Server pronte all'uso.</span><span class="sxs-lookup"><span data-stu-id="10876-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="10876-213">Si ottiene anche un percorso online comune accessibile ai tester e la scalabilità automatica tramite i set di scalabilità di macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="10876-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="10876-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="10876-214">Next steps</span></span>

<span data-ttu-id="10876-215">Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="10876-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="10876-216">Procedura dettagliata 4: Distribuire le app basate su contenitori Windows in istanze di contenitore di Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="10876-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="10876-217">Procedura dettagliata relativa alla disponibilità</span><span class="sxs-lookup"><span data-stu-id="10876-217">Technical walkthrough availability</span></span>

<span data-ttu-id="10876-218">La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="10876-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="10876-219">[Distribuzione delle app in ACI (istanze di contenitore di Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="10876-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="10876-220">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10876-220">Overview</span></span>

<span data-ttu-id="10876-221">[Istanze di contenitore di Azure](https://docs.microsoft.com/azure/container-instances/) è il modo più rapido per avere un ambiente di sviluppo/test/gestione temporanea di contenitori in cui è possibile distribuire singole istanze di contenitori.</span><span class="sxs-lookup"><span data-stu-id="10876-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="10876-222">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="10876-222">Goals</span></span>

<span data-ttu-id="10876-223">Questa procedura dettagliata illustra gli scenari principali per la distribuzione di contenitori di Windows in istanze di contenitore di Azure (ACI) e come è possibile distribuire app eShopModernizing in ACI.</span><span class="sxs-lookup"><span data-stu-id="10876-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="10876-224">Scenari</span><span class="sxs-lookup"><span data-stu-id="10876-224">Scenarios</span></span>

<span data-ttu-id="10876-225">È possibile che si verifichino variazioni di distribuzione delle app eShopModernizing in ACI, ad esempio la distribuzione di una o tutte le app (app MVC, app Web Form o servizio WCF).</span><span class="sxs-lookup"><span data-stu-id="10876-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="10876-226">Nel seguente scenario illustrato di seguito è possibile visualizzare l'app MVC ASP.NET più il contenitore SQL Server entrambi distribuiti come contenitori in ACI (istanze di contenitore di Azure).</span><span class="sxs-lookup"><span data-stu-id="10876-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Eseguire la distribuzione in ACI da un ambiente di sviluppo](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="10876-228">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="10876-228">Benefits</span></span>

<span data-ttu-id="10876-229">Istanze di contenitore di Azure semplifica la creazione e la gestione di contenitori Docker in Azure, senza dover eseguire il provisioning di macchine virtuali o adottare un servizio di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="10876-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="10876-230">Con ACI è possibile distribuire direttamente un contenitore Windows in Azure ed esporlo a Internet con un nome di dominio completo (FQDN) in pochi secondi (a condizione che l'immagine del contenitore di Windows sia pronta in un registro Docker, ad esempio l'hub Docker o il contenitore di Azure). Registro di sistema).</span><span class="sxs-lookup"><span data-stu-id="10876-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="10876-231">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="10876-231">Considerations</span></span>

<span data-ttu-id="10876-232">La distribuzione di contenitori di Windows con .NET Framework completo/ASP.NET o SQL Server in istanze di contenitore di Azure non è molto veloce quanto la distribuzione in un normale host Docker, ad esempio Windows Server 2016 con contenitori Windows, perché l'immagine Docker deve essere scaricati (estratti dal registro Docker) ogni volta e le dimensioni dell'immagine del contenitore SQL (15,1 GB) e dell'immagine del contenitore ASP.NET (13,9 GB) sono molto grandi, ma è molto più economico rispetto alla gestione del proprio host Docker (in modo permanente in linea Windows Server 2016 con la macchina virtuale contenitori Windows in Azure) non menzionare un intero agente di orchestrazione come Kubernetes in Azure (AKS), che è d'altra parte una scelta ottimale per le distribuzioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="10876-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="10876-233">Come conclusione principale, l'uso di istanze di contenitore di Azure è un'opzione molto interessante per gli scenari di sviluppo e test e per le pipeline CI/CD.</span><span class="sxs-lookup"><span data-stu-id="10876-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10876-234">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="10876-234">Next steps</span></span>

<span data-ttu-id="10876-235">Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="10876-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="10876-236">Procedura dettagliata 5: Distribuire le app basate su contenitori Windows in Kubernetes nel servizio contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="10876-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="10876-237">Procedura dettagliata relativa alla disponibilità</span><span class="sxs-lookup"><span data-stu-id="10876-237">Technical walkthrough availability</span></span>

<span data-ttu-id="10876-238">La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="10876-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="10876-239">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10876-239">Overview</span></span>

<span data-ttu-id="10876-240">Un'applicazione basata su contenitori di Windows dovrà usare rapidamente le piattaforme, allontanandosi ancora più dalle macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="10876-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="10876-241">Questa operazione è necessaria per ottenere facilmente scalabilità elevata e una migliore scalabilità automatica e per un miglioramento significativo delle distribuzioni e del controllo delle versioni automatizzate.</span><span class="sxs-lookup"><span data-stu-id="10876-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="10876-242">Per raggiungere questi obiettivi, è possibile usare l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile nei [Servizi contenitore di Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="10876-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="10876-243">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="10876-243">Goals</span></span>

<span data-ttu-id="10876-244">L'obiettivo di questa procedura dettagliata consiste nell'apprendere come distribuire un'applicazione basata su contenitore Windows in Kubernetes (anche denominata *K8s*) nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="10876-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="10876-245">La distribuzione in Kubernetes da zero è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="10876-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="10876-246">Distribuire un cluster Kubernetes nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="10876-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="10876-247">Distribuire l'applicazione e le risorse correlate al cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="10876-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="10876-248">Scenari</span><span class="sxs-lookup"><span data-stu-id="10876-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="10876-249">Scenario A: Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="10876-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo](./media/image5-7.png)

<span data-ttu-id="10876-251">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="10876-251">**Figure 5-7.**</span></span> <span data-ttu-id="10876-252">Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="10876-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="10876-253">Scenario B: Eseguire la distribuzione in un cluster Kubernetes da pipeline CI/CD in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="10876-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Eseguire la distribuzione in un cluster Kubernetes da pipeline CI/CD in Azure DevOps Services](./media/image5-8.png)

<span data-ttu-id="10876-255">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="10876-255">**Figure 5-8.**</span></span> <span data-ttu-id="10876-256">Eseguire la distribuzione in un cluster Kubernetes da pipeline CI/CD in Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="10876-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="10876-257">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="10876-257">Benefits</span></span>

<span data-ttu-id="10876-258">La distribuzione in un cluster in Kubernetes presenta numerosi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="10876-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="10876-259">Il vantaggio principale è che si ottiene un ambiente di produzione in cui è possibile scalare verticalmente l'applicazione in base al numero di istanze di contenitore che si vuole usare (scalabilità interna nei nodi esistenti) e in base al numero di nodi o macchine virtuali nel cluster ( scalabilità globale del cluster.</span><span class="sxs-lookup"><span data-stu-id="10876-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="10876-260">Il servizio contenitore di Azure ottimizza le tecnologie e gli strumenti open source più diffusi in modo specifico per Azure.</span><span class="sxs-lookup"><span data-stu-id="10876-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="10876-261">Si ottiene una soluzione aperta che offre la portabilità, sia per i contenitori che per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="10876-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="10876-262">Si selezionano le dimensioni, il numero di host e gli strumenti di orchestrazione-il servizio contenitore gestisce tutto il resto.</span><span class="sxs-lookup"><span data-stu-id="10876-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="10876-263">Con Kubernetes, gli sviluppatori possono progredire dalla riflessione su macchine fisiche e virtuali, alla pianificazione di un'infrastruttura incentrata sul contenitore che facilita le funzionalità seguenti, tra le altre:</span><span class="sxs-lookup"><span data-stu-id="10876-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="10876-264">Applicazioni basate su più contenitori</span><span class="sxs-lookup"><span data-stu-id="10876-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="10876-265">Replica di istanze di contenitore e scalabilità automatica orizzontale</span><span class="sxs-lookup"><span data-stu-id="10876-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="10876-266">Denominazione e individuazione (ad esempio, DNS interno)</span><span class="sxs-lookup"><span data-stu-id="10876-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="10876-267">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="10876-267">Balancing loads</span></span>

- <span data-ttu-id="10876-268">Aggiornamenti in sequenza</span><span class="sxs-lookup"><span data-stu-id="10876-268">Rolling updates</span></span>

- <span data-ttu-id="10876-269">Distribuzione dei segreti</span><span class="sxs-lookup"><span data-stu-id="10876-269">Distributing secrets</span></span>

- <span data-ttu-id="10876-270">Controlli di integrità dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="10876-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="10876-271">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="10876-271">Next steps</span></span>

<span data-ttu-id="10876-272">Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="10876-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="10876-273">Procedura dettagliata 6: Distribuire le app basate su contenitori di Windows nel servizio app Azure per i contenitori</span><span class="sxs-lookup"><span data-stu-id="10876-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="10876-274">Procedura dettagliata relativa alla disponibilità</span><span class="sxs-lookup"><span data-stu-id="10876-274">Technical walkthrough availability</span></span>

<span data-ttu-id="10876-275">La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="10876-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="10876-276">Panoramica</span><span class="sxs-lookup"><span data-stu-id="10876-276">Overview</span></span>

<span data-ttu-id="10876-277">Una semplice applicazione in contenitori con i contenitori di Windows può essere facilmente distribuita al servizio app Azure per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="10876-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="10876-278">Si tratta dell'approccio consigliato per la maggior parte delle applicazioni basate su contenitore Windows.</span><span class="sxs-lookup"><span data-stu-id="10876-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="10876-279">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="10876-279">Goals</span></span>

<span data-ttu-id="10876-280">L'obiettivo di questa procedura dettagliata consiste nell'apprendere come distribuire un'applicazione basata su contenitore Windows per app Azure servizio per i contenitori da un registro (hub Docker o Azure Container Registry).</span><span class="sxs-lookup"><span data-stu-id="10876-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="10876-281">Scenario</span><span class="sxs-lookup"><span data-stu-id="10876-281">Scenario</span></span>

![Distribuire un'app basata su contenitori Windows nel servizio app Azure per i contenitori](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="10876-283">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="10876-283">Benefits</span></span>

<span data-ttu-id="10876-284">La distribuzione nel servizio app Azure per i contenitori offre i vantaggi dei contenitori abbinati ai vantaggi PaaS di app Azure servizio.</span><span class="sxs-lookup"><span data-stu-id="10876-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="10876-285">Il servizio app può essere facilmente ridimensionato verticalmente e orizzontalmente e può essere configurato per la scalabilità automatica per soddisfare le esigenze mutevoli.</span><span class="sxs-lookup"><span data-stu-id="10876-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="10876-286">Gli aggiornamenti possono essere eseguiti senza tempi di inattività e la configurazione della distribuzione continua da un registro di sistema è facilmente configurabile.</span><span class="sxs-lookup"><span data-stu-id="10876-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10876-287">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="10876-287">Next steps</span></span>

<span data-ttu-id="10876-288">Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="10876-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="10876-289">[Precedente](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Successivo](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="10876-289">[Previous](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
