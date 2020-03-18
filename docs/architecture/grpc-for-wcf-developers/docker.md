---
title: Docker - gRPC for WCF Developers
description: Creazione di immagini Docker per applicazioni ASP.NET Core gRPC
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148114"
---
# <a name="create-docker-images"></a><span data-ttu-id="1ec0c-103">Creare immagini Docker</span><span class="sxs-lookup"><span data-stu-id="1ec0c-103">Create Docker images</span></span>

<span data-ttu-id="1ec0c-104">Questa sezione illustra la creazione di immagini Docker per ASP.NET applicazioni gRPC Core, pronte per l'esecuzione in Docker, Kubernetes o altri ambienti contenitore.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="1ec0c-105">L'applicazione di esempio utilizzata, con un'app Web MVC di ASP.NET core e un servizio gRPC, è disponibile nel repository [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="1ec0c-106">Immagini di base Microsoft per applicazioni ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1ec0c-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="1ec0c-107">Microsoft fornisce una gamma di immagini di base per la creazione e l'esecuzione di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="1ec0c-108">Per creare un'immagine ASP.NET Core 3.0, si utilizzano due immagini di base:To create an ASP.NET Core 3.0 image, you use two base images:</span><span class="sxs-lookup"><span data-stu-id="1ec0c-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="1ec0c-109">Immagine SDK per compilare e pubblicare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="1ec0c-110">Immagine di runtime per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="1ec0c-111">Immagine</span><span class="sxs-lookup"><span data-stu-id="1ec0c-111">Image</span></span> | <span data-ttu-id="1ec0c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ec0c-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="1ec0c-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="1ec0c-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="1ec0c-114">Per la `docker build`creazione di applicazioni con .</span><span class="sxs-lookup"><span data-stu-id="1ec0c-114">For building applications with `docker build`.</span></span> <span data-ttu-id="1ec0c-115">Non deve essere utilizzato in produzione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="1ec0c-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="1ec0c-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="1ec0c-117">Contiene le dipendenze runtime e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="1ec0c-118">Per la produzione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-118">For production.</span></span> |

<span data-ttu-id="1ec0c-119">Per ogni immagine, ci sono quattro varianti basate su diverse distribuzioni Linux, distinte dai tag.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="1ec0c-120">Tag immagine</span><span class="sxs-lookup"><span data-stu-id="1ec0c-120">Image tag(s)</span></span> | <span data-ttu-id="1ec0c-121">Linux</span><span class="sxs-lookup"><span data-stu-id="1ec0c-121">Linux</span></span> | <span data-ttu-id="1ec0c-122">Note</span><span class="sxs-lookup"><span data-stu-id="1ec0c-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="1ec0c-123">3.0-buster, 3.0</span><span class="sxs-lookup"><span data-stu-id="1ec0c-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="1ec0c-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="1ec0c-124">Debian 10</span></span> | <span data-ttu-id="1ec0c-125">L'immagine predefinita se non viene specificata alcuna variante del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="1ec0c-126">3.0 alpino</span><span class="sxs-lookup"><span data-stu-id="1ec0c-126">3.0-alpine</span></span> | <span data-ttu-id="1ec0c-127">Alpi 3.9</span><span class="sxs-lookup"><span data-stu-id="1ec0c-127">Alpine 3.9</span></span> | <span data-ttu-id="1ec0c-128">Le immagini di base alpine sono molto più piccole di quelle di Debian o Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="1ec0c-129">3.0-discoteca</span><span class="sxs-lookup"><span data-stu-id="1ec0c-129">3.0-disco</span></span> | <span data-ttu-id="1ec0c-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="1ec0c-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="1ec0c-131">3.0-bionic</span><span class="sxs-lookup"><span data-stu-id="1ec0c-131">3.0-bionic</span></span> | <span data-ttu-id="1ec0c-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="1ec0c-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="1ec0c-133">L'immagine di base alpina è di circa 100 MB, rispetto ai 200 MB per le immagini Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="1ec0c-134">Alcuni pacchetti software o librerie potrebbero non essere disponibili nella gestione dei pacchetti di Alpine.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="1ec0c-135">Se non sei sicuro di quale immagine usare, probabilmente dovresti scegliere il Debian predefinito.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ec0c-136">Assicurarsi di utilizzare la stessa variante di Linux per la compilazione e il runtime.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="1ec0c-137">Le applicazioni create e pubblicate su una variante potrebbero non funzionare su un'altra.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="1ec0c-138">Creare un'immagine Docker</span><span class="sxs-lookup"><span data-stu-id="1ec0c-138">Create a Docker image</span></span>

<span data-ttu-id="1ec0c-139">Un'immagine Docker è definita da un *file Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="1ec0c-140">Si tratta di un file di testo che contiene tutti i comandi necessari per compilare l'applicazione e installare le dipendenze necessarie per la compilazione o l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="1ec0c-141">L'esempio seguente mostra il Dockerfile più semplice per un'applicazione ASP.NET Core 3.0:The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span><span class="sxs-lookup"><span data-stu-id="1ec0c-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="1ec0c-142">Il Dockerfile ha due parti: `sdk` il primo utilizza l'immagine di base per compilare e pubblicare l'applicazione; il secondo crea un'immagine di runtime dalla `aspnet` base.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="1ec0c-143">Questo perché `sdk` l'immagine è di circa 900 MB, rispetto a circa 200 MB per l'immagine di runtime e la maggior parte del suo contenuto non sono necessari in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="1ec0c-144">Le istruzioni di compilazione</span><span class="sxs-lookup"><span data-stu-id="1ec0c-144">The build steps</span></span>

| <span data-ttu-id="1ec0c-145">Passaggio</span><span class="sxs-lookup"><span data-stu-id="1ec0c-145">Step</span></span> | <span data-ttu-id="1ec0c-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ec0c-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="1ec0c-147">Dichiara l'immagine di base `builder` e assegna l'alias.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="1ec0c-148">Crea `/src` la directory e la imposta come directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="1ec0c-149">Copia tutti gli elementi al di sotto della directory corrente nell'host nella directory corrente sull'immagine.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="1ec0c-150">Ripristina tutti i pacchetti esterni (ASP.NET framework Core 3.0 è preinstallato con l'SDK).</span><span class="sxs-lookup"><span data-stu-id="1ec0c-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="1ec0c-151">Compila e pubblica una build di rilascio.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="1ec0c-152">Si noti che il `--runtime` flag non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="1ec0c-153">Passaggi dell'immagine di runtimeThe runtime image steps</span><span class="sxs-lookup"><span data-stu-id="1ec0c-153">The runtime image steps</span></span>

| <span data-ttu-id="1ec0c-154">Passaggio</span><span class="sxs-lookup"><span data-stu-id="1ec0c-154">Step</span></span> | <span data-ttu-id="1ec0c-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ec0c-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="1ec0c-156">Dichiara una nuova immagine di base.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="1ec0c-157">Crea `/app` la directory e la imposta come directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="1ec0c-158">Copia l'applicazione pubblicata dall'immagine `builder` precedente, utilizzando `FROM` l'alias dalla prima riga.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="1ec0c-159">Imposta il comando da eseguire all'avvio del contenitore.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="1ec0c-160">Il `dotnet` comando nell'immagine di runtime può eseguire solo file DLL.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="1ec0c-161">HTTPS in Docker</span><span class="sxs-lookup"><span data-stu-id="1ec0c-161">HTTPS in Docker</span></span>

<span data-ttu-id="1ec0c-162">Le immagini di base `ASPNETCORE_URLS` Microsoft per `http://+:80`Docker impostano la variabile di ambiente su , il che significa che Kestrel viene eseguito senza HTTPS su tale porta.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="1ec0c-163">Se si utilizza HTTPS con un certificato personalizzato (come descritto in [Applicazioni gRPC self-hosted](self-hosted.md)), è necessario eseguire l'override di questo.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="1ec0c-164">Impostare la variabile di ambiente nella parte di creazione dell'immagine di runtime del file Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="1ec0c-165">Il file .dockerignore</span><span class="sxs-lookup"><span data-stu-id="1ec0c-165">The .dockerignore file</span></span>

<span data-ttu-id="1ec0c-166">`.gitignore` Analogamente ai file che escludono determinati file e directory dal controllo del codice sorgente, il `.dockerignore` file può essere utilizzato per escludere file e directory dalla copia nell'immagine durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="1ec0c-167">Questo non solo consente di risparmiare tempo di copia, ma `obj` può anche evitare alcuni errori che derivano da avere la directory dal PC copiata nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="1ec0c-168">Come minimo, è necessario aggiungere `bin` `obj` voci `.dockerignore` per e al file.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="1ec0c-169">Compilare l'immagine</span><span class="sxs-lookup"><span data-stu-id="1ec0c-169">Build the image</span></span>

<span data-ttu-id="1ec0c-170">Per una soluzione con una singola applicazione e quindi un singolo Dockerfile, è più semplice inserire il Dockerfile nella directory di base.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="1ec0c-171">In altre parole, metterlo nella stessa `.sln` directory del file.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="1ec0c-172">In tal caso, per compilare `docker build` l'immagine, utilizzare il comando seguente dalla directory contenente il Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="1ec0c-173">Il flag `--tag` confuso denominato (che `-t`può essere abbreviato in ) specifica l'intero nome dell'immagine, incluso il tag effettivo, se specificato.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="1ec0c-174">L'oggetto `.` alla fine specifica il contesto in cui verrà eseguita la compilazione. la directory di `COPY` lavoro corrente per i comandi nel dockerfile.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="1ec0c-175">Se si dispone di più applicazioni all'interno di una singola soluzione, è `.csproj` possibile mantenere il Dockerfile per ogni applicazione nella propria cartella, accanto al file.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="1ec0c-176">È comunque `docker build` necessario eseguire il comando dalla directory di base per assicurarsi che la soluzione e tutti i progetti vengano copiati nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="1ec0c-177">È possibile specificare un Dockerfile sotto `--file` la `-f`directory corrente utilizzando il flag (o ).</span><span class="sxs-lookup"><span data-stu-id="1ec0c-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="1ec0c-178">Eseguire l'immagine in un contenitore nel computerRun the image in a container on your machine</span><span class="sxs-lookup"><span data-stu-id="1ec0c-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="1ec0c-179">Per eseguire l'immagine nell'istanza Docker locale, utilizzare il `docker run` comando .</span><span class="sxs-lookup"><span data-stu-id="1ec0c-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="1ec0c-180">Il `-ti` flag collega il terminale corrente al terminale del contenitore e viene eseguito in modalità interattiva.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="1ec0c-181">La `-p 5000:80` porta pubblica (collegamenti) 80 sul contenitore alla porta 5000 sull'interfaccia di rete localhost.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="1ec0c-182">Eseguire il push dell'immagine in un registro</span><span class="sxs-lookup"><span data-stu-id="1ec0c-182">Push the image to a registry</span></span>

<span data-ttu-id="1ec0c-183">Dopo aver verificato il funzionamento dell'immagine, eseguirne il push in un Registro di sistema di Docker per renderla disponibile in altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="1ec0c-184">Le reti interne dovranno eseguire il provisioning di un registro Docker.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="1ec0c-185">Questo può essere semplice come [ `registry` l'esecuzione dell'immagine di Docker](https://docs.docker.com/registry/deploying/) (il Registro di sistema Docker viene eseguito in un contenitore Docker), ma sono disponibili varie soluzioni più complete.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="1ec0c-186">Per la condivisione esterna e l'uso nel cloud, sono disponibili vari registri gestiti, ad esempio [Registro contenitori](https://docs.microsoft.com/azure/container-registry/) di Azure o [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="1ec0c-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="1ec0c-187">Per eseguire il push a Docker Hub, anteporre all'utente o all'organizzazione il nome dell'utente o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="1ec0c-188">Per eseguire il push in un registro privato, anteporre al nome dell'immagine il nome host del Registro di sistema e il nome dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="1ec0c-189">Dopo che l'immagine è in un Registro di sistema, è possibile distribuirla a singoli host Docker o a un motore di orchestrazione contenitore come Kubernetes.After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1ec0c-190">[Successivo](self-hosted.md)
>[precedente](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="1ec0c-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
