---
title: Compilazione di immagini Docker per .NET Core
description: Informazioni sulle immagini Docker e su .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f539efe15ce68a77890538430a170da64ff325e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="34731-103">Compilazione di immagini Docker per applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="34731-103">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="34731-104">Questa esercitazione è incentrata su come usare .NET Core in Docker.</span><span class="sxs-lookup"><span data-stu-id="34731-104">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="34731-105">Vengono prima di tutto presentati le diverse immagini Docker offerte e gestite da Microsoft e i casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="34731-105">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="34731-106">Verranno poi descritte le procedure per compilare un'app di ASP.NET Core e inserirla in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="34731-106">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="34731-107">Nel corso di questa esercitazione verranno illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="34731-107">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="34731-108">Informazioni sulle immagini Docker per Microsoft .NET Core</span><span class="sxs-lookup"><span data-stu-id="34731-108">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="34731-109">Ottenere un'app di esempio ASP.NET Core da inserire in un contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="34731-109">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="34731-110">Eseguire localmente l'app di esempio ASP.NET</span><span class="sxs-lookup"><span data-stu-id="34731-110">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="34731-111">Compilare ed eseguire l'esempio con Docker per i contenitori Linux</span><span class="sxs-lookup"><span data-stu-id="34731-111">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="34731-112">Compilare ed eseguire l'esempio con Docker per i contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="34731-112">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="34731-113">Ottimizzazioni delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="34731-113">Docker Image Optimizations</span></span>

<span data-ttu-id="34731-114">Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione su tre scenari principali:</span><span class="sxs-lookup"><span data-stu-id="34731-114">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="34731-115">Immagini usate per sviluppare app .NET Core</span><span class="sxs-lookup"><span data-stu-id="34731-115">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="34731-116">Immagini usate per compilare app .NET Core</span><span class="sxs-lookup"><span data-stu-id="34731-116">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="34731-117">Immagini usate per eseguire app .NET Core</span><span class="sxs-lookup"><span data-stu-id="34731-117">Images used to run .NET Core apps</span></span>

<span data-ttu-id="34731-118">Perché tre immagini?</span><span class="sxs-lookup"><span data-stu-id="34731-118">Why three images?</span></span>
<span data-ttu-id="34731-119">Durante lo sviluppo, la compilazione e l'esecuzione di applicazioni nei contenitori, è necessario tenere conto di diverse priorità.</span><span class="sxs-lookup"><span data-stu-id="34731-119">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="34731-120">**Sviluppo:** le priorità sono la velocità di iterazione delle modifiche e la possibilità di eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="34731-120">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="34731-121">Le dimensioni dell'immagine non sono essenziali, mentre è importante la possibilità di apportare modifiche al codice e visualizzare rapidamente tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="34731-121">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="34731-122">**Compilazione:** questa immagine contiene tutti gli elementi necessari per compilare l'app, inclusi il compilatore ed eventuali altre dipendenze per ottimizzare i file binari.</span><span class="sxs-lookup"><span data-stu-id="34731-122">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="34731-123">L'immagine di compilazione viene usata per creare gli asset da includere in un'immagine di produzione.</span><span class="sxs-lookup"><span data-stu-id="34731-123">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="34731-124">Questa immagine verrà usata per l'integrazione continuativa o in un ambiente di compilazione.</span><span class="sxs-lookup"><span data-stu-id="34731-124">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="34731-125">Questo approccio consente a un agente di compilazione di compilare l'applicazione (con tutte le dipendenze necessarie) in un'istanza dell'immagine di compilazione.</span><span class="sxs-lookup"><span data-stu-id="34731-125">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="34731-126">Per l'agente di compilazione è necessario soltanto sapere come eseguire questa immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="34731-126">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="34731-127">**Produzione:** con quale velocità è possibile distribuire e avviare l'immagine?</span><span class="sxs-lookup"><span data-stu-id="34731-127">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="34731-128">Questa immagine ha dimensioni ridotte, quindi le prestazioni di rete dal registro Docker agli host Docker sono ottimizzate.</span><span class="sxs-lookup"><span data-stu-id="34731-128">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="34731-129">Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'esecuzione Docker e l'elaborazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="34731-129">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="34731-130">La compilazione dinamica del codice non è necessaria nel modello di Docker.</span><span class="sxs-lookup"><span data-stu-id="34731-130">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="34731-131">Il contenuto inserito in questa immagine sarà limitato ai file binari e al contenuto necessario per eseguire l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="34731-131">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="34731-132">Ad esempio, l'output `dotnet publish` contiene:</span><span class="sxs-lookup"><span data-stu-id="34731-132">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="34731-133">i file binari compilati</span><span class="sxs-lookup"><span data-stu-id="34731-133">the compiled binaries</span></span>
    * <span data-ttu-id="34731-134">i file con estensione js e css</span><span class="sxs-lookup"><span data-stu-id="34731-134">.js and .css files</span></span>


<span data-ttu-id="34731-135">Il motivo per includere l'output del comando `dotnet publish` nell'immagine di produzione è mantenere il più possibile ridotte le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="34731-135">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="34731-136">Alcune immagini .NET Core condividono i livelli tra tag diversi, quindi il download del tag più recente è un processo relativamente leggero.</span><span class="sxs-lookup"><span data-stu-id="34731-136">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="34731-137">Se è già disponibile una versione precedente nel computer in uso, questa architettura consente di ridurre lo spazio su disco necessario.</span><span class="sxs-lookup"><span data-stu-id="34731-137">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="34731-138">Quando più applicazioni usano immagini comuni nello stesso computer, la memoria viene condivisa tra le immagini comuni.</span><span class="sxs-lookup"><span data-stu-id="34731-138">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="34731-139">Le immagini devono essere uguali per essere condivise.</span><span class="sxs-lookup"><span data-stu-id="34731-139">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="34731-140">Variazioni delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="34731-140">Docker image variations</span></span>

<span data-ttu-id="34731-141">Per raggiungere gli obiettivi sopra descritti, in [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) sono disponibili varianti delle immagini.</span><span class="sxs-lookup"><span data-stu-id="34731-141">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="34731-142">`microsoft/dotnet:<version>-sdk` (`microsoft/dotnet:2.0.0-sdk`). Questa immagine contiene .NET Core SDK che include gli strumenti .NET Core e quelli dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="34731-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="34731-143">Questa immagine è mappata allo **scenario di sviluppo**.</span><span class="sxs-lookup"><span data-stu-id="34731-143">This image maps to the **development scenario**.</span></span> <span data-ttu-id="34731-144">Usare questa immagine per operazioni locali di sviluppo, debug e testing unità.</span><span class="sxs-lookup"><span data-stu-id="34731-144">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="34731-145">Questa immagine può essere usata anche per gli scenari di **compilazione**.</span><span class="sxs-lookup"><span data-stu-id="34731-145">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="34731-146">L'uso di `microsoft/dotnet:sdk` consente di ottenere sempre la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="34731-146">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="34731-147">In caso di dubbi sulle effettive esigenze, è possibile usare l'immagine `microsoft/dotnet:<version>-sdk`.</span><span class="sxs-lookup"><span data-stu-id="34731-147">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="34731-148">In quanto immagine "de facto", è progettata per l'uso come contenitore provvisorio (montare il codice sorgente e avviare il contenitore per avviare l'app) e come immagine di base da cui compilare altre immagini.</span><span class="sxs-lookup"><span data-stu-id="34731-148">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="34731-149">`microsoft/dotnet:<version>-runtime`: questa immagine contiene .NET Core (runtime e librerie) ed è ottimizzata per l'esecuzione di app .NET Core in **produzione**.</span><span class="sxs-lookup"><span data-stu-id="34731-149">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="34731-150">Immagini alternative</span><span class="sxs-lookup"><span data-stu-id="34731-150">Alternative images</span></span>

<span data-ttu-id="34731-151">Oltre agli scenari ottimizzati di sviluppo, compilazione e produzione, Microsoft fornisce immagini aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="34731-151">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="34731-152">`microsoft/dotnet:<version>-runtime-deps`: l'immagine **runtime-deps** contiene il sistema operativo con tutte le dipendenze native richieste da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="34731-152">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="34731-153">Questa immagine è per [applicazioni indipendenti](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="34731-153">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="34731-154">Versioni più recenti di ciascuna variante:</span><span class="sxs-lookup"><span data-stu-id="34731-154">Latest versions of each variant:</span></span>

* <span data-ttu-id="34731-155">`microsoft/dotnet` o `microsoft/dotnet:latest` (alias per l'immagine SDK)</span><span class="sxs-lookup"><span data-stu-id="34731-155">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="34731-156">Esempi da esplorare</span><span class="sxs-lookup"><span data-stu-id="34731-156">Samples to explore</span></span>

* <span data-ttu-id="34731-157">[Questo esempio di Docker per ASP.NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) illustra un modello di procedura consigliata per la compilazione di immagini Docker per app ASP.NET Core per la produzione.</span><span class="sxs-lookup"><span data-stu-id="34731-157">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="34731-158">L'esempio usa contenitori sia Linux che Windows.</span><span class="sxs-lookup"><span data-stu-id="34731-158">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="34731-159">Questo esempio di Docker per .NET Core illustra un modello di procedura consigliata per la [compilazione di immagini Docker per app .NET Core per la produzione](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod).</span><span class="sxs-lookup"><span data-stu-id="34731-159">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="34731-160">La prima app Docker ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="34731-160">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="34731-161">In questa esercitazione verrà usata l'applicazione di esempio Docker per ASP.NET Core per l'app da inserire in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="34731-161">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="34731-162">Questa applicazione di esempio Docker per ASP.NET Core illustra un modello di procedura consigliata per la compilazione di immagini Docker per app ASP.NET Core per la produzione.</span><span class="sxs-lookup"><span data-stu-id="34731-162">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="34731-163">L'esempio usa contenitori sia Linux che Windows.</span><span class="sxs-lookup"><span data-stu-id="34731-163">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="34731-164">Il Dockerfile di esempio crea un'immagine Docker dell'applicazione ASP.NET Core in base all'immagine di base Docker di ASP.NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="34731-164">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="34731-165">Usa la [funzionalità di compilazione in più fasi di Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) per:</span><span class="sxs-lookup"><span data-stu-id="34731-165">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="34731-166">Compilare l'esempio in un contenitore in base all'immagine di base Docker di compilazione per ASP.NET Core **più grande**</span><span class="sxs-lookup"><span data-stu-id="34731-166">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="34731-167">Copia il risultato finale di compilazione in un'immagine Docker in base all'immagine di base di runtime Docker per ASP.NET Core **più piccola**</span><span class="sxs-lookup"><span data-stu-id="34731-167">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="34731-168">L'immagine di compilazione contiene gli strumenti necessari per compilare applicazioni, diversamente dall'immagine di runtime.</span><span class="sxs-lookup"><span data-stu-id="34731-168">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="34731-169">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="34731-169">Prerequisites</span></span>

<span data-ttu-id="34731-170">Per compilare ed eseguire, installare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="34731-170">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="34731-171">.NET Core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="34731-171">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="34731-172">Installare [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="34731-172">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="34731-173">Installare l'editor del codice preferito, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="34731-173">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="34731-174">È necessario installare un editor del codice?</span><span class="sxs-lookup"><span data-stu-id="34731-174">Need to install a code editor?</span></span> <span data-ttu-id="34731-175">Provare [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="34731-175">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="34731-176">Installazione del client di Docker</span><span class="sxs-lookup"><span data-stu-id="34731-176">Installing Docker Client</span></span>

<span data-ttu-id="34731-177">Installare [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) o una versione successiva del client di Docker.</span><span class="sxs-lookup"><span data-stu-id="34731-177">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="34731-178">Il client di Docker può essere installato in:</span><span class="sxs-lookup"><span data-stu-id="34731-178">The Docker client can be installed in:</span></span>

* <span data-ttu-id="34731-179">Distribuzioni di Linux</span><span class="sxs-lookup"><span data-stu-id="34731-179">Linux distributions</span></span>

   * [<span data-ttu-id="34731-180">CentOS</span><span class="sxs-lookup"><span data-stu-id="34731-180">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="34731-181">Debian</span><span class="sxs-lookup"><span data-stu-id="34731-181">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="34731-182">Fedora</span><span class="sxs-lookup"><span data-stu-id="34731-182">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="34731-183">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="34731-183">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="34731-184">macOS</span><span class="sxs-lookup"><span data-stu-id="34731-184">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="34731-185">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="34731-185">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="34731-186">Installazione di Git per il repository degli esempi</span><span class="sxs-lookup"><span data-stu-id="34731-186">Installing Git for sample repository</span></span>

* <span data-ttu-id="34731-187">Installare [Git](https://git-scm.com/download) se si desidera clonare il repository.</span><span class="sxs-lookup"><span data-stu-id="34731-187">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="34731-188">Ottenere l'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="34731-188">Getting the sample application</span></span>

<span data-ttu-id="34731-189">Il modo più semplice per ottenere l'esempio è clonando il [repository degli esempi](https://github.com/dotnet/dotnet-docker-samples) con Git, seguendo queste istruzioni:</span><span class="sxs-lookup"><span data-stu-id="34731-189">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="34731-190">È anche possibile scaricare il repository (che ha dimensioni contenute) come file ZIP dal repository degli esempi Docker di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="34731-190">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="34731-191">Eseguire localmente l'app ASP.NET</span><span class="sxs-lookup"><span data-stu-id="34731-191">Run the ASP.NET app locally</span></span>

<span data-ttu-id="34731-192">Come punto di riferimento, prima di inserire l'applicazione nei contenitori, eseguirla localmente.</span><span class="sxs-lookup"><span data-stu-id="34731-192">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="34731-193">È possibile compilare ed eseguire l'applicazione in locale con .NET Core 2.0 SDK tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):</span><span class="sxs-lookup"><span data-stu-id="34731-193">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="34731-194">Dopo l'avvio dell'applicazione, visitare **http://localhost:5000** nel Web browser.</span><span class="sxs-lookup"><span data-stu-id="34731-194">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="34731-195">Compilare ed eseguire l'esempio con Docker per i contenitori Linux</span><span class="sxs-lookup"><span data-stu-id="34731-195">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="34731-196">È possibile compilare ed eseguire l'esempio in Docker usando contenitori Linux tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):</span><span class="sxs-lookup"><span data-stu-id="34731-196">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="34731-197">L'argomento `docker run` '-p' mappa la porta 5000 nel computer locale alla porta 80 nel contenitore (il formato per il mapping delle porte è `host:container`).</span><span class="sxs-lookup"><span data-stu-id="34731-197">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="34731-198">Per altre informazioni, vedere le informazioni di riferimento su [docker run](https://docs.docker.com/engine/reference/commandline/exec/) per i parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="34731-198">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="34731-199">Dopo l'avvio dell'applicazione, visitare **http://localhost:5000** nel Web browser.</span><span class="sxs-lookup"><span data-stu-id="34731-199">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="34731-200">Compilare ed eseguire l'esempio con Docker per i contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="34731-200">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="34731-201">È possibile compilare ed eseguire l'esempio in Docker usando contenitori Windows tramite i comandi seguenti (le istruzioni presuppongono la radice del repository):</span><span class="sxs-lookup"><span data-stu-id="34731-201">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="34731-202">È necessario passare direttamente all'**indirizzo IP del contenitore** (in contrapposizione a http://localhost)) nel browser quando si usano i contenitori Windows.</span><span class="sxs-lookup"><span data-stu-id="34731-202">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="34731-203">È possibile ottenere l'indirizzo IP del contenitore con i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="34731-203">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="34731-204">Aprire un altro prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="34731-204">Open up another command prompt.</span></span>
* <span data-ttu-id="34731-205">Eseguire `docker ps` per visualizzare i contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34731-205">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="34731-206">Deve essere presente il contenitore "aspnetcore_sample".</span><span class="sxs-lookup"><span data-stu-id="34731-206">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="34731-207">Eseguire `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="34731-207">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="34731-208">Copiare l'indirizzo IP del contenitore e incollarlo nel browser (ad esempio, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="34731-208">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="34731-209">Il comando docker exec supporta l'identificazione dei contenitori in base al nome o all'hash.</span><span class="sxs-lookup"><span data-stu-id="34731-209">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="34731-210">In questo esempio, viene usato il nome (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="34731-210">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="34731-211">Vedere l'esempio seguente su come ottenere l'indirizzo IP di un contenitore Windows in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34731-211">See the following example of how to get the IP address of a running Windows container.</span></span>

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

> [!NOTE]
> <span data-ttu-id="34731-212">Il comando docker exec esegue un nuovo comando in un contenitore in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34731-212">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="34731-213">Per altre informazioni, vedere le informazioni di riferimento su [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) per i parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="34731-213">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="34731-214">È possibile creare un'applicazione pronta per la distribuzione nell'ambiente di produzione in locale usando il comando [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="34731-214">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!NOTE]
> <span data-ttu-id="34731-215">L'argomento - c Release compila l'applicazione in modalità di versione (l'impostazione predefinita è la modalità di debug).</span><span class="sxs-lookup"><span data-stu-id="34731-215">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="34731-216">Per altre informazioni, vedere le informazioni di riferimento su [dotnet run](../tools/dotnet-run.md) per i parametri della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="34731-216">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="34731-217">È possibile eseguire l'applicazione in **Windows** usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="34731-217">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="34731-218">È possibile eseguire l'applicazione in **Linux** o **macOS** usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="34731-218">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="34731-219">Immagini Docker usate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="34731-219">Docker Images used in this sample</span></span>

<span data-ttu-id="34731-220">In questo esempio vengono usate le immagini Docker seguenti</span><span class="sxs-lookup"><span data-stu-id="34731-220">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="34731-221">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="34731-221">Congratulations!</span></span> <span data-ttu-id="34731-222">Sono state eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="34731-222">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="34731-223">Raccolta di informazioni sulle immagini Docker per Microsoft .NET Core</span><span class="sxs-lookup"><span data-stu-id="34731-223">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="34731-224">Recupero di un'app di esempio ASP.NET Core da inserire in un contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="34731-224">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="34731-225">Esecuzione locale dell'app di esempio ASP.NET</span><span class="sxs-lookup"><span data-stu-id="34731-225">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="34731-226">Compilazione ed esecuzione dell'esempio con Docker per i contenitori Linux</span><span class="sxs-lookup"><span data-stu-id="34731-226">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="34731-227">Compilazione ed esecuzione dell'esempio con Docker per i contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="34731-227">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="34731-228">**Passaggi successivi**</span><span class="sxs-lookup"><span data-stu-id="34731-228">**Next Steps**</span></span>

<span data-ttu-id="34731-229">Ecco alcuni dei possibili argomenti con cui proseguire:</span><span class="sxs-lookup"><span data-stu-id="34731-229">Here are some next steps you can take:</span></span>

* <span data-ttu-id="34731-230">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Uso degli strumenti Docker per Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="34731-230">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>
* <span data-ttu-id="34731-231">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Distribuzione di immagini Docker dal Registro contenitori di Azure a Istanze di contenitore di Azure)</span><span class="sxs-lookup"><span data-stu-id="34731-231">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>
* <span data-ttu-id="34731-232">[Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) (Debug con Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="34731-232">[Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)</span></span> 
* <span data-ttu-id="34731-233">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Informazioni su Visual Studio per Mac, contenitori e codice senza server nel cloud)</span><span class="sxs-lookup"><span data-stu-id="34731-233">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)</span></span>
* <span data-ttu-id="34731-234">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Lab introduttivo per Docker e Visual Studio per Mac)</span><span class="sxs-lookup"><span data-stu-id="34731-234">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

> [!NOTE]
> <span data-ttu-id="34731-235">Se non si ha una sottoscrizione di Azure, [iscriversi subito](https://azure.microsoft.com/free/?b=16.48) per ottenere un account gratuito di 30 giorni e 200 dollari in crediti di Azure per poter provare una combinazione dei servizi di Azure.</span><span class="sxs-lookup"><span data-stu-id="34731-235">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
