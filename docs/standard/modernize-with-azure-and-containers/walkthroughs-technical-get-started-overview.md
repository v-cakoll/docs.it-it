---
title: Procedure dettagliate e technical Panoramica avviata
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows | procedure dettagliate e technical Panoramica avviata
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0bad7e3afbdf3e55c447319b3756f2235b9e0a19
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="009b3-103">Procedure dettagliate e technical Panoramica avviata</span><span class="sxs-lookup"><span data-stu-id="009b3-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="009b3-104">Per limitare le dimensioni di questo e-book, documentazione tecnica aggiuntiva e le procedure dettagliate di complete sono stati resi disponibili in un repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="009b3-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="009b3-105">La serie in linea di procedure dettagliate in cui sono descritto in questo capitolo descrive la procedura di configurazione di più ambienti basati su contenitori di Windows e la distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="009b3-106">Le sezioni seguenti illustrano ciò che ogni procedura dettagliata è sui relativi obiettivi e degli obiettivi di alto livello e un diagramma di attività che sono coinvolti.</span><span class="sxs-lookup"><span data-stu-id="009b3-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="009b3-107">È possibile ottenere le procedure dettagliate autonomamente nel *eShopModernizing* wiki repository GitHub di App in [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span><span class="sxs-lookup"><span data-stu-id="009b3-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="009b3-108">Elenco di istruzioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="009b3-108">Technical walkthrough list</span></span>

<span data-ttu-id="009b3-109">Le procedure dettagliate seguenti avviato get forniscono linee guida tecnica completa e coerenza per le app di esempio che è possibile sollevare e spostare usando i contenitori e quindi spostare utilizzando più opzioni di distribuzione in Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="009b3-110">Ognuna delle procedure dettagliate seguenti utilizza il nuovo esempio eShopLegacy eShopModernizing le App e quali sono disponibili in GitHub all'indirizzo [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="009b3-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="009b3-111">**Presentazione dell'App legacy eShop**</span><span class="sxs-lookup"><span data-stu-id="009b3-111">**Tour of eShop legacy apps**</span></span>

- <span data-ttu-id="009b3-112">**Le applicazioni .NET esistenti con i contenitori di Windows inserita in un contenitore**</span><span class="sxs-lookup"><span data-stu-id="009b3-112">**Containerize your existing .NET applications with Windows Containers**</span></span>

- <span data-ttu-id="009b3-113">**Distribuire l'app basata su contenitori di Windows in macchine virtuali di Azure**</span><span class="sxs-lookup"><span data-stu-id="009b3-113">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="009b3-114">**Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di Azure**</span><span class="sxs-lookup"><span data-stu-id="009b3-114">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="009b3-115">**Distribuire le app basate su contenitori di Windows Azure Service Fabric**</span><span class="sxs-lookup"><span data-stu-id="009b3-115">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="009b3-116">Procedura dettagliata 1: Panoramica delle applicazioni legacy eShop</span><span class="sxs-lookup"><span data-stu-id="009b3-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="009b3-117">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="009b3-117">Technical walkthrough availability</span></span>

<span data-ttu-id="009b3-118">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="009b3-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a><span data-ttu-id="009b3-119">Panoramica</span><span class="sxs-lookup"><span data-stu-id="009b3-119">Overview</span></span>

<span data-ttu-id="009b3-120">In questa procedura dettagliata, è possibile esplorare l'implementazione iniziale due applicazioni di esempio legacy.</span><span class="sxs-lookup"><span data-stu-id="009b3-120">In this walkthrough, you can explore the initial implementation of two sample legacy applications.</span></span> <span data-ttu-id="009b3-121">Entrambe le app di esempio dispone di un'architettura monolitica e sono state create tramite ASP.NET classico.</span><span class="sxs-lookup"><span data-stu-id="009b3-121">Both sample apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="009b3-122">Un'applicazione basata su ASP.NET 4. x MVC; la seconda applicazione è basata su Web Form ASP.NET 4. x.</span><span class="sxs-lookup"><span data-stu-id="009b3-122">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="009b3-123">Entrambe le applicazioni presenti il [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="009b3-123">Both applications are in the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

<span data-ttu-id="009b3-124">È possibile inserita in un contenitore entrambe le app di esempio, simile al modo in cui è possibile inserita in un contenitore un classico [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) applicazione (WCF) deve essere utilizzato come un'applicazione desktop.</span><span class="sxs-lookup"><span data-stu-id="009b3-124">You can containerize both sample apps, similar to the way you can containerize a classic [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) (WCF) application to be consumed as a desktop application.</span></span> <span data-ttu-id="009b3-125">Per un esempio, vedere [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span><span class="sxs-lookup"><span data-stu-id="009b3-125">For an example, see [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span></span>

### <a name="goals"></a><span data-ttu-id="009b3-126">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="009b3-126">Goals</span></span>

<span data-ttu-id="009b3-127">L'obiettivo principale di questa procedura dettagliata è semplicemente per acquisire familiarità con queste App e con il codice e configurazione.</span><span class="sxs-lookup"><span data-stu-id="009b3-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="009b3-128">È possibile configurare le App in modo che possano generare e utilizzare dati fittizi, senza l'utilizzo del database SQL, a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="009b3-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="009b3-129">Questa configurazione facoltativa è basata sul inserimento di dipendenze, in modo separato.</span><span class="sxs-lookup"><span data-stu-id="009b3-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario"></a><span data-ttu-id="009b3-130">Scenario</span><span class="sxs-lookup"><span data-stu-id="009b3-130">Scenario</span></span>

<span data-ttu-id="009b3-131">Figura 5-1 viene illustrato un semplice scenario di applicazioni legacy originale.</span><span class="sxs-lookup"><span data-stu-id="009b3-131">Figure 5-1 shows the simple scenario of the original legacy applications.</span></span>

> ![Scenario semplice architettura delle applicazioni legacy originale](./media/image5-1.png)
>
> <span data-ttu-id="009b3-133">**Figura 5-1.**</span><span class="sxs-lookup"><span data-stu-id="009b3-133">**Figure 5-1.**</span></span> <span data-ttu-id="009b3-134">Scenario semplice architettura delle applicazioni legacy originale</span><span class="sxs-lookup"><span data-stu-id="009b3-134">Simple architecture scenario of the original legacy applications</span></span>

<span data-ttu-id="009b3-135">Da una prospettiva di dominio aziendale, entrambe le app offrono lo stesso catalogo le funzionalità di gestione.</span><span class="sxs-lookup"><span data-stu-id="009b3-135">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="009b3-136">I membri del team enterprise eShop utilizzerebbe l'app per visualizzare e modificare il catalogo dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="009b3-136">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> <span data-ttu-id="009b3-137">Figura 5-2 è illustrata la schermata iniziale di app.</span><span class="sxs-lookup"><span data-stu-id="009b3-137">Figure 5-2 shows the initial app screenshots.</span></span>

![Applicazioni ASP.NET MVC e Web Form ASP.NET (le tecnologie esistenti/legacy)](./media/image5-2.png)

> <span data-ttu-id="009b3-139">**Figura 5-2.**</span><span class="sxs-lookup"><span data-stu-id="009b3-139">**Figure 5-2.**</span></span> <span data-ttu-id="009b3-140">Applicazioni ASP.NET MVC e Web Form ASP.NET (le tecnologie esistenti/legacy)</span><span class="sxs-lookup"><span data-stu-id="009b3-140">ASP.NET MVC and ASP.NET Web Forms applications (existing/legacy technologies)</span></span>

<span data-ttu-id="009b3-141">Si tratta di applicazioni web che consentono di esplorare e modificare le voci di catalogo.</span><span class="sxs-lookup"><span data-stu-id="009b3-141">These are web applications that are used to browse and modify catalog entries.</span></span> <span data-ttu-id="009b3-142">Il fatto che entrambe le app offrono le stesse funzionalità di business funzionali è sufficiente per il confronto.</span><span class="sxs-lookup"><span data-stu-id="009b3-142">The fact that both apps deliver the same business/functional features is simply for comparison purposes.</span></span> <span data-ttu-id="009b3-143">È possibile visualizzare un processo di modernizzazione simile per le app che sono state create tramite il framework ASP.NET MVC e Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="009b3-143">You can see a similar modernization process for apps that were created by using the ASP.NET MVC and ASP.NET Web Forms frameworks.</span></span>

<span data-ttu-id="009b3-144">Le dipendenze in ASP.NET 4. x o versioni precedenti (per MVC o Web Form) significa che queste applicazioni non verranno eseguito su .NET Core, a meno che il codice è completamente riscritto utilizzando ASP.NET MVC di base.</span><span class="sxs-lookup"><span data-stu-id="009b3-144">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> <span data-ttu-id="009b3-145">Viene descritto il punto che se non si desidera progettare nuovamente o riscrivere il codice, è possibile inserita in un contenitore applicazioni esistenti e continuare a usare le stesse tecnologie .NET e lo stesso codice.</span><span class="sxs-lookup"><span data-stu-id="009b3-145">This demonstrates the point that if you don't want to re-architect or rewrite code, you can containerize existing applications, and still use the same .NET technologies and the same code.</span></span> <span data-ttu-id="009b3-146">È possibile vedere come è possibile eseguire applicazioni come questi contenitori, senza apportare modifiche al codice legacy.</span><span class="sxs-lookup"><span data-stu-id="009b3-146">You can see how you can run applications like these in containers, without any changes to legacy code.</span></span>

### <a name="benefits"></a><span data-ttu-id="009b3-147">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="009b3-147">Benefits</span></span>

<span data-ttu-id="009b3-148">I vantaggi di questa procedura dettagliata sono semplici: semplicemente acquisire familiarità con la configurazione di codice e l'applicazione, in base a inserimento di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="009b3-148">The benefits of this walkthrough are simple: Just get familiar with the code and application configuration, based on dependency injection.</span></span> <span data-ttu-id="009b3-149">Quindi, è possibile provare a utilizzare questo approccio quando è inserita in un contenitore e distribuire in più ambienti in futuro.</span><span class="sxs-lookup"><span data-stu-id="009b3-149">Then, you can experiment with this approach when you containerize and deploy to multiple environments in the future.</span></span>

### <a name="next-steps"></a><span data-ttu-id="009b3-150">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="009b3-150">Next steps</span></span>

<span data-ttu-id="009b3-151">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="009b3-151">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="009b3-152">Procedura dettagliata 2: Inserita in un contenitore le applicazioni .NET esistenti con i contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="009b3-152">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="009b3-153">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="009b3-153">Technical walkthrough availability</span></span>

<span data-ttu-id="009b3-154">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="009b3-154">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a><span data-ttu-id="009b3-155">Panoramica</span><span class="sxs-lookup"><span data-stu-id="009b3-155">Overview</span></span>

<span data-ttu-id="009b3-156">Utilizzare i contenitori di Windows per migliorare la distribuzione di applicazioni .NET esistenti, ad esempio quelle basate su WCF, MVC o Web Form per gli ambienti di test, sviluppo e produzione.</span><span class="sxs-lookup"><span data-stu-id="009b3-156">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="009b3-157">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="009b3-157">Goals</span></span>

<span data-ttu-id="009b3-158">L'obiettivo di questa procedura dettagliata è descrivere le diverse opzioni per containerizing un'applicazione esistente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="009b3-158">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="009b3-159">È possibile:</span><span class="sxs-lookup"><span data-stu-id="009b3-159">You can:</span></span>

- <span data-ttu-id="009b3-160">L'applicazione inserita in un contenitore utilizzando [Visual Studio 2017 Tools per Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="009b3-160">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="009b3-161">L'applicazione inserita in un contenitore aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)e quindi utilizzando il [CLI di Docker](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="009b3-161">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="009b3-162">L'applicazione inserita in un contenitore utilizzando il [Img2Docker](https://github.com/docker/communitytools-image2docker-win) strumento (uno strumento open source da Docker).</span><span class="sxs-lookup"><span data-stu-id="009b3-162">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="009b3-163">Questa procedura dettagliata si concentra sugli strumenti di Visual Studio 2017 per approccio Docker, ma gli altri due approcci sono piuttosto simili per quanto riguarda utilizzo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="009b3-163">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario"></a><span data-ttu-id="009b3-164">Scenario</span><span class="sxs-lookup"><span data-stu-id="009b3-164">Scenario</span></span>

<span data-ttu-id="009b3-165">Figura 5-3 viene illustrato lo scenario per le applicazioni legacy eShop nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="009b3-165">Figure 5-3 shows the scenario for containerized eShop legacy applications.</span></span>

> ![Diagramma dell'architettura semplificata delle applicazioni nei contenitori in un ambiente di sviluppo](./media/image5-3.png)
>
> <span data-ttu-id="009b3-167">**Figura 5-3.**</span><span class="sxs-lookup"><span data-stu-id="009b3-167">**Figure 5-3.**</span></span> <span data-ttu-id="009b3-168">Diagramma dell'architettura semplificata delle applicazioni nei contenitori in un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="009b3-168">Simplified architecture diagram of containerized applications in a development environment</span></span>

### <a name="benefits"></a><span data-ttu-id="009b3-169">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="009b3-169">Benefits</span></span>

<span data-ttu-id="009b3-170">Esistono vantaggi rispetto all'esecuzione dell'applicazione monolitica in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="009b3-170">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="009b3-171">Creare un'immagine per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="009b3-171">First, you create an image for the application.</span></span> <span data-ttu-id="009b3-172">Da quel momento in poi, ogni distribuzione viene eseguito nello stesso ambiente.</span><span class="sxs-lookup"><span data-stu-id="009b3-172">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="009b3-173">Ogni contenitore Usa la stessa versione del sistema operativo, ha la stessa versione di dipendenze installata, Usa la stessa versione di .NET framework e viene compilato con lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="009b3-173">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="009b3-174">In pratica, controllare le dipendenze dell'applicazione tramite un'immagine di Docker.</span><span class="sxs-lookup"><span data-stu-id="009b3-174">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="009b3-175">Quando si distribuiscono i contenitori, le dipendenze viaggiano con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="009b3-175">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="009b3-176">Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente di coerente fornito dai contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="009b3-176">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="009b3-177">I problemi che vengono visualizzati solo con alcune versioni possono essere rilevati immediatamente, invece di replica in un ambiente di gestione temporanea o produzione.</span><span class="sxs-lookup"><span data-stu-id="009b3-177">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="009b3-178">Differenze in ambienti di sviluppo utilizzati dai membri del team di sviluppo è importante minore quando le applicazioni eseguite nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="009b3-178">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="009b3-179">Le applicazioni nei contenitori hanno anche una curva di scalabilità orizzontale più semplice.</span><span class="sxs-lookup"><span data-stu-id="009b3-179">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="009b3-180">Le applicazioni nei contenitori consentono di disporre di altre applicazioni e le istanze del servizio (basate su contenitori) in una macchina virtuale o un computer fisico rispetto alle distribuzioni applicazione regolare per ogni macchina.</span><span class="sxs-lookup"><span data-stu-id="009b3-180">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="009b3-181">Questo si traduce in maggiore densità e meno necessarie risorse, soprattutto quando si utilizzano orchestrators come Kubernetes o Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="009b3-181">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="009b3-182">Creazione dei contenitori, in situazioni ideali, non è necessario apportare modifiche al codice dell'applicazione (C\#).</span><span class="sxs-lookup"><span data-stu-id="009b3-182">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="009b3-183">Nella maggior parte degli scenari, è necessario solo i file di metadati di distribuzione (file Dockerfile e Docker Compose) Docker.</span><span class="sxs-lookup"><span data-stu-id="009b3-183">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="009b3-184">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="009b3-184">Next steps</span></span>

<span data-ttu-id="009b3-185">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span><span class="sxs-lookup"><span data-stu-id="009b3-185">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span></span>

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="009b3-186">Procedura dettagliata 3: Distribuire l'app basata su contenitori di Windows in macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="009b3-186">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="009b3-187">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="009b3-187">Technical walkthrough availability</span></span>

<span data-ttu-id="009b3-188">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="009b3-188">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="009b3-189">Panoramica</span><span class="sxs-lookup"><span data-stu-id="009b3-189">Overview</span></span>

<span data-ttu-id="009b3-190">La distribuzione in un host Docker in un Windows Server 2016 macchina virtuale (VM) in Azure consente di configurare rapidamente gli ambienti di sviluppo/test/staging.</span><span class="sxs-lookup"><span data-stu-id="009b3-190">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="009b3-191">Offre inoltre una posizione comune per i tester o gli utenti di business convalidare l'app.</span><span class="sxs-lookup"><span data-stu-id="009b3-191">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="009b3-192">Macchine virtuali anche possono essere modalità valido come ambienti di produzione un servizio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="009b3-192">VMs also can be valid Infrastucture as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="009b3-193">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="009b3-193">Goals</span></span>

<span data-ttu-id="009b3-194">L'obiettivo di questa procedura dettagliata è di illustrare le alternative più, che è necessario quando si distribuiscono i contenitori di Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="009b3-194">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="009b3-195">Scenari</span><span class="sxs-lookup"><span data-stu-id="009b3-195">Scenarios</span></span>

<span data-ttu-id="009b3-196">In questa procedura dettagliata sono illustrati i diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="009b3-196">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="009b3-197">Scenario a: distribuire una macchina virtuale di Azure da un PC di sviluppo tramite una connessione al motore Docker</span><span class="sxs-lookup"><span data-stu-id="009b3-197">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Distribuire in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker](./media/image5-4.png)

> <span data-ttu-id="009b3-199">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="009b3-199">**Figure 5-4.**</span></span> <span data-ttu-id="009b3-200">Distribuire in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker</span><span class="sxs-lookup"><span data-stu-id="009b3-200">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="009b3-201">Scenario b: distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker</span><span class="sxs-lookup"><span data-stu-id="009b3-201">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker](./media/image5-5.png)

> <span data-ttu-id="009b3-203">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="009b3-203">**Figure 5-5.**</span></span> <span data-ttu-id="009b3-204">Distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker</span><span class="sxs-lookup"><span data-stu-id="009b3-204">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="009b3-205">Scenario c: distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="009b3-205">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services](./media/image5-6.png)

> <span data-ttu-id="009b3-207">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="009b3-207">**Figure 5-6.**</span></span> <span data-ttu-id="009b3-208">Distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="009b3-208">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="009b3-209">Macchine virtuali di Azure per i contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="009b3-209">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="009b3-210">Macchine virtuali di Azure per i contenitori di Windows sono le macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambi con il motore Docker impostato.</span><span class="sxs-lookup"><span data-stu-id="009b3-210">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="009b3-211">Nella maggior parte dei casi, viene utilizzato Windows Server 2016 in macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-211">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="009b3-212">Azure offre attualmente di una macchina virtuale denominata **Windows Server 2016 con contenitori**.</span><span class="sxs-lookup"><span data-stu-id="009b3-212">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="009b3-213">È possibile utilizzare questa macchina virtuale per provare la nuova funzionalità di contenitore di Windows Server, con Windows Server Core o Nano Server di Windows.</span><span class="sxs-lookup"><span data-stu-id="009b3-213">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="009b3-214">Immagini del sistema operativo contenitore vengono installate e quindi la macchina virtuale è pronta all'uso con Docker.</span><span class="sxs-lookup"><span data-stu-id="009b3-214">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="009b3-215">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="009b3-215">Benefits</span></span>

<span data-ttu-id="009b3-216">Sebbene i contenitori di Windows possono essere distribuiti a macchine virtuali in locale Windows Server 2016, quando si distribuiscono in Azure, è possibile ottenere un modo più semplice per iniziare, con macchine virtuali di contenitore pronto all'uso Windows Server.</span><span class="sxs-lookup"><span data-stu-id="009b3-216">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="009b3-217">Anche possibile ottenere un percorso online comune che è accessibile ai tester e la scalabilità automatica tramite il set di scalabilità di macchine virtuali di Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-217">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="009b3-218">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="009b3-218">Next steps</span></span>

<span data-ttu-id="009b3-219">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="009b3-219">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="009b3-220">Procedura dettagliata 4: Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="009b3-220">Walkthrough 4: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="009b3-221">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="009b3-221">Technical walkthrough availability</span></span>

<span data-ttu-id="009b3-222">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="009b3-222">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="009b3-223">Panoramica</span><span class="sxs-lookup"><span data-stu-id="009b3-223">Overview</span></span>

<span data-ttu-id="009b3-224">Un'applicazione che si basa sui contenitori di Windows, rapidamente è necessario utilizzare le piattaforme, spostando ulteriormente da macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="009b3-224">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="009b3-225">Questo è necessario per ottenere facilmente la scalabilità elevata meglio la scalabilità automatica e per un miglioramento significativo automaticamente le distribuzioni e controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="009b3-225">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="009b3-226">È possibile raggiungere questi obiettivi tramite l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile in [servizi contenitore Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="009b3-226">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="009b3-227">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="009b3-227">Goals</span></span>

<span data-ttu-id="009b3-228">L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su contenitore di Windows per Kubernetes (chiamato anche *K8s*) nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-228">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="009b3-229">La distribuzione in Kubernetes da zero è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="009b3-229">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="009b3-230">Distribuire un cluster Kubernetes al servizio di contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-230">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="009b3-231">Distribuire l'applicazione e le relative risorse nel cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="009b3-231">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="009b3-232">Scenari</span><span class="sxs-lookup"><span data-stu-id="009b3-232">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="009b3-233">Scenario a: distribuire direttamente a un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="009b3-233">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo](./media/image5-7.png)

> <span data-ttu-id="009b3-235">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="009b3-235">**Figure 5-7.**</span></span> <span data-ttu-id="009b3-236">Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="009b3-236">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="009b3-237">Scenario b: distribuire a un cluster Kubernetes CI/CD pipeline in Team Services</span><span class="sxs-lookup"><span data-stu-id="009b3-237">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Distribuire un cluster Kubernetes dalla pipeline CI/CD-ROM in Team Services](./media/image5-8.png)

> <span data-ttu-id="009b3-239">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="009b3-239">**Figure 5-8.**</span></span> <span data-ttu-id="009b3-240">Distribuire un cluster Kubernetes dalla pipeline CI/CD-ROM in Team Services</span><span class="sxs-lookup"><span data-stu-id="009b3-240">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="009b3-241">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="009b3-241">Benefits</span></span>

<span data-ttu-id="009b3-242">Esistono numerosi vantaggi per la distribuzione a un cluster in Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="009b3-242">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="009b3-243">Il vantaggio più importante è che si ottiene un ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitori, si desidera utilizzare (scalabilità interna in nodi esistenti) e in base al numero di nodi o le macchine virtuali in (il cluster scalabilità globale del cluster).</span><span class="sxs-lookup"><span data-stu-id="009b3-243">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="009b3-244">Il servizio contenitore di Azure consente di ottimizzare tecnologie e strumenti open source più diffusi in particolare per Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-244">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="009b3-245">È possibile ottenere una soluzione aperta che offre la portabilità, per i contenitori e per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="009b3-245">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="009b3-246">Selezionare la dimensione, il numero di host, e orchestrator strumenti-Container servizio gestisce tutti gli altri elementi.</span><span class="sxs-lookup"><span data-stu-id="009b3-246">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="009b3-247">Con Kubernetes, gli sviluppatori possono sullo stato da considerare macchine fisiche e virtuali, per la pianificazione di un'infrastruttura incentrato sul contenitore che facilita le seguenti funzionalità, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="009b3-247">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="009b3-248">In base a più contenitori di applicazioni</span><span class="sxs-lookup"><span data-stu-id="009b3-248">Applications based on multiple containers</span></span>

- <span data-ttu-id="009b3-249">La replica delle istanze di contenitori e il ridimensionamento orizzontale</span><span class="sxs-lookup"><span data-stu-id="009b3-249">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="009b3-250">Denominazione e individuazione (ad esempio, DNS interno)</span><span class="sxs-lookup"><span data-stu-id="009b3-250">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="009b3-251">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="009b3-251">Balancing loads</span></span>

- <span data-ttu-id="009b3-252">Gli aggiornamenti in sequenza</span><span class="sxs-lookup"><span data-stu-id="009b3-252">Rolling updates</span></span>

- <span data-ttu-id="009b3-253">Distribuzione di segreti</span><span class="sxs-lookup"><span data-stu-id="009b3-253">Distributing secrets</span></span>

- <span data-ttu-id="009b3-254">Controlli di integrità dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="009b3-254">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="009b3-255">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="009b3-255">Next steps</span></span>

<span data-ttu-id="009b3-256">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="009b3-256">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="009b3-257">Procedura dettagliata 5: Distribuire le app basate su contenitori di Windows Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="009b3-257">Walkthrough 5: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="009b3-258">Procedura dettagliata tecniche disponibilità</span><span class="sxs-lookup"><span data-stu-id="009b3-258">Technical walkthrough availability</span></span>

<span data-ttu-id="009b3-259">Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="009b3-259">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="009b3-260">Panoramica</span><span class="sxs-lookup"><span data-stu-id="009b3-260">Overview</span></span>

<span data-ttu-id="009b3-261">Un'applicazione basata su contenitori di Windows rapidamente deve utilizzare le piattaforme, spostando ulteriormente da macchine virtuali IaaS.</span><span class="sxs-lookup"><span data-stu-id="009b3-261">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="009b3-262">Questo è necessario per ottenere facilmente la scalabilità elevata meglio la scalabilità automatica e per un miglioramento significativo automaticamente le distribuzioni e controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="009b3-262">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="009b3-263">È possibile raggiungere questi obiettivi tramite orchestrator Azure Service Fabric è disponibile nel cloud di Azure, ma è anche disponibile per l'utilizzo di on-premise, o anche in un cloud pubblico diverso.</span><span class="sxs-lookup"><span data-stu-id="009b3-263">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="009b3-264">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="009b3-264">Goals</span></span>

<span data-ttu-id="009b3-265">L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su Windows contenitore a un cluster di Service Fabric in Azure.</span><span class="sxs-lookup"><span data-stu-id="009b3-265">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="009b3-266">Distribuzione di Service Fabric da zero è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="009b3-266">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="009b3-267">Distribuire un cluster di Service Fabric in Azure (o in un ambiente diverso).</span><span class="sxs-lookup"><span data-stu-id="009b3-267">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="009b3-268">Distribuire l'applicazione e le relative risorse nel cluster di Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="009b3-268">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="009b3-269">Scenari</span><span class="sxs-lookup"><span data-stu-id="009b3-269">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="009b3-270">Scenario a: distribuire direttamente a un cluster di Service Fabric da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="009b3-270">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo](./media/image5-9.png)

> <span data-ttu-id="009b3-272">**Figura 5-9.**</span><span class="sxs-lookup"><span data-stu-id="009b3-272">**Figure 5-9.**</span></span> <span data-ttu-id="009b3-273">Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="009b3-273">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="009b3-274">Scenario b: distribuire a un cluster di Service Fabric dal CI/CD-ROM pipeline in Team Services</span><span class="sxs-lookup"><span data-stu-id="009b3-274">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Distribuire un cluster di Service Fabric dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services](./media/image5-10.png)

> <span data-ttu-id="009b3-276">**Figura 5-10.**</span><span class="sxs-lookup"><span data-stu-id="009b3-276">**Figure 5-10.**</span></span> <span data-ttu-id="009b3-277">Distribuire un cluster di Service Fabric dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="009b3-277">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="009b3-278">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="009b3-278">Benefits</span></span>

<span data-ttu-id="009b3-279">I vantaggi della distribuzione a un cluster nell'infrastruttura del servizio sono simili ai vantaggi dell'utilizzo Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="009b3-279">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="009b3-280">Una differenza, tuttavia, è che Service Fabric è un ambiente di produzione più avanzato per le applicazioni di Windows rispetto a Kubernetes, ovvero in una fase beta per i contenitori di Windows nella Kubernetes versione 1.9 (2017 dicembre).</span><span class="sxs-lookup"><span data-stu-id="009b3-280">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="009b3-281">Kubernetes è un ambiente più avanzato per Linux.</span><span class="sxs-lookup"><span data-stu-id="009b3-281">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="009b3-282">Il principale vantaggio dell'utilizzo di Azure Service Fabric è che si dispone di un ambiente di ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitori, si desidera utilizzare (scalabilità interna in nodi esistenti) e in base al numero di i nodi o macchine virtuali in cluster (scalabilità globale del cluster).</span><span class="sxs-lookup"><span data-stu-id="009b3-282">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="009b3-283">Azure Service Fabric offre portabilità per i contenitori e per la configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="009b3-283">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="009b3-284">È un'infrastruttura del servizio cluster in Azure oppure installarlo in locale nel proprio Data Center.</span><span class="sxs-lookup"><span data-stu-id="009b3-284">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="009b3-285">È anche possibile installare un cluster di Service Fabric in un cloud diverso, ad esempio [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="009b3-285">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="009b3-286">Con Service Fabric, gli sviluppatori possono sullo stato da considerare macchine fisiche e virtuali per la pianificazione di un'infrastruttura incentrato sul contenitore che facilita le seguenti funzionalità, tra gli altri:</span><span class="sxs-lookup"><span data-stu-id="009b3-286">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="009b3-287">Applicazioni basate su più contenitori.</span><span class="sxs-lookup"><span data-stu-id="009b3-287">Applications based on multiple containers.</span></span>

- <span data-ttu-id="009b3-288">La replica di istanze di contenitori e scalabilità orizzontale automatica.</span><span class="sxs-lookup"><span data-stu-id="009b3-288">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="009b3-289">Denominazione e individuazione (ad esempio, DNS interno).</span><span class="sxs-lookup"><span data-stu-id="009b3-289">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="009b3-290">Bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="009b3-290">Balancing loads.</span></span>

- <span data-ttu-id="009b3-291">Aggiornamenti in sequenza.</span><span class="sxs-lookup"><span data-stu-id="009b3-291">Rolling updates.</span></span>

- <span data-ttu-id="009b3-292">Distribuire i segreti.</span><span class="sxs-lookup"><span data-stu-id="009b3-292">Distributing secrets.</span></span>

- <span data-ttu-id="009b3-293">Controlla l'integrità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="009b3-293">Application health checks.</span></span>

<span data-ttu-id="009b3-294">Le seguenti funzionalità sono esclusive nell'infrastruttura di servizio (rispetto a altro orchestrators):</span><span class="sxs-lookup"><span data-stu-id="009b3-294">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="009b3-295">Funzionalità di servizi con stato, tramite il modello applicazione servizi affidabili.</span><span class="sxs-lookup"><span data-stu-id="009b3-295">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="009b3-296">Modello di attori, tramite il modello di applicazione Reliable Actors.</span><span class="sxs-lookup"><span data-stu-id="009b3-296">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="009b3-297">Distribuire processi ossa bare, oltre ai contenitori di Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="009b3-297">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="009b3-298">Gli aggiornamenti in sequenza e controlli di integrità avanzati.</span><span class="sxs-lookup"><span data-stu-id="009b3-298">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="009b3-299">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="009b3-299">Next steps</span></span>

<span data-ttu-id="009b3-300">Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:</span><span class="sxs-lookup"><span data-stu-id="009b3-300">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
<span data-ttu-id="009b3-301">[Precedente](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Successivo](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="009b3-301">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
