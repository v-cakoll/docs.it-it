---
title: Compilazione di immagini Docker per .NET Core
description: Informazioni sulle immagini Docker e su .NET Core
keywords: .NET, .NET Core, Docker
author: spboyer
ms.author: shboyer
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.translationtype: HT
ms.sourcegitcommit: 9dc52f3a8c74c1aa575a83cb3bbd579b93fae9ae
ms.openlocfilehash: 0e679ffc22f52de5e2ce8194942efbb2f5299ee4
ms.contentlocale: it-it
ms.lasthandoff: 09/06/2017

---

#<a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="adf17-104">Compilazione di immagini Docker per applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="adf17-104">Building Docker Images for .NET Core Applications</span></span>

 
> [!IMPORTANT]
> <span data-ttu-id="adf17-105">È in corso il processo di aggiornamento per .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="adf17-105">We are in the process of updating for .NET Core 2.0.</span></span> <span data-ttu-id="adf17-106">Le istruzioni seguenti non sono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="adf17-106">The instructions below are out of date.</span></span> <span data-ttu-id="adf17-107">Ci scusiamo per qualsiasi inconveniente.</span><span class="sxs-lookup"><span data-stu-id="adf17-107">We sincerely apologize for any inconvenience!</span></span>

<span data-ttu-id="adf17-108">Per comprendere in che modo usare insieme .NET Core e Docker, è necessario prima conoscere le diverse immagini Docker disponibili e i casi in cui è opportuno usarle.</span><span class="sxs-lookup"><span data-stu-id="adf17-108">In order to get an understanding of how to use .NET Core and Docker together, we must first get to know the different Docker images that are offered and when is the right use case for them.</span></span> <span data-ttu-id="adf17-109">Di seguito verranno illustrate in modo dettagliato le variazioni offerte, verrà creata un'API Web ASP.NET Core, verranno usati gli strumenti Yeoman Docker per creare un contenitore sottoponibile a debug e verrà mostrato in che modo è possibile usare Visual Studio Code per l'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="adf17-109">Here we will walk through the variations offered, build an ASP.NET Core Web API, use the Yeoman Docker tools to create a debuggable container as well as peek at how Visual Studio Code can assist in the process.</span></span> 

## <a name="docker-image-optimizations"></a><span data-ttu-id="adf17-110">Ottimizzazioni delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="adf17-110">Docker Image Optimizations</span></span>

<span data-ttu-id="adf17-111">Quando si creano immagini Docker per gli sviluppatori, è opportuno concentrare l'attenzione su tre scenari principali:</span><span class="sxs-lookup"><span data-stu-id="adf17-111">When building Docker images for developers, we focused on three main scenarios:</span></span>

- <span data-ttu-id="adf17-112">Immagini usate per sviluppare app .NET Core</span><span class="sxs-lookup"><span data-stu-id="adf17-112">Images used to develop .NET Core apps</span></span>
- <span data-ttu-id="adf17-113">Immagini usate per compilare app .NET Core</span><span class="sxs-lookup"><span data-stu-id="adf17-113">Images used to build .NET Core apps</span></span>
- <span data-ttu-id="adf17-114">Immagini usate per eseguire app .NET Core</span><span class="sxs-lookup"><span data-stu-id="adf17-114">Images used to run .NET Core apps</span></span>

<span data-ttu-id="adf17-115">Perché tre immagini?</span><span class="sxs-lookup"><span data-stu-id="adf17-115">Why three images?</span></span>
<span data-ttu-id="adf17-116">Durante lo sviluppo, la compilazione e l'esecuzione di applicazioni nei contenitori, è necessario tenere conto di diverse priorità.</span><span class="sxs-lookup"><span data-stu-id="adf17-116">When developing, building and running containerized applications, we have different priorities.</span></span>
- <span data-ttu-id="adf17-117">**Sviluppo:** qual è la velocità di iterazione delle modifiche? È possibile eseguirne il debug?</span><span class="sxs-lookup"><span data-stu-id="adf17-117">**Development:**  How fast can you iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="adf17-118">Le dimensioni dell'immagine non sono essenziali, mentre è importante la possibilità di apportare modifiche al codice e visualizzare rapidamente tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="adf17-118">The size of the image isn't as important, rather can you make changes to your code and see them quickly.</span></span> <span data-ttu-id="adf17-119">Alcuni degli strumenti Microsoft, ad esempio [yo docker](https://aka.ms/yodocker), da usare in Visual Studio Code usano questa immagine durante la fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="adf17-119">Some of our tools, like [yo docker](https://aka.ms/yodocker) for use in Visual Studio Code use this image during development time.</span></span> 
- <span data-ttu-id="adf17-120">**Compilazione:** quali sono gli elementi necessari per compilare l'app?</span><span class="sxs-lookup"><span data-stu-id="adf17-120">**Build:** What's needed to compile your app.</span></span> <span data-ttu-id="adf17-121">Questi elementi includono il compilatore e qualsiasi altra dipendenza necessaria per ottimizzare i file binari.</span><span class="sxs-lookup"><span data-stu-id="adf17-121">This includes the compiler and any other dependencies to optimize the binaries.</span></span> <span data-ttu-id="adf17-122">Questa immagine non è quella che verrà distribuita, ma piuttosto un'immagine usata per compilare il contenuto inserito in un'immagine di produzione.</span><span class="sxs-lookup"><span data-stu-id="adf17-122">This image isn't the image you deploy, rather it's an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="adf17-123">Questa immagine verrà usata nell'integrazione continuativa o nell'ambiente di compilazione.</span><span class="sxs-lookup"><span data-stu-id="adf17-123">This image would be used in your continuous integration, or build environment.</span></span> <span data-ttu-id="adf17-124">Ad esempio, anziché installare le dipendenze direttamente in un agente di compilazione, quest'ultimo creerà un'istanza dell'immagine di compilazione per compilare l'applicazione contenuta nell'immagine stessa con tutte le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="adf17-124">For instance, rather than installing all the dependencies directly on a build agent, the build agent would instance a build image to compile the application with all the dependencies required to build the app contained within the image.</span></span> <span data-ttu-id="adf17-125">Per l'agente di compilazione è necessario soltanto sapere come eseguire questa immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="adf17-125">Your build agent only needs to know how to run this Docker image.</span></span> 
- <span data-ttu-id="adf17-126">**Produzione:** con quale velocità è possibile distribuire e avviare l'immagine?</span><span class="sxs-lookup"><span data-stu-id="adf17-126">**Production:** How fast you can deploy and start your image.</span></span> <span data-ttu-id="adf17-127">Questa immagine ha dimensioni ridotte, motivo per cui può passare rapidamente attraverso la rete dal registro Docker agli host Docker.</span><span class="sxs-lookup"><span data-stu-id="adf17-127">This image is small so it can quickly travel across the network from your Docker Registry to your Docker hosts.</span></span> <span data-ttu-id="adf17-128">Il contenuto è pronto per l'esecuzione, rendendo minimo l'intervallo tra l'esecuzione Docker e l'elaborazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="adf17-128">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="adf17-129">Nel modello Docker non modificabile non è necessaria la compilazione dinamica del codice.</span><span class="sxs-lookup"><span data-stu-id="adf17-129">In the immutable Docker model, there's no need for dynamic compilation of code.</span></span> <span data-ttu-id="adf17-130">Il contenuto inserito in questa immagine sarà limitato ai file binari e al contenuto necessario per eseguire l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="adf17-130">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span> <span data-ttu-id="adf17-131">ad esempio l'output pubblicato usando `dotnet publish` e contenente i file binari, le immagini e i file con estensione js e css compilati.</span><span class="sxs-lookup"><span data-stu-id="adf17-131">For example, the published output using `dotnet publish` which contains the compiled binaries, images, .js and .css files.</span></span> <span data-ttu-id="adf17-132">Nel corso del tempo si vedranno immagini contenenti pacchetti PreJit.</span><span class="sxs-lookup"><span data-stu-id="adf17-132">Over time, you'll see images that contain pre-jitted packages.</span></span>  

<span data-ttu-id="adf17-133">Anche se sono presenti più versioni dell'immagine .NET Core, tutte queste versioni condividono uno o più layer.</span><span class="sxs-lookup"><span data-stu-id="adf17-133">Though there are multiple versions of the .NET Core image, they all share one or more layers.</span></span> <span data-ttu-id="adf17-134">La quantità di spazio su disco necessaria per l'archiviazione o per il delta per effettuare il pull dal Registro di sistema è molto minore dell'insieme delle immagini, perché tutte le immagini condividono lo stesso layer di base e potenzialmente altri layer.</span><span class="sxs-lookup"><span data-stu-id="adf17-134">The amount of disk space needed to store or the delta to pull from your registry is much smaller than the whole because all of the images share the same base layer and potentially others.</span></span>  

## <a name="docker-image-variations"></a><span data-ttu-id="adf17-135">Variazioni delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="adf17-135">Docker image variations</span></span>

<span data-ttu-id="adf17-136">Per raggiungere gli obiettivi sopra descritti, in [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) sono disponibili varianti delle immagini.</span><span class="sxs-lookup"><span data-stu-id="adf17-136">To achieve the goals above, we provide image variants under [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

- <span data-ttu-id="adf17-137">`microsoft/dotnet:<version>-sdk` : ovvero **microsoft/dotnet:1.0.0-preview2-sdk**. Questa immagine contiene .NET Core SDK che include gli strumenti .NET Core e quelli dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="adf17-137">`microsoft/dotnet:<version>-sdk` : that is **microsoft/dotnet:1.0.0-preview2-sdk**, this image contains the .NET Core SDK which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="adf17-138">Questa immagine è mappata allo **scenario di sviluppo**.</span><span class="sxs-lookup"><span data-stu-id="adf17-138">This image maps to the **development scenario**.</span></span> <span data-ttu-id="adf17-139">Usare questa immagine per operazioni locali di sviluppo, debug e testing unità,</span><span class="sxs-lookup"><span data-stu-id="adf17-139">You would use this image for local development, debugging and unit testing.</span></span> <span data-ttu-id="adf17-140">ad esempio tutte le attività di sviluppo eseguite prima dell'archiviazione del codice.</span><span class="sxs-lookup"><span data-stu-id="adf17-140">For example, all the development you do, before you check in your code.</span></span> <span data-ttu-id="adf17-141">Questa immagine può essere usata anche per gli scenari di **compilazione**.</span><span class="sxs-lookup"><span data-stu-id="adf17-141">This image can also be used for your **build** scenarios.</span></span>

- <span data-ttu-id="adf17-142">`microsoft/dotnet:<version>-core` : ovvero **microsoft/dotnet:1.0.0-core**. Questa immagine esegue [applicazioni .NET Core portabili](../deploying/index.md) ed è ottimizzata per l'esecuzione dell'applicazione nella fase di **produzione**.</span><span class="sxs-lookup"><span data-stu-id="adf17-142">`microsoft/dotnet:<version>-core` : that is **microsoft/dotnet:1.0.0-core**, image which runs [portable .NET Core applications](../deploying/index.md) and it is optimized for running your application in **production**.</span></span> <span data-ttu-id="adf17-143">Non contiene l'SDK ed è finalizzata all'acquisizione dell'output ottimizzato di `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="adf17-143">It does not contain the SDK, and is meant to take the optimized output of `dotnet publish`.</span></span> <span data-ttu-id="adf17-144">Il runtime portabile è adatto agli scenari Docker di contenitore poiché l'esecuzione di più contenitori trae vantaggio dai layer di immagine condivisi.</span><span class="sxs-lookup"><span data-stu-id="adf17-144">The portable runtime is well suited for Docker container scenarios as running multiple containers benefit from shared image layers.</span></span>  

## <a name="alternative-images"></a><span data-ttu-id="adf17-145">Immagini alternative</span><span class="sxs-lookup"><span data-stu-id="adf17-145">Alternative images</span></span>

<span data-ttu-id="adf17-146">Oltre agli scenari ottimizzati di sviluppo, compilazione e produzione, Microsoft fornisce immagini aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="adf17-146">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

- <span data-ttu-id="adf17-147">`microsoft/dotnet:<version>-onbuild` : ovvero **microsoft/dotnet:1.0.0-preview2-onbuild**. Contiene trigger [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild).</span><span class="sxs-lookup"><span data-stu-id="adf17-147">`microsoft/dotnet:<version>-onbuild` : that is **microsoft/dotnet:1.0.0-preview2-onbuild**, contains [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) triggers.</span></span> <span data-ttu-id="adf17-148">La compilazione eseguirà il comando [COPY](https://docs.docker.com/engine/reference/builder/#/copy) sull'applicazione, eseguirà `dotnet restore` e creerà un'istruzione [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` per eseguire l'applicazione al momento dell'esecuzione dell'immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="adf17-148">The build will [COPY](https://docs.docker.com/engine/reference/builder/#/copy) your application, run `dotnet restore` and create an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` instruction to run the application when the Docker image is run.</span></span> <span data-ttu-id="adf17-149">Anche se non si tratta di un'immagine ottimizzata per la produzione, alcuni utenti possono trovarla utile per copiare semplicemente il codice sorgente in un'immagine ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="adf17-149">While not an optimized image for production, some may find it useful to simply copy their source code into an image and run it.</span></span> 

- <span data-ttu-id="adf17-150">`microsoft/dotnet:<version>-core-deps` : ovvero **microsoft/dotnet:1.0.0-core-deps**. Usare questa immagine, se si vogliono eseguire applicazioni autonome.</span><span class="sxs-lookup"><span data-stu-id="adf17-150">`microsoft/dotnet:<version>-core-deps` : that is **microsoft/dotnet:1.0.0-core-deps**, if you wish to run self-contained applications use this image.</span></span> <span data-ttu-id="adf17-151">Questa immagine contiene il sistema operativo con tutte le dipendenze native richieste da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="adf17-151">It contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="adf17-152">Può essere usata anche come immagine di base per compilazioni CoreFX o CoreCLR personalizzate.</span><span class="sxs-lookup"><span data-stu-id="adf17-152">This image can also be used as a base image for your own custom CoreFX or CoreCLR builds.</span></span> <span data-ttu-id="adf17-153">Mentre la variante **onbuild** è ottimizzata per inserire semplicemente il codice in un'immagine ed eseguirlo, questa immagine è ottimizzata per contenere soltanto le dipendenze del sistema operativo necessarie per l'esecuzione di app .NET Core per cui viene fornito anche il runtime di .NET.</span><span class="sxs-lookup"><span data-stu-id="adf17-153">While the **onbuild** variant is optimized to simply place your code in an image and run it, this image is optimized to have only the operating system dependencies required to run .NET Core apps that have the .NET runtime packaged with the application.</span></span> <span data-ttu-id="adf17-154">Questa immagine non è in genere ottimizzata per l'esecuzione di più contenitori .NET Core nello stesso host. Ciascuna immagine infatti include il runtime di .NET Core e di conseguenza la struttura multi-layer delle immagini non offrirà alcun vantaggio.</span><span class="sxs-lookup"><span data-stu-id="adf17-154">This image isn't generally optimized for running multiple .NET Core containers on the same host, as each image carries the .NET Core runtime within the application, and you will not benefit from image layering.</span></span>   

<span data-ttu-id="adf17-155">Versioni più recenti di ciascuna variante:</span><span class="sxs-lookup"><span data-stu-id="adf17-155">Latest versions of each variant:</span></span>

- <span data-ttu-id="adf17-156">`microsoft/dotnet` o `microsoft/dotnet:latest` (include l'SDK)</span><span class="sxs-lookup"><span data-stu-id="adf17-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (includes SDK)</span></span>
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

<span data-ttu-id="adf17-157">Di seguito è riportato un elenco delle immagini dopo un'operazione `docker pull <imagename>` in un computer di sviluppo per mostrare le diverse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="adf17-157">Here is a list of the images after a `docker pull <imagename>` on a development machine to show the various sizes.</span></span> <span data-ttu-id="adf17-158">Si noti che la variante di sviluppo/compilazione, `microsoft/dotnet:1.0.0-preview2-sdk`, ha dimensioni maggiori in quanto contiene l'SDK per lo sviluppo e la compilazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="adf17-158">Notice, the development/build variant, `microsoft/dotnet:1.0.0-preview2-sdk` is larger as it contains the SDK to develop and build your application.</span></span> <span data-ttu-id="adf17-159">La variante di produzione, `microsoft/dotnet:core`, ha dimensioni minori, in quanto contiene soltanto il runtime di NET Core.</span><span class="sxs-lookup"><span data-stu-id="adf17-159">The production variant, `microsoft/dotnet:core` is smaller, as it only contains the .NET Core runtime.</span></span> <span data-ttu-id="adf17-160">L'immagine minima utilizzabile in Linux, `core-deps`, ha dimensioni abbastanza ridotte. L'applicazione, tuttavia, dovrà eseguire una copia privata del runtime di .NET con tale immagine.</span><span class="sxs-lookup"><span data-stu-id="adf17-160">The minimal image capable of being used on Linux, `core-deps`, is quite smaller, however your application will need to copy a private copy of the .NET runtime with it.</span></span> <span data-ttu-id="adf17-161">Dal momento che i contenitori sono già barriere private per l'isolamento, quando si eseguono più contenitori basati su .NET tale ottimizzazione andrà perduta.</span><span class="sxs-lookup"><span data-stu-id="adf17-161">Since containers are already private isolation barriers, you will lose that optimization when running multiple dotnet based containers.</span></span> 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a><span data-ttu-id="adf17-162">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="adf17-162">Prerequisites</span></span>

<span data-ttu-id="adf17-163">Per la compilazione e l'esecuzione è necessario che nel computer siano installati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="adf17-163">To build and run, you'll need a few things installed:</span></span>

- [<span data-ttu-id="adf17-164">.NET Core</span><span class="sxs-lookup"><span data-stu-id="adf17-164">.NET Core</span></span>](http://dot.net)
- <span data-ttu-id="adf17-165">[Docker](https://www.docker.com/products/docker), per eseguire localmente i contenitori Docker</span><span class="sxs-lookup"><span data-stu-id="adf17-165">[Docker](https://www.docker.com/products/docker) to run your Docker containers locally</span></span>
- [<span data-ttu-id="adf17-166">Node.js</span><span class="sxs-lookup"><span data-stu-id="adf17-166">Node.js</span></span>](https://nodejs.org/)
- <span data-ttu-id="adf17-167">[Generatore Yeoman per ASP.NET](https://github.com/omnisharp/generator-aspnet), per creare l'applicazione API Web</span><span class="sxs-lookup"><span data-stu-id="adf17-167">[Yeoman generator for ASP.NET](https://github.com/omnisharp/generator-aspnet) for creating the Web API application</span></span>
- <span data-ttu-id="adf17-168">[Generatore Yeoman per Docker](http://aka.ms/yodocker), fornito da Microsoft</span><span class="sxs-lookup"><span data-stu-id="adf17-168">[Yeoman generator for Docker](http://aka.ms/yodocker) from Microsoft</span></span>

<span data-ttu-id="adf17-169">Installare i generatori Yeoman per ASP.NET Core e Docker usando npm</span><span class="sxs-lookup"><span data-stu-id="adf17-169">Install the Yeoman generators for ASP.NET Core and Docker using npm</span></span> 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> <span data-ttu-id="adf17-170">Questo esempio userà [Visual Studio Code](http://code.visualstudio.com) per l'editor.</span><span class="sxs-lookup"><span data-stu-id="adf17-170">This sample will be using [Visual Studio Code](http://code.visualstudio.com) for the editor.</span></span>

## <a name="creating-the-web-api-application"></a><span data-ttu-id="adf17-171">Creazione dell'applicazione API Web</span><span class="sxs-lookup"><span data-stu-id="adf17-171">Creating the Web API application</span></span>

<span data-ttu-id="adf17-172">Come punto di riferimento, prima di inserire l'applicazione nei contenitori, eseguirla localmente.</span><span class="sxs-lookup"><span data-stu-id="adf17-172">For a reference point, before we containerize the application, first run the application locally.</span></span> 

<span data-ttu-id="adf17-173">L'applicazione completata si trova nel repository [dotnet/docs su GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="adf17-173">The finished application is located in the [dotnet/docs repository on GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span></span> <span data-ttu-id="adf17-174">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="adf17-174">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="adf17-175">Creare una directory per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="adf17-175">Create a directory for your application.</span></span>

<span data-ttu-id="adf17-176">Aprire una sessione della riga di comando o terminal in tale directory e usare il generatore Yeoman ASP.NET digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="adf17-176">Open a command or terminal session in that directory and use the ASP.NET Yeoman generator by typing the following:</span></span>
```
yo aspnet
```

<span data-ttu-id="adf17-177">Selezionare l'**applicazione API Web**, digitare **api** come nome dell'app, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="adf17-177">Select **Web API Application** and type **api** for the name of the app and tap enter.</span></span>  <span data-ttu-id="adf17-178">Dopo che è stato eseguito lo scaffolding dell'applicazione, passare alla directory `/api` e ripristinare le dipendenze NuGet usando `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="adf17-178">Once the application is scaffolded, change to the `/api` directory and restore the NuGet dependencies using `dotnet restore`.</span></span>

```
cd api
dotnet restore
```

<span data-ttu-id="adf17-179">Testare l'applicazione usando `dotnet run` e i valori disponibili in **http://localhost:5000/api/values**</span><span class="sxs-lookup"><span data-stu-id="adf17-179">Test the application using `dotnet run` and browsing to **http://localhost:5000/api/values**</span></span>

```javascript
[
    "value1",
    "value2"
]
```

<span data-ttu-id="adf17-180">Usare `Ctrl+C` per arrestare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="adf17-180">Use `Ctrl+C` to stop the application.</span></span>

## <a name="adding-docker-support"></a><span data-ttu-id="adf17-181">Aggiunta del supporto per Docker</span><span class="sxs-lookup"><span data-stu-id="adf17-181">Adding Docker support</span></span>

<span data-ttu-id="adf17-182">Per aggiungere al progetto il supporto per Docker usare il generatore Yeoman fornito da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="adf17-182">Adding Docker support to the project is achieved using the Yeoman generator from Microsoft.</span></span> <span data-ttu-id="adf17-183">Questo generatore attualmente supporta progetti .NET Core, Node.js e Go mediante la creazione di un documento Dockerfile e di script che consentono di compilare ed eseguire progetti all'interno dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="adf17-183">It currently supports .NET Core, Node.js and Go projects by creating a Dockerfile and scripts that help build and run projects inside containers.</span></span> <span data-ttu-id="adf17-184">Vengono aggiunti anche specifici file Visual Studio Code (launch.json, tasks.json) per il debug dell'editor e il supporto del riquadro comandi.</span><span class="sxs-lookup"><span data-stu-id="adf17-184">Visual Studio Code specific files are also added (launch.json, tasks.json) for editor debugging and command palette support.</span></span>

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js
```

- <span data-ttu-id="adf17-185">Selezionare `.NET Core` come tipo di progetto</span><span class="sxs-lookup"><span data-stu-id="adf17-185">Select `.NET Core` as the project type</span></span>
- <span data-ttu-id="adf17-186">`rtm` per la versione di .NET Core</span><span class="sxs-lookup"><span data-stu-id="adf17-186">`rtm` for the version of .NET Core</span></span>
- <span data-ttu-id="adf17-187">`Y` il progetto usa un server Web</span><span class="sxs-lookup"><span data-stu-id="adf17-187">`Y` the project uses a web server</span></span>
- <span data-ttu-id="adf17-188">`5000` la porta su cui l'applicazione API Web è in ascolto (http://localhost:5000)</span><span class="sxs-lookup"><span data-stu-id="adf17-188">`5000` is the port the Web API application is listening on (http://localhost:5000)</span></span>
- <span data-ttu-id="adf17-189">`api` per il nome dell'immagine</span><span class="sxs-lookup"><span data-stu-id="adf17-189">`api` for the image name</span></span>
- <span data-ttu-id="adf17-190">`api` per il nome del servizio</span><span class="sxs-lookup"><span data-stu-id="adf17-190">`api` for the service name</span></span>
- <span data-ttu-id="adf17-191">`api` per il progetto di composizione</span><span class="sxs-lookup"><span data-stu-id="adf17-191">`api` for the compose project</span></span> 
- <span data-ttu-id="adf17-192">`Y` per sovrascrivere il documento Dockerfile corrente</span><span class="sxs-lookup"><span data-stu-id="adf17-192">`Y` to overwrite the current Dockerfile</span></span>

<span data-ttu-id="adf17-193">Quando il generatore è completo, al progetto vengono aggiunti i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="adf17-193">When the generator is complete, the following files are added to the project</span></span>

- <span data-ttu-id="adf17-194">.vscode/launch.json</span><span class="sxs-lookup"><span data-stu-id="adf17-194">.vscode/launch.json</span></span>
- <span data-ttu-id="adf17-195">Dockerfile.debug</span><span class="sxs-lookup"><span data-stu-id="adf17-195">Dockerfile.debug</span></span>
- <span data-ttu-id="adf17-196">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="adf17-196">Dockerfile</span></span>
- <span data-ttu-id="adf17-197">docker-compose.debug.yml</span><span class="sxs-lookup"><span data-stu-id="adf17-197">docker-compose.debug.yml</span></span>
- <span data-ttu-id="adf17-198">docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="adf17-198">docker-compose.yml</span></span>
- <span data-ttu-id="adf17-199">dockerTask.ps1</span><span class="sxs-lookup"><span data-stu-id="adf17-199">dockerTask.ps1</span></span>
- <span data-ttu-id="adf17-200">dockerTask.sh</span><span class="sxs-lookup"><span data-stu-id="adf17-200">dockerTask.sh</span></span>
- <span data-ttu-id="adf17-201">.vscode/tasks.json</span><span class="sxs-lookup"><span data-stu-id="adf17-201">.vscode/tasks.json</span></span>

<span data-ttu-id="adf17-202">Il generatore crea due documenti Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="adf17-202">The generator creates two Dockerfiles.</span></span>

<span data-ttu-id="adf17-203">**Dockerfile.debug**: questo file è basato sull'immagine **microsoft/dotnet:1.0.0-preview2-sdk** che, come si nota dall'elenco delle varianti di immagine, include SDK, interfaccia della riga di comando e .NET Core. Tale immagine sarà quella usata per lo sviluppo e il debug (F5).</span><span class="sxs-lookup"><span data-stu-id="adf17-203">**Dockerfile.debug** - this file is based on the **microsoft/dotnet:1.0.0-preview2-sdk** image which if you note from the list of image variants, includes the SDK, CLI and .NET Core and will be the image used for development and debugging (F5).</span></span> <span data-ttu-id="adf17-204">L'inclusione di tutti questi componenti crea un'immagine più grande, di dimensioni pari a circa 540 MB.</span><span class="sxs-lookup"><span data-stu-id="adf17-204">Including all of these components produces a larger image with a size roughly of 540MB.</span></span>

<span data-ttu-id="adf17-205">**Dockerfile**: si tratta dell'immagine della versione basata su **microsoft/dotnet:1.0.0-core** e deve essere usata per la produzione.</span><span class="sxs-lookup"><span data-stu-id="adf17-205">**Dockerfile** - this image is the release image based on **microsoft/dotnet:1.0.0-core** and should be used for production.</span></span> <span data-ttu-id="adf17-206">Quando eseguita, questa immagine è pari a circa 253 MB.</span><span class="sxs-lookup"><span data-stu-id="adf17-206">This image when built is approximately 253 MB.</span></span>

### <a name="creating-the-docker-images"></a><span data-ttu-id="adf17-207">Creazione di immagini Docker</span><span class="sxs-lookup"><span data-stu-id="adf17-207">Creating the Docker images</span></span>
<span data-ttu-id="adf17-208">Usando lo script `dockerTask.sh` o `dockerTask.ps1` è possibile compilare o comporre l'immagine e il contenitore dell'applicazione **api** per un ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="adf17-208">Using the `dockerTask.sh` or `dockerTask.ps1` script, we can build or compose the image and container for the **api** application for a specific environment.</span></span> <span data-ttu-id="adf17-209">Compilare l'immagine di **debug** eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="adf17-209">Build the **debug** image by running the following command.</span></span>

```bash
./dockerTask.sh build debug
```

<span data-ttu-id="adf17-210">L'immagine compilerà l'applicazione ASP.NET, eseguirà `dotnet restore`, aggiungerà il debugger all'immagine, imposterà un `ENTRYPOINT` e al termine copierà l'app nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="adf17-210">The image will build the ASP.NET application, run `dotnet restore`, add the debugger to the image, set an `ENTRYPOINT` and finally copy the app to the image.</span></span> <span data-ttu-id="adf17-211">Il risultato è un'immagine Docker denominata *api* con un `TAG` di *debug*.</span><span class="sxs-lookup"><span data-stu-id="adf17-211">The result is a Docker image named *api* with a `TAG` of *debug*.</span></span>  <span data-ttu-id="adf17-212">Vedere le immagini sul computer usando `docker images`.</span><span class="sxs-lookup"><span data-stu-id="adf17-212">See the images on the machine using `docker images`.</span></span>

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

<span data-ttu-id="adf17-213">Un altro modo per generare l'immagine ed eseguire l'applicazione all'interno del contenitore Docker consiste nell'aprire l'applicazione in Visual Studio Code e usare gli strumenti di debug.</span><span class="sxs-lookup"><span data-stu-id="adf17-213">Another way to generate the image and run the application within the Docker container is to open the application in Visual Studio Code and use the debugging tools.</span></span> 

<span data-ttu-id="adf17-214">Selezionare l'icona di debug nella barra delle visualizzazioni a sinistra di Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="adf17-214">Select the debugging icon in the View Bar on the left side of Visual Studio Code.</span></span>

![icona per il debug di Visual Studio Code](./media/building-net-docker-images/debugging_debugicon.png)

<span data-ttu-id="adf17-216">Fare quindi clic sull'icona per la riproduzione o premere F5 per generare l'immagine e avviare l'applicazione all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="adf17-216">Then tap the play icon or F5 to generate the image and start the application within the container.</span></span> <span data-ttu-id="adf17-217">L'applicazione API Web verrà avviata usando il Web browser predefinito in http://localhost:5000.</span><span class="sxs-lookup"><span data-stu-id="adf17-217">The Web API will be launched using your default web browser at http://localhost:5000.</span></span>

![Visual Studio Code - Strumenti di debug Docker](./media/building-net-docker-images/docker-tools-vscode-f5.png)

<span data-ttu-id="adf17-219">Nell'applicazione è possibile impostare punti di interruzione, passaggi e così via come se l'applicazione stessa fosse in esecuzione in locale sul computer di sviluppo e non all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="adf17-219">You may set break points in your application, step through, etc. just as if the application was running locally on your development machine as opposed to inside the container.</span></span> <span data-ttu-id="adf17-220">Il vantaggio di eseguire il debug all'interno del contenitore consiste nel fatto che questa è la stessa immagine che verrà distribuita in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="adf17-220">The benefit to debugging within the container is this is the same image that would be deployed to a production environment.</span></span>

<span data-ttu-id="adf17-221">Per la creazione dell'immagine della versione o di produzione è sufficiente eseguire questo comando dal terminale passando il nome di ambiente `release`.</span><span class="sxs-lookup"><span data-stu-id="adf17-221">Creating the release or production image requires simply running the command from the terminal passing the `release` environment name.</span></span>

```bash
./dockerTask build release
```

<span data-ttu-id="adf17-222">Il comando crea l'immagine basandosi sull'immagine di base **microsoft/dotnet:core** più piccola, esegue un [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) sulla porta 5000, imposta l'[ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) per `dotnet api.dll` e lo copia nella directory `/app`.</span><span class="sxs-lookup"><span data-stu-id="adf17-222">The command creates the image based on the smaller **microsoft/dotnet:core** base image, [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) port 5000, sets the [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) for `dotnet api.dll` and copies it to the `/app` directory.</span></span> <span data-ttu-id="adf17-223">Non è presente alcun debugger, SDK o `dotnet restore` risultante in un'immagine molto più piccola.</span><span class="sxs-lookup"><span data-stu-id="adf17-223">There is no debugger, SDK or `dotnet restore` resulting in a much smaller image.</span></span> <span data-ttu-id="adf17-224">L'immagine è denominata **api** e ha un `TAG` di tipo **latest**.</span><span class="sxs-lookup"><span data-stu-id="adf17-224">The image is named **api** with a `TAG` of **latest**.</span></span>

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a><span data-ttu-id="adf17-225">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="adf17-225">Summary</span></span>

<span data-ttu-id="adf17-226">L'uso del generatore Docker per aggiungere i file necessari all'applicazione API Web semplifica il processo di creazione delle versioni di sviluppo e produzione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="adf17-226">Using the Docker generator to add the necessary files to our Web API application made the process simple to create the development and production versions of the images.</span></span>  <span data-ttu-id="adf17-227">Gli strumenti sono multipiattaforma e forniscono anche uno script PowerShell per ottenere gli stessi risultati riguardo all'integrazione di Windows e Visual Studio Code, con procedure per il debug dell'applicazione all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="adf17-227">The tooling is cross platform by also providing a PowerShell script to accomplish the same results on Windows and Visual Studio Code integration providing step through debugging of the application within the container.</span></span> <span data-ttu-id="adf17-228">La comprensione delle varianti delle immagini e degli scenari di destinazione consente di ottimizzare i processi di sviluppo a ciclo interno, ottenendo al tempo stesso immagini ottimizzate per le distribuzioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="adf17-228">By understanding the image variants and the target scenarios, you can optimize your inner-loop development process, while achieving optimized images for production deployments.</span></span>  



