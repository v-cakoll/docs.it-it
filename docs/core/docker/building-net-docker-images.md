---
title: Compilazione di immagini Docker per .NET Core
description: Informazioni sulle immagini Docker e su .NET Core
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="943c0-104">Compilazione di immagini Docker per applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="943c0-104">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="943c0-105">In questa esercitazione, l'attenzione su come usare .NET Core in Docker.</span><span class="sxs-lookup"><span data-stu-id="943c0-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="943c0-106">In primo luogo, è esplorare le immagini di Docker diverse offerte e gestiti da Microsoft e casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="943c0-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="943c0-107">È quindi come compilare e dockerize un'app di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="943c0-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="943c0-108">Nel corso di questa esercitazione, si apprenderà:</span><span class="sxs-lookup"><span data-stu-id="943c0-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="943c0-109">Informazioni sulle immagini di Microsoft .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="943c0-110">Ottenere un ASP.NET Core app di esempio per Dockerize</span><span class="sxs-lookup"><span data-stu-id="943c0-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="943c0-111">Eseguire localmente l'app di esempio ASP.NET</span><span class="sxs-lookup"><span data-stu-id="943c0-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="943c0-112">Compilare ed eseguire l'esempio con Docker per i contenitori di Linux</span><span class="sxs-lookup"><span data-stu-id="943c0-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="943c0-113">Compilare ed eseguire l'esempio con i contenitori di Docker per Windows</span><span class="sxs-lookup"><span data-stu-id="943c0-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="943c0-114">Ottimizzazioni delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-114">Docker Image Optimizations</span></span>

<span data-ttu-id="943c0-115">Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione su tre scenari principali:</span><span class="sxs-lookup"><span data-stu-id="943c0-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="943c0-116">Immagini usate per sviluppare app .NET Core</span><span class="sxs-lookup"><span data-stu-id="943c0-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="943c0-117">Immagini usate per compilare app .NET Core</span><span class="sxs-lookup"><span data-stu-id="943c0-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="943c0-118">Immagini usate per eseguire app .NET Core</span><span class="sxs-lookup"><span data-stu-id="943c0-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="943c0-119">Perché tre immagini?</span><span class="sxs-lookup"><span data-stu-id="943c0-119">Why three images?</span></span>
<span data-ttu-id="943c0-120">Durante lo sviluppo, compilazione e l'esecuzione di applicazioni nei contenitori, abbiamo diverse priorità.</span><span class="sxs-lookup"><span data-stu-id="943c0-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="943c0-121">**Sviluppo:** la priorità è incentrata sulla scorrere rapidamente le modifiche e la possibilità di eseguire il debug delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="943c0-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="943c0-122">Le dimensioni dell'immagine non sono importante, piuttosto possibile si apportano modifiche al codice e visualizzarli rapidamente?</span><span class="sxs-lookup"><span data-stu-id="943c0-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="943c0-123">**Compilazione:** questa immagine contiene tutti gli elementi necessari per compilare l'app, che include il compilatore e delle dipendenze per ottimizzare i file binari.</span><span class="sxs-lookup"><span data-stu-id="943c0-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="943c0-124">Utilizzare l'immagine di compilazione per creare asset di che inserire in un'immagine di produzione.</span><span class="sxs-lookup"><span data-stu-id="943c0-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="943c0-125">Viene utilizzata l'immagine di compilazione per l'integrazione continua o in un ambiente di compilazione.</span><span class="sxs-lookup"><span data-stu-id="943c0-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="943c0-126">Questo approccio consente a un agente di compilazione compilare e compilare l'applicazione (con tutte le dipendenze necessarie) in un'istanza di immagine di compilazione.</span><span class="sxs-lookup"><span data-stu-id="943c0-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="943c0-127">Per l'agente di compilazione è necessario soltanto sapere come eseguire questa immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="943c0-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="943c0-128">**Produzione:** la velocità con cui è possibile distribuire e avviare l'immagine?</span><span class="sxs-lookup"><span data-stu-id="943c0-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="943c0-129">Questa immagine è piccola, pertanto le prestazioni di rete dal Registro di sistema Docker per gli host Docker sono ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="943c0-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="943c0-130">Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'esecuzione Docker e l'elaborazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="943c0-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="943c0-131">Compilazione dinamica del codice non è necessaria nel modello di Docker.</span><span class="sxs-lookup"><span data-stu-id="943c0-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="943c0-132">Il contenuto inserito in questa immagine sarà limitato ai file binari e al contenuto necessario per eseguire l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="943c0-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="943c0-133">Ad esempio, il `dotnet publish` output contiene:</span><span class="sxs-lookup"><span data-stu-id="943c0-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="943c0-134">i file binari compilati</span><span class="sxs-lookup"><span data-stu-id="943c0-134">the compiled binaries</span></span>
    * <span data-ttu-id="943c0-135">file con estensione js e CSS</span><span class="sxs-lookup"><span data-stu-id="943c0-135">.js and .css files</span></span>


<span data-ttu-id="943c0-136">Il motivo per includere il `dotnet publish` output del comando in un'immagine di produzione è quello di mantenere il ' dimensioni al minimo.</span><span class="sxs-lookup"><span data-stu-id="943c0-136">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="943c0-137">Alcune immagini .NET Core condividono livelli tra tag diversi, pertanto il tag più recente di download è un processo relativamente semplice.</span><span class="sxs-lookup"><span data-stu-id="943c0-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="943c0-138">Se si dispone di una versione precedente del computer, questa architettura consente di ridurre lo spazio su disco necessaria.</span><span class="sxs-lookup"><span data-stu-id="943c0-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="943c0-139">Quando più applicazioni utilizzano immagini comuni nello stesso computer, la memoria è condivisa tra le immagini più comuni.</span><span class="sxs-lookup"><span data-stu-id="943c0-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="943c0-140">Le immagini devono essere uguali a essere condivisi.</span><span class="sxs-lookup"><span data-stu-id="943c0-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="943c0-141">Variazioni delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-141">Docker image variations</span></span>

<span data-ttu-id="943c0-142">Per ottenere gli obiettivi di cui sopra, forniamo varianti di immagine in [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="943c0-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="943c0-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Questa immagine contiene .NET Core SDK, che include .NET Core e gli strumenti della riga di comando (CLI).</span><span class="sxs-lookup"><span data-stu-id="943c0-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="943c0-144">Questa immagine è mappata allo **scenario di sviluppo**.</span><span class="sxs-lookup"><span data-stu-id="943c0-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="943c0-145">Utilizzare questa immagine per lo sviluppo locale e il debug di unit test.</span><span class="sxs-lookup"><span data-stu-id="943c0-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="943c0-146">Questa immagine può essere usata anche per gli scenari di **compilazione**.</span><span class="sxs-lookup"><span data-stu-id="943c0-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="943c0-147">Utilizzando `microsoft/dotnet:sdk` fornisce sempre la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="943c0-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="943c0-148">Se non si conosce le proprie esigenze, si desidera utilizzare il `microsoft/dotnet:<version>-sdk` immagine.</span><span class="sxs-lookup"><span data-stu-id="943c0-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="943c0-149">Come l'immagine "fatto", è progettato per essere utilizzato come un'istruzione throw contenitore di stoccaggio montare il codice sorgente e avviare il contenitore per avviare l'app e come immagine di base per altre immagini da compilare.</span><span class="sxs-lookup"><span data-stu-id="943c0-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="943c0-150">`microsoft/dotnet:<version>-runtime`: Questa immagine contiene .NET Core (runtime e librerie) ed è ottimizzata per l'esecuzione di App .NET Core in **produzione**.</span><span class="sxs-lookup"><span data-stu-id="943c0-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="943c0-151">Immagini alternative</span><span class="sxs-lookup"><span data-stu-id="943c0-151">Alternative images</span></span>

<span data-ttu-id="943c0-152">Oltre agli scenari ottimizzati di sviluppo, compilazione e produzione, Microsoft fornisce immagini aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="943c0-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="943c0-153">`microsoft/dotnet:<version>-runtime-deps`: il **runtime deps** immagine contiene il sistema operativo con tutte le dipendenze native necessari per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="943c0-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="943c0-154">Questa immagine è per [applicazioni indipendente](https://docs.microsoft.com/dotnet/core/deploying/index).</span><span class="sxs-lookup"><span data-stu-id="943c0-154">This image is for [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index).</span></span>

<span data-ttu-id="943c0-155">Versioni più recenti di ciascuna variante:</span><span class="sxs-lookup"><span data-stu-id="943c0-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="943c0-156">`microsoft/dotnet`o `microsoft/dotnet:latest` (alias per l'immagine SDK)</span><span class="sxs-lookup"><span data-stu-id="943c0-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="943c0-157">Esempi per l'esplorazione</span><span class="sxs-lookup"><span data-stu-id="943c0-157">Samples to explore</span></span>

* <span data-ttu-id="943c0-158">[In questo esempio di ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) viene illustrato un modello migliore di procedure consigliate per la creazione di immagini Docker per ASP.NET Core App per la produzione.</span><span class="sxs-lookup"><span data-stu-id="943c0-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="943c0-159">L'esempio funziona con contenitori di Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="943c0-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="943c0-160">Questo esempio di .NET Core Docker viene illustrato un modello prassi migliori per [la creazione di immagini Docker per le applicazioni .NET Core per la produzione.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="943c0-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="943c0-161">La prima app di ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-161">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="943c0-162">Per questa esercitazione consente di utilizzare un'applicazione di esempio ASP.NET Core Docker per l'app a cui che si desidera dockerize.</span><span class="sxs-lookup"><span data-stu-id="943c0-162">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="943c0-163">Questa applicazione di esempio ASP.NET Core Docker viene illustrato un modello prassi migliori per la creazione di immagini Docker per ASP.NET Core App per la produzione.</span><span class="sxs-lookup"><span data-stu-id="943c0-163">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="943c0-164">L'esempio funziona con contenitori di Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="943c0-164">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="943c0-165">L'esempio Dockerfile crea un'immagine di Docker dell'applicazione ASP.NET Core in base di fuori dell'immagine di base di ASP.NET Core Runtime Docker.</span><span class="sxs-lookup"><span data-stu-id="943c0-165">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="943c0-166">Usa il [funzionalità di compilazione in più fasi Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) per:</span><span class="sxs-lookup"><span data-stu-id="943c0-166">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="943c0-167">compilare l'esempio in un contenitore in base il **maggiore** immagine di base di ASP.NET Core compilazione Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-167">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="943c0-168">Copia il risultato finale di compilazione in un'immagine di Docker in base il **più piccoli** immagine di base del Runtime di ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-168">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!Note]
> <span data-ttu-id="943c0-169">L'immagine di compilazione contiene strumenti necessari per compilare applicazioni, mentre l'immagine di runtime non.</span><span class="sxs-lookup"><span data-stu-id="943c0-169">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="943c0-170">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="943c0-170">Prerequisites</span></span>

<span data-ttu-id="943c0-171">Per compilare ed eseguire, installare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="943c0-171">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="943c0-172">.NET core SDK 2.0</span><span class="sxs-lookup"><span data-stu-id="943c0-172">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="943c0-173">Installare [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="943c0-173">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="943c0-174">Installare l'editor di codice preferito, se hai già fatto.</span><span class="sxs-lookup"><span data-stu-id="943c0-174">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="943c0-175">È necessario installare un editor di codice?</span><span class="sxs-lookup"><span data-stu-id="943c0-175">Need to install a code editor?</span></span> <span data-ttu-id="943c0-176">Provare a [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="943c0-176">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="943c0-177">L'installazione Client di Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-177">Installing Docker Client</span></span>

<span data-ttu-id="943c0-178">Installare [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) o versione successiva del client Docker.</span><span class="sxs-lookup"><span data-stu-id="943c0-178">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="943c0-179">Il client Docker può essere installato in:</span><span class="sxs-lookup"><span data-stu-id="943c0-179">The Docker client can be installed in:</span></span>

* <span data-ttu-id="943c0-180">Distribuzioni di Linux</span><span class="sxs-lookup"><span data-stu-id="943c0-180">Linux distributions</span></span>

   * [<span data-ttu-id="943c0-181">CentOS</span><span class="sxs-lookup"><span data-stu-id="943c0-181">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="943c0-182">Debian</span><span class="sxs-lookup"><span data-stu-id="943c0-182">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="943c0-183">Fedora</span><span class="sxs-lookup"><span data-stu-id="943c0-183">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="943c0-184">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="943c0-184">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="943c0-185">macOS</span><span class="sxs-lookup"><span data-stu-id="943c0-185">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="943c0-186">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="943c0-186">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="943c0-187">Installare Git per il repository di esempio</span><span class="sxs-lookup"><span data-stu-id="943c0-187">Installing Git for sample repository</span></span>

* <span data-ttu-id="943c0-188">Installare [git](https://git-scm.com/download) se si desidera clonare il repository.</span><span class="sxs-lookup"><span data-stu-id="943c0-188">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="943c0-189">L'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="943c0-189">Getting the sample application</span></span>

<span data-ttu-id="943c0-190">È il modo più semplice per ottenere il codice di esempio clonando la [repository di esempi](https://github.com/dotnet/dotnet-docker-samples) con git, seguendo le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="943c0-190">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="943c0-191">È anche possibile scaricare il repository (è piccolo) come un file zip dal repository di esempi di .NET Core Docker.</span><span class="sxs-lookup"><span data-stu-id="943c0-191">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="943c0-192">Eseguire localmente l'app ASP.NET</span><span class="sxs-lookup"><span data-stu-id="943c0-192">Run the ASP.NET app locally</span></span>

<span data-ttu-id="943c0-193">Come punto di riferimento, prima di inserire l'applicazione nei contenitori, eseguirla localmente.</span><span class="sxs-lookup"><span data-stu-id="943c0-193">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="943c0-194">È possibile compilare ed eseguire l'applicazione localmente con .NET Core 2.0 SDK tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):</span><span class="sxs-lookup"><span data-stu-id="943c0-194">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="943c0-195">Dopo l'avvio dell'applicazione, visitare **indirizzo http://localhost:5000/** nel web browser.</span><span class="sxs-lookup"><span data-stu-id="943c0-195">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="943c0-196">Compilare ed eseguire l'esempio con Docker per i contenitori di Linux</span><span class="sxs-lookup"><span data-stu-id="943c0-196">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="943c0-197">È possibile compilare ed eseguire l'esempio in Docker usando i contenitori di Linux usando i comandi seguenti (le istruzioni presuppongono la radice del repository):</span><span class="sxs-lookup"><span data-stu-id="943c0-197">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] <span data-ttu-id="943c0-198">Il `docker run` '-p' argomento mappe porta 5000 sul computer locale alla porta 80 del contenitore (il modulo di mapping di porta è `host:container`).</span><span class="sxs-lookup"><span data-stu-id="943c0-198">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="943c0-199">Per ulteriori informazioni, vedere il [docker eseguire](https://docs.docker.com/engine/reference/commandline/exec/) riferimento ai parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="943c0-199">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="943c0-200">Dopo l'avvio dell'applicazione, visitare **indirizzo http://localhost:5000/** nel web browser.</span><span class="sxs-lookup"><span data-stu-id="943c0-200">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="943c0-201">Compilare ed eseguire l'esempio con i contenitori di Docker per Windows</span><span class="sxs-lookup"><span data-stu-id="943c0-201">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="943c0-202">È possibile compilare ed eseguire l'esempio in Docker usando i contenitori di Windows usando i comandi seguenti (le istruzioni presuppongono la radice del repository):</span><span class="sxs-lookup"><span data-stu-id="943c0-202">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="943c0-203">È necessario passare al **indirizzo IP contenitore** (in contrapposizione a http://localhost) nel browser direttamente quando si usano i contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="943c0-203">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="943c0-204">È possibile ottenere l'indirizzo IP del contenitore con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="943c0-204">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="943c0-205">Aprire il prompt dei comandi di un altro.</span><span class="sxs-lookup"><span data-stu-id="943c0-205">Open up another command prompt.</span></span>
* <span data-ttu-id="943c0-206">Eseguire `docker ps` per visualizzare i contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="943c0-206">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="943c0-207">Il contenitore "aspnetcore_sample" deve essere presente.</span><span class="sxs-lookup"><span data-stu-id="943c0-207">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="943c0-208">Eseguire `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="943c0-208">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="943c0-209">L'indirizzo IP di contenitore di copiare e incollare nel browser (ad esempio, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="943c0-209">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!Note]
> <span data-ttu-id="943c0-210">Exec docker supporta i contenitori di identificazione con nome o hash.</span><span class="sxs-lookup"><span data-stu-id="943c0-210">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="943c0-211">In questo esempio, viene utilizzato il nome (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="943c0-211">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="943c0-212">Vedere l'esempio seguente di come ottenere l'indirizzo IP di un contenitore di Windows in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="943c0-212">See the following example of how to get the IP address of a running Windows container.</span></span>

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!Note]
> <span data-ttu-id="943c0-213">Exec docker viene eseguito un nuovo comando in un contenitore in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="943c0-213">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="943c0-214">Per ulteriori informazioni, vedere il [riferimento a docker exec](https://docs.docker.com/engine/reference/commandline/exec/) sui parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="943c0-214">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="943c0-215">È possibile creare un'applicazione che è possibile distribuire nell'ambiente di produzione in locale utilizzando il [dotnet pubblicare](../tools/dotnet-publish.md) comando.</span><span class="sxs-lookup"><span data-stu-id="943c0-215">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!Note]
> <span data-ttu-id="943c0-216">L'argomento di versione - c compila l'applicazione in modalità di rilascio (il valore predefinito è la modalità di debug).</span><span class="sxs-lookup"><span data-stu-id="943c0-216">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="943c0-217">Per ulteriori informazioni, vedere il [dotnet eseguire riferimento](../tools/dotnet-run.md) sui parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="943c0-217">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="943c0-218">È possibile eseguire l'applicazione in **Windows** usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="943c0-218">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="943c0-219">È possibile eseguire l'applicazione in **Linux** o **macOS** usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="943c0-219">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="943c0-220">Immagini docker usate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="943c0-220">Docker Images used in this sample</span></span>

<span data-ttu-id="943c0-221">Le immagini Docker seguenti vengono utilizzate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="943c0-221">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="943c0-222">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="943c0-222">Congratulations!</span></span> <span data-ttu-id="943c0-223">sono disponibili solo:</span><span class="sxs-lookup"><span data-stu-id="943c0-223">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="943c0-224">Sono fornite informazioni su Microsoft .NET Core Docker images</span><span class="sxs-lookup"><span data-stu-id="943c0-224">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="943c0-225">Ha ricevuto un ASP.NET Core app di esempio per Dockerize</span><span class="sxs-lookup"><span data-stu-id="943c0-225">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="943c0-226">È stata eseguita l'app di esempio ASP.NET localmente</span><span class="sxs-lookup"><span data-stu-id="943c0-226">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="943c0-227">Compilato ed eseguito il codice di esempio con Docker per i contenitori di Linux</span><span class="sxs-lookup"><span data-stu-id="943c0-227">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="943c0-228">Compilato ed eseguito il codice di esempio con i contenitori di Docker per Windows</span><span class="sxs-lookup"><span data-stu-id="943c0-228">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="943c0-229">**Passaggi successivi**</span><span class="sxs-lookup"><span data-stu-id="943c0-229">**Next Steps**</span></span>

<span data-ttu-id="943c0-230">Ecco alcuni dei passaggi da eseguire:</span><span class="sxs-lookup"><span data-stu-id="943c0-230">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="943c0-231">Utilizzo degli strumenti di Visual Studio Docker</span><span class="sxs-lookup"><span data-stu-id="943c0-231">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="943c0-232">Distribuzione di immagini Docker dal Registro di sistema contenitore di Azure per le istanze di contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="943c0-232">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="943c0-233">Il debug con codice di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="943c0-233">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="943c0-234">Recupero mani nel con Visual Studio per Mac, contenitori e senza codice nel cloud</span><span class="sxs-lookup"><span data-stu-id="943c0-234">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="943c0-235">Introduzione a Docker e Visual Studio per Mac Lab</span><span class="sxs-lookup"><span data-stu-id="943c0-235">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> <span data-ttu-id="943c0-236">Se non si dispone di una sottoscrizione di Azure, [Iscriviti oggi stesso](https://azure.microsoft.com/free/?b=16.48) per un account gratuito di 30 giorni e get 200 dollari di crediti di Azure per provare qualsiasi combinazione di servizi di Azure.</span><span class="sxs-lookup"><span data-stu-id="943c0-236">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
