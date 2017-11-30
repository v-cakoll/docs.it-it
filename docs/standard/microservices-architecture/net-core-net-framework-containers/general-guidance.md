---
title: Indicazioni generali
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Indicazioni generali
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a><span data-ttu-id="1cb99-104">Indicazioni generali</span><span class="sxs-lookup"><span data-stu-id="1cb99-104">General guidance</span></span>

<span data-ttu-id="1cb99-105">In questa sezione fornisce un riepilogo del momento in cui scegliere .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1cb99-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="1cb99-106">Sono forniti ulteriori dettagli su queste opzioni nelle sezioni che seguono.</span><span class="sxs-lookup"><span data-stu-id="1cb99-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="1cb99-107">Utilizzare .NET Core, con i contenitori di Windows, o Linux per l'applicazione nei contenitori di Docker server quando:</span><span class="sxs-lookup"><span data-stu-id="1cb99-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="1cb99-108">Si hanno esigenze multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="1cb99-108">You have cross-platform needs.</span></span> <span data-ttu-id="1cb99-109">Ad esempio, si desidera utilizzare i contenitori di Windows e Linux.</span><span class="sxs-lookup"><span data-stu-id="1cb99-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="1cb99-110">L'architettura dell'applicazione si basa su microservizi.</span><span class="sxs-lookup"><span data-stu-id="1cb99-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="1cb99-111">È necessario avviare fast contenitori e desidera un footprint ridotto per ogni contenitore per ottenere una migliore densità o più contenitori per unità di hardware, per ridurre i costi.</span><span class="sxs-lookup"><span data-stu-id="1cb99-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="1cb99-112">In breve, quando si creano nuove applicazioni .NET nei contenitori, è necessario considerare .NET Core come scelta predefinita.</span><span class="sxs-lookup"><span data-stu-id="1cb99-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="1cb99-113">Dispone di numerosi vantaggi e più appropriato per la filosofia di contenitori e lo stile di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1cb99-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="1cb99-114">Un ulteriore vantaggio dell'utilizzo di .NET Core è possibile eseguire side-by versioni di .NET per le applicazioni all'interno della macchina stessa.</span><span class="sxs-lookup"><span data-stu-id="1cb99-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="1cb99-115">Questo vantaggio è più importante per i server o le macchine virtuali che non utilizzano contenitori, perché le versioni di .NET che l'app è necessario isolare i contenitori.</span><span class="sxs-lookup"><span data-stu-id="1cb99-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="1cb99-116">(Purché siano compatibili con il sistema operativo sottostante).</span><span class="sxs-lookup"><span data-stu-id="1cb99-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="1cb99-117">Utilizzare .NET Framework, i contenitori di Windows per l'applicazione nei contenitori di Docker server quando:</span><span class="sxs-lookup"><span data-stu-id="1cb99-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="1cb99-118">L'applicazione attualmente Usa .NET Framework e è associate dipendenze complesse in Windows.</span><span class="sxs-lookup"><span data-stu-id="1cb99-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="1cb99-119">È necessario usare le API di Windows che non sono supportati da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1cb99-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="1cb99-120">È necessario utilizzare le librerie .NET di terze parti o pacchetti NuGet che non sono disponibili per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1cb99-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="1cb99-121">L'utilizzo di .NET Framework in Docker può migliorare le esperienze di distribuzione riducendo al minimo i problemi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1cb99-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="1cb99-122">Questo [ *"sollevare e spostare" scenario* ](https://aka.ms/liftandshiftwithcontainersebook) è importante per le applicazioni legacy che sono stati originariamente sviluppate con .NET Framework tradizionale, quali Web Form ASP.NET, MVC web App o WCF (containerizing Servizi Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="1cb99-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1cb99-123">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1cb99-123">Additional resources</span></span>

-   <span data-ttu-id="1cb99-124">**e-book: modernizzare le applicazioni .NET Framework esistenti e i contenitori di Windows Azure**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="1cb99-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="1cb99-125">**App di esempio: moderna del App web ASP.NET legacy usando i contenitori di Windows**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="1cb99-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="1cb99-126">[Precedente] [Avanti] (net core-contenitore scenarios.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="1cb99-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
