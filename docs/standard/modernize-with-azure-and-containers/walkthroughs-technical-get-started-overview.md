---
title: Procedure dettagliate e panoramica introduttiva tecnica
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows | Procedure dettagliate e technical panoramica introduttiva
ms.date: 04/28/2018
ms.openlocfilehash: 1ae6f3c1e739184356b97fa96e74bab402bf1d2a
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832963"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="cf1b9-103">Procedure dettagliate e panoramica introduttiva tecnica</span><span class="sxs-lookup"><span data-stu-id="cf1b9-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="cf1b9-104">Per limitare le dimensioni di questo e-book, documentazione tecnica aggiuntiva e le procedure dettagliate complete sono stati resi disponibili in un repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="cf1b9-105">La linea serie di procedure dettagliate che sono descritti in questo capitolo descrive la configurazione dettagliata di più ambienti basati su contenitori di Windows e la distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="cf1b9-106">Le sezioni seguenti illustrano ciò che ogni procedura dettagliata sui suoi obiettivi e una visione generale e fornisce un diagramma di attività che sono coinvolti.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="cf1b9-107">È possibile ottenere le procedure dettagliate autonomamente nel *eShopModernizing* wiki repository GitHub di App a <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="cf1b9-108">Elenco delle procedure dettagliate tecniche</span><span class="sxs-lookup"><span data-stu-id="cf1b9-108">Technical walkthrough list</span></span>

<span data-ttu-id="cf1b9-109">Procedure dettagliate di introduzione seguenti forniscono indicazioni tecniche completa e coerente per le app di esempio che è possibile sollevare e spostare usando i contenitori e reinserirvi usando più opzioni di distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="cf1b9-110">Ognuna delle procedure dettagliate seguenti utilizza il nuovo esempio eShopLegacy eShopModernizing le App e quali sono disponibili in GitHub all'indirizzo <https://github.com/dotnet-architecture/eShopModernizing>.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="cf1b9-111">**Panoramica delle App legacy eShop (app linea di base per modernizzare)**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="cf1b9-112">**Distribuire le app web ASP.NET esistenti (Web Form e MVC) in un contenitore con contenitori Windows**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="cf1b9-113">**Distribuire i servizi WCF esistenti (App a più livelli) con i contenitori Windows in un contenitore**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="cf1b9-114">**Distribuire l'app basata su contenitori Windows in macchine virtuali di Azure**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="cf1b9-115">**Distribuire le app di Windows basata su contenitori in Kubernetes nel servizio contenitore di Azure**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="cf1b9-116">Procedura dettagliata 1: Panoramica delle App legacy eShop</span><span class="sxs-lookup"><span data-stu-id="cf1b9-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="cf1b9-117">Istruzioni dettagliate su disponibilità</span><span class="sxs-lookup"><span data-stu-id="cf1b9-117">Technical walkthrough availability</span></span>

<span data-ttu-id="cf1b9-118">La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="cf1b9-119">procedure wiki dettagliate eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="cf1b9-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="cf1b9-120">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cf1b9-120">Overview</span></span>

<span data-ttu-id="cf1b9-121">In questa procedura dettagliata, è possibile esplorare l'implementazione iniziale di tre applicazioni legacy di esempio.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="cf1b9-122">Le prime due App web di esempio dispone di un'architettura monolitica e sono state create utilizzando ASP.NET classico.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="cf1b9-123">Un'applicazione si basa su ASP.NET 4.x MVC; la seconda applicazione si basa su Web Form ASP.NET 4.x.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="cf1b9-124">Il terzo app è un'app a 3 livelli composta da un lato server e un'app client di Windows Form [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) servizio.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="cf1b9-125">Sono disponibili in tutte le applicazioni di [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="cf1b9-126">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-126">Goals</span></span>

<span data-ttu-id="cf1b9-127">L'obiettivo principale di questa procedura dettagliata è semplicemente per acquisire familiarità con queste App e con il codice e configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="cf1b9-128">È possibile configurare le App in modo che possano generare e usare dati fittizi, senza usare il database SQL, a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="cf1b9-129">Questa configurazione facoltativa si basa sull'inserimento delle dipendenze, in modo disgiunto.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="cf1b9-130">Scenario 1: App Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cf1b9-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="cf1b9-131">La figura seguente illustra uno scenario semplice delle applicazioni web ASP.NET legacy originale.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Scenario semplice architettura delle applicazioni web originale legacy ASP.NET](./media/image5-1.png)

<span data-ttu-id="cf1b9-133">Dalla prospettiva del dominio aziendale, entrambe le app offrono lo stesso catalogo le funzionalità di gestione.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="cf1b9-134">I membri del team di enterprise eShop utilizzerebbe l'app per visualizzare e modificare il catalogo dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="cf1b9-135">La figura seguente mostra le schermate iniziale dell'app.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-135">The next figure shows the initial app screenshots.</span></span>

![Applicazioni MVC ASP.NET e Web Form ASP.NET (le tecnologie esistenti/legacy)](./media/image5-2.png)

<span data-ttu-id="cf1b9-137">Le dipendenze in ASP.NET 4.x o versioni precedenti (per MVC o Web Form) significa che queste applicazioni non verranno eseguito in .NET Core, a meno che il codice è completamente riscritto usando ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="cf1b9-138">Scenario 2: Client di Windows Forms app (app di livello 3) e un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="cf1b9-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="cf1b9-139">La figura seguente illustra uno scenario semplice dell'applicazione legacy a 3 livelli originale.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Scenario semplice architettura di app legacy originale a 3 livelli con un servizio WCF e un'app client di Windows Form](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="cf1b9-141">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-141">Benefits</span></span>

<span data-ttu-id="cf1b9-142">I vantaggi di questa procedura dettagliata sono semplici: Semplicemente acquisire familiarità con le app iniziale e il codice.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="cf1b9-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-143">Next steps</span></span>

<span data-ttu-id="cf1b9-144">Esplorare il contenuto più approfondito su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="cf1b9-145">Panoramica sulla linea di base ASP.NET MVC e le app "legacy" Web Form</span><span class="sxs-lookup"><span data-stu-id="cf1b9-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="cf1b9-146">Panoramica sul servizio WCF di base e l'app "legacy" (livello 3) di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cf1b9-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="cf1b9-147">Procedura dettagliata 2: Distribuire le applicazioni .NET esistenti con contenitori Windows in un contenitore</span><span class="sxs-lookup"><span data-stu-id="cf1b9-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="cf1b9-148">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cf1b9-148">Overview</span></span>

<span data-ttu-id="cf1b9-149">Usare i contenitori di Windows per migliorare la distribuzione delle applicazioni .NET esistenti, ad esempio quelle basate su Web Form, MVC o WCF, produzione, sviluppo e ambienti di test.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="cf1b9-150">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-150">Goals</span></span>

<span data-ttu-id="cf1b9-151">L'obiettivo di questa procedura dettagliata è descrive diverse opzioni per l'inserimento di un'applicazione esistente di .NET Framework nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="cf1b9-152">È possibile:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-152">You can:</span></span>

- <span data-ttu-id="cf1b9-153">Distribuire l'applicazione in un contenitore usando [Visual Studio 2017 Tools per Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="cf1b9-154">Distribuire in un contenitore dell'applicazione aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)e quindi usando la [CLI di Docker](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="cf1b9-155">Distribuire l'applicazione in un contenitore usando il [Img2Docker](https://github.com/docker/communitytools-image2docker-win) strumento (uno strumento open source da Docker).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="cf1b9-156">Questa procedura dettagliata si basa su Visual Studio 2017 Tools per l'approccio di Docker, ma gli altri due approcci sono abbastanza simili dal punto di vista usando i Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="cf1b9-157">Scenario 1: App web ASP.NET nei contenitori</span><span class="sxs-lookup"><span data-stu-id="cf1b9-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="cf1b9-158">Nella figura seguente illustra lo scenario per applicazioni web legacy eShop nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Diagramma dell'architettura semplificata in contenitori le applicazioni ASP.NET in un ambiente di sviluppo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="cf1b9-160">Scenario 2: Servizio WCF in contenitori</span><span class="sxs-lookup"><span data-stu-id="cf1b9-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="cf1b9-161">Nella figura seguente illustra lo scenario per un'app a 3 livelli con un servizio WCF in contenitori.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Diagramma dell'architettura del servizio WCF in contenitori in un ambiente di sviluppo semplificato](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="cf1b9-163">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-163">Benefits</span></span>

<span data-ttu-id="cf1b9-164">Esistono vantaggi rispetto all'esecuzione dell'applicazione monolitica in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="cf1b9-165">In primo luogo, viene creata un'immagine per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-165">First, you create an image for the application.</span></span> <span data-ttu-id="cf1b9-166">Da quel momento, ogni distribuzione viene eseguito nello stesso ambiente.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="cf1b9-167">Ogni contenitore Usa la stessa versione del sistema operativo, ha la stessa versione di dipendenze installata, Usa la stessa versione di .NET framework e viene compilato con lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="cf1b9-168">In pratica, si controllano le dipendenze dell'applicazione usando un'immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="cf1b9-169">Le dipendenze di pari passo con l'applicazione quando si distribuisce i contenitori.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="cf1b9-170">Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente coerente che viene fornito dai contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="cf1b9-171">I problemi che vengono visualizzati solo con determinate versioni possono essere rilevati immediatamente, anziché emergere in un ambiente di gestione temporanea o produzione.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="cf1b9-172">Differenze in ambienti di sviluppo usati dai membri del team di sviluppo sono meno rilevanti quando le applicazioni eseguite nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="cf1b9-173">Le applicazioni in contenitori hanno anche una curva di scalabilità orizzontale flatter.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="cf1b9-174">Le App in contenitori consentono di avere più applicazioni e istanze del servizio (basate su contenitori) in una macchina virtuale o fisica rispetto alle distribuzioni di applicazioni normali per ogni macchina.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="cf1b9-175">Questo si traduce in maggiore densità e meno necessarie risorse, soprattutto quando si usano gli agenti di orchestrazione come Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="cf1b9-176">Utilizzo dei contenitori, in situazioni ideali non è necessario apportare modifiche al codice dell'applicazione (C\#).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="cf1b9-177">Nella maggior parte degli scenari, è necessario solo i file di metadati di distribuzione di Docker (file Dockerfile e Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="cf1b9-178">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-178">Next steps</span></span>

<span data-ttu-id="cf1b9-179">Esplorare il contenuto più approfondito su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="cf1b9-180">Come distribuire le app web di .NET Framework con i contenitori Windows e Docker in un contenitore</span><span class="sxs-lookup"><span data-stu-id="cf1b9-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="cf1b9-181">Aggiunta del supporto Docker a un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="cf1b9-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="cf1b9-182">Procedura dettagliata 3: Distribuire l'app basata su contenitori Windows in macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="cf1b9-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="cf1b9-183">Istruzioni dettagliate su disponibilità</span><span class="sxs-lookup"><span data-stu-id="cf1b9-183">Technical walkthrough availability</span></span>

<span data-ttu-id="cf1b9-184">La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="cf1b9-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="cf1b9-185">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cf1b9-185">Overview</span></span>

<span data-ttu-id="cf1b9-186">Distribuzione in un host Docker in un Windows Server 2016 Virtual Machine (VM) in Azure consente di configurare rapidamente gli ambienti di sviluppo/test/staging.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="cf1b9-187">Offre inoltre una posizione frequente per i tester o utenti di business convalidare l'app.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="cf1b9-188">Le macchine virtuali possono rivelarsi infrastruttura valido come ambienti di produzione un servizio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="cf1b9-189">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-189">Goals</span></span>

<span data-ttu-id="cf1b9-190">L'obiettivo di questa procedura dettagliata è descrive le alternative più, che è necessario quando si distribuisce i contenitori Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="cf1b9-191">Scenari</span><span class="sxs-lookup"><span data-stu-id="cf1b9-191">Scenarios</span></span>

<span data-ttu-id="cf1b9-192">In questa procedura dettagliata vengono illustrati gli scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="cf1b9-193">Scenario a: Distribuire in una VM di Azure da un PC di sviluppo tramite connessione al motore di Docker</span><span class="sxs-lookup"><span data-stu-id="cf1b9-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Distribuire in una VM di Azure da un computer di sviluppo tramite una connessione al motore di Docker](./media/image5-4.png)

<span data-ttu-id="cf1b9-195">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-195">**Figure 5-4.**</span></span> <span data-ttu-id="cf1b9-196">Distribuire in una VM di Azure da un computer di sviluppo tramite una connessione al motore di Docker</span><span class="sxs-lookup"><span data-stu-id="cf1b9-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="cf1b9-197">Scenario b: Distribuire una macchina virtuale di Azure tramite un registro Docker</span><span class="sxs-lookup"><span data-stu-id="cf1b9-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Distribuire una macchina virtuale di Azure tramite un registro Docker](./media/image5-5.png)

<span data-ttu-id="cf1b9-199">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-199">**Figure 5-5.**</span></span> <span data-ttu-id="cf1b9-200">Distribuire una macchina virtuale di Azure tramite un registro Docker</span><span class="sxs-lookup"><span data-stu-id="cf1b9-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="cf1b9-201">Scenario di c: Distribuire in una VM di Azure dalla pipeline CI/CD in servizi di Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="cf1b9-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Distribuire in una VM di Azure dalla pipeline CI/CD in servizi di Azure DevOps](./media/image5-6.png)

<span data-ttu-id="cf1b9-203">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-203">**Figure 5-6.**</span></span> <span data-ttu-id="cf1b9-204">Distribuire in una VM di Azure dalla pipeline CI/CD in servizi di Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="cf1b9-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="cf1b9-205">Macchine virtuali di Azure per contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="cf1b9-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="cf1b9-206">Macchine virtuali di Azure per contenitori Windows sono macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambi con il motore Docker configurare.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="cf1b9-207">Nella maggior parte dei casi, viene usato Windows Server 2016 in macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="cf1b9-208">Attualmente, Azure offre una macchina virtuale denominata **Windows Server 2016 with Containers**.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="cf1b9-209">È possibile usare questa macchina virtuale per provare la nuova funzionalità di contenitore di Windows Server con Windows Server Core o Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="cf1b9-210">Le immagini del sistema operativo del contenitore vengono installate, e quindi la macchina virtuale è pronta per l'uso con Docker.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="cf1b9-211">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-211">Benefits</span></span>

<span data-ttu-id="cf1b9-212">Sebbene i contenitori di Windows possono essere distribuiti in macchine virtuali in locale Windows Server 2016, quando si distribuiscono in Azure, si ottiene un modo più semplice per iniziare, con macchine virtuali di contenitore pronto da usare Windows Server.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="cf1b9-213">È anche possibile ottenere una posizione online comune che è accessibile ai tester e la scalabilità automatica tramite set di scalabilità di macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="cf1b9-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-214">Next steps</span></span>

<span data-ttu-id="cf1b9-215">Esplorare il contenuto più approfondito su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="cf1b9-216">Procedura dettagliata 4: Distribuire le app di Windows basata su contenitori in istanze di contenitore di Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="cf1b9-217">Istruzioni dettagliate su disponibilità</span><span class="sxs-lookup"><span data-stu-id="cf1b9-217">Technical walkthrough availability</span></span>

<span data-ttu-id="cf1b9-218">La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="cf1b9-219">[La distribuzione dell'App a ACI (istanze di contenitore di Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="cf1b9-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="cf1b9-220">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cf1b9-220">Overview</span></span>

<span data-ttu-id="cf1b9-221">[Le istanze di contenitore di Azure (ACI)](https://docs.microsoft.com/azure/container-instances/) è il modo più rapido per disporre di un ambiente di sviluppo/test/staging contenitori in cui è possibile distribuire singole istanze di contenitori.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="cf1b9-222">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-222">Goals</span></span>

<span data-ttu-id="cf1b9-223">Questa procedura dettagliata illustra gli scenari principali quando si distribuisce i contenitori di Windows per le istanze di contenitore di Azure (ACI) e come è possibile distribuire le app eShopModernizing in ACI.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="cf1b9-224">Scenari</span><span class="sxs-lookup"><span data-stu-id="cf1b9-224">Scenarios</span></span>

<span data-ttu-id="cf1b9-225">Possono esistere variazioni sulla distribuzione di App eShopModernizing in ACI quali la distribuzione solo una o tutte le App (app MVC, applicazione Web Form o servizio WCF).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="cf1b9-226">Nello scenario seguente illustrato di seguito è possibile visualizzare l'app ASP.NET MVC e il contenitore di SQL Server di entrambi gli elementi distribuiti come contenitori in ACI (istanze di contenitore di Azure).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Distribuire da un ambiente di sviluppo in ACI](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="cf1b9-228">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-228">Benefits</span></span>

<span data-ttu-id="cf1b9-229">Istanze di contenitore di Azure rende semplice creare e gestire contenitori Docker in Azure, senza dover effettuare il provisioning di macchine virtuali o adottare un servizio di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="cf1b9-230">Con ACI, è possibile distribuire un contenitore Windows in Azure direttamente ed esporla a internet con un nome di dominio completo (FQDN) in pochi secondi (purché si disponga dell'immagine del contenitore Windows pronto in un registro Docker come contenitori di Azure o Hub Docker Registro di sistema).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="cf1b9-231">Considerazioni</span><span class="sxs-lookup"><span data-stu-id="cf1b9-231">Considerations</span></span>

<span data-ttu-id="cf1b9-232">La distribuzione di contenitori di Windows con una versione completa di .NET Framework / ASP.NET o SQL Server in Azure le istanze di contenitore non è abbastanza veloce come distribuzione in un Host Docker normali (ad esempio, Windows Server 2016 con contenitori Windows) perché deve essere l'immagine Docker scaricato (estratta dal registro Docker) ogni volta e le dimensioni dell'immagine del contenitore SQL (15.1 GB) e l'immagine del contenitore ASP.NET (13.9 GB) sono significativamente grandi, tuttavia, è molto più economica rispetto a mantenere il proprio host docker (in modo permanente in linea Windows Server 2016 con VM di contenitori Windows in Azure) per non parlare di un intero agente di orchestrazione come Kubernetes in Azure (AKS) che rappresenta, d'altra parte, la scelta ideale per distribuzioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="cf1b9-233">Come principale conclusione, tramite le istanze di contenitore di Azure è un'opzione molto accattivante per gli scenari di sviluppo/Test e per le pipeline di integrazione continua/recapito Continuo.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cf1b9-234">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-234">Next steps</span></span>

<span data-ttu-id="cf1b9-235">Esplorare il contenuto più approfondito su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="cf1b9-236">Procedura dettagliata 5: Distribuire le app di Windows basata su contenitori in Kubernetes nel servizio contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="cf1b9-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="cf1b9-237">Istruzioni dettagliate su disponibilità</span><span class="sxs-lookup"><span data-stu-id="cf1b9-237">Technical walkthrough availability</span></span>

<span data-ttu-id="cf1b9-238">La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="cf1b9-239">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cf1b9-239">Overview</span></span>

<span data-ttu-id="cf1b9-240">Un'applicazione basata su contenitori Windows sarà necessario rapidamente a usare le piattaforme, spostando ulteriormente dalle macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="cf1b9-241">Questo è necessario per ottenere con facilità la scalabilità elevata e meglio automatizzata della scalabilità e per un miglioramento significativo delle automaticamente le distribuzioni e controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="cf1b9-242">È possibile raggiungere questi obiettivi con l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile in [servizi contenitore di Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="cf1b9-243">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-243">Goals</span></span>

<span data-ttu-id="cf1b9-244">L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su Windows contenitore in Kubernetes (detto anche *K8s*) nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="cf1b9-245">Distribuzione di Kubernetes da zero è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="cf1b9-246">Distribuire un cluster Kubernetes del servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="cf1b9-247">Distribuire l'applicazione e le risorse correlate al cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="cf1b9-248">Scenari</span><span class="sxs-lookup"><span data-stu-id="cf1b9-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="cf1b9-249">Scenario a: Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="cf1b9-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo](./media/image5-7.png)

<span data-ttu-id="cf1b9-251">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-251">**Figure 5-7.**</span></span> <span data-ttu-id="cf1b9-252">Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="cf1b9-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="cf1b9-253">Scenario b: Distribuire un cluster Kubernetes dalla pipeline CI/CD in servizi di Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="cf1b9-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Distribuire un cluster Kubernetes dalla pipeline CI/CD in servizi di Azure DevOps](./media/image5-8.png)

<span data-ttu-id="cf1b9-255">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="cf1b9-255">**Figure 5-8.**</span></span> <span data-ttu-id="cf1b9-256">Distribuire un cluster Kubernetes dalla pipeline CI/CD in servizi di Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="cf1b9-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="cf1b9-257">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-257">Benefits</span></span>

<span data-ttu-id="cf1b9-258">Esistono diversi vantaggi per la distribuzione in un cluster di Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="cf1b9-259">Il vantaggio più importante è che si ottiene un ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitore si desidera utilizzare (inner una scalabilità molto elevata di nodi esistenti) e in base al numero di nodi o macchine virtuali nel (cluster scalabilità globale del cluster).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="cf1b9-260">Servizio contenitore di Azure consente di ottimizzare le tecnologie e strumenti open source più diffusi per Azure.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="cf1b9-261">Si ottiene una soluzione che offre la portabilità sia per i contenitori per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="cf1b9-262">Selezionare le dimensioni, il numero di host, e dell'agente di orchestrazione strumenti-servizio contenitore gestisce tutto il resto.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="cf1b9-263">Con Kubernetes, gli sviluppatori possono passare da pensare macchine fisiche e virtuali, alla pianificazione di un'infrastruttura incentrata sui contenitori che facilita le funzionalità seguenti, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="cf1b9-264">Applicazioni basate su più contenitori</span><span class="sxs-lookup"><span data-stu-id="cf1b9-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="cf1b9-265">La replica di istanze di contenitore e la scalabilità automatica orizzontale</span><span class="sxs-lookup"><span data-stu-id="cf1b9-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="cf1b9-266">Denominazione e l'individuazione (ad esempio, il DNS interno)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="cf1b9-267">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="cf1b9-267">Balancing loads</span></span>

- <span data-ttu-id="cf1b9-268">Aggiornamenti in sequenza</span><span class="sxs-lookup"><span data-stu-id="cf1b9-268">Rolling updates</span></span>

- <span data-ttu-id="cf1b9-269">Distribuzione segreti</span><span class="sxs-lookup"><span data-stu-id="cf1b9-269">Distributing secrets</span></span>

- <span data-ttu-id="cf1b9-270">Controlli di integrità dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="cf1b9-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="cf1b9-271">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-271">Next steps</span></span>

<span data-ttu-id="cf1b9-272">Esplorare il contenuto più approfondito su wiki di GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="cf1b9-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="cf1b9-273">Procedura dettagliata 6: Distribuire le app basate su contenitori Windows in servizio App di Azure per contenitori</span><span class="sxs-lookup"><span data-stu-id="cf1b9-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="cf1b9-274">Istruzioni dettagliate su disponibilità</span><span class="sxs-lookup"><span data-stu-id="cf1b9-274">Technical walkthrough availability</span></span>

<span data-ttu-id="cf1b9-275">La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="cf1b9-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="cf1b9-276">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cf1b9-276">Overview</span></span>

<span data-ttu-id="cf1b9-277">Una semplice applicazione in contenitori usando i contenitori di Windows può essere distribuita facilmente nel servizio App di Azure per contenitori.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="cf1b9-278">Questo è l'approccio consigliato per la maggior parte delle applicazioni basate su contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="cf1b9-279">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-279">Goals</span></span>

<span data-ttu-id="cf1b9-280">L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su contenitori di Windows per il servizio App di Azure per contenitori da un registro (Hub Docker o registro contenitori di Azure).</span><span class="sxs-lookup"><span data-stu-id="cf1b9-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="cf1b9-281">Scenario</span><span class="sxs-lookup"><span data-stu-id="cf1b9-281">Scenario</span></span>

![Distribuire app basate su contenitori Windows in servizio App di Azure per contenitori](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="cf1b9-283">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-283">Benefits</span></span>

<span data-ttu-id="cf1b9-284">Distribuzione servizio App di Azure per contenitori offre i vantaggi dei contenitori associati con i vantaggi di PaaS di Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="cf1b9-285">Il servizio app può essere facilmente ridimensionato sia verticalmente che orizzontalmente e può essere configurato per la scalabilità automatica per soddisfare le variazioni della domanda.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="cf1b9-286">Gli aggiornamenti possono essere eseguiti senza tempi di inattività e configurazione della distribuzione continua da un registro è possibile configurare facilmente anche.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cf1b9-287">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf1b9-287">Next steps</span></span>

<span data-ttu-id="cf1b9-288">Esplorare il contenuto più approfondito su wiki di GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="cf1b9-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="cf1b9-289">[Precedente](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [Successivo](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-289">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
