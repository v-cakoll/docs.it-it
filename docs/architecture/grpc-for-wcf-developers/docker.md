---
title: Docker-gRPC per sviluppatori WCF
description: Creazione di immagini Docker per ASP.NET Core applicazioni gRPC
ms.date: 09/02/2019
ms.openlocfilehash: a5aceb4b5270cb828965e990a62db4147012adff
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967836"
---
# <a name="docker"></a><span data-ttu-id="d5a3b-103">Docker</span><span class="sxs-lookup"><span data-stu-id="d5a3b-103">Docker</span></span>

<span data-ttu-id="d5a3b-104">Questa sezione include la creazione di immagini Docker per ASP.NET Core applicazioni gRPC, pronte per l'esecuzione in Docker, Kubernetes o in altri ambienti contenitore.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-104">This section will cover the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="d5a3b-105">L'applicazione di esempio usata con un'app Web MVC ASP.NET Core e un servizio gRPC è disponibile nel repository [DotNet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="d5a3b-106">Immagini di base di Microsoft per applicazioni ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d5a3b-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="d5a3b-107">Microsoft offre una gamma di immagini di base per la compilazione e l'esecuzione di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="d5a3b-108">Per creare un'immagine di ASP.NET Core 3,0, vengono usate due immagini di base: un'immagine dell'SDK per compilare e pubblicare l'applicazione e un'immagine di runtime per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-108">To create an ASP.NET Core 3.0 image, two base images are used: an SDK image to build and publish the application, and a runtime image for deployment.</span></span>

| <span data-ttu-id="d5a3b-109">Image</span><span class="sxs-lookup"><span data-stu-id="d5a3b-109">Image</span></span> | <span data-ttu-id="d5a3b-110">description</span><span class="sxs-lookup"><span data-stu-id="d5a3b-110">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="d5a3b-111">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="d5a3b-111">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="d5a3b-112">Per la compilazione di applicazioni con `docker build`.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-112">For building applications with `docker build`.</span></span> <span data-ttu-id="d5a3b-113">Che non deve essere utilizzato nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-113">Not to be used in production.</span></span> |
| [<span data-ttu-id="d5a3b-114">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="d5a3b-114">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="d5a3b-115">Contiene le dipendenze di runtime e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-115">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="d5a3b-116">Per la produzione.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-116">For production.</span></span> |

<span data-ttu-id="d5a3b-117">Per ogni immagine sono disponibili quattro varianti basate su distribuzioni diverse di Linux, distinte per i tag.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-117">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="d5a3b-118">Tag immagine</span><span class="sxs-lookup"><span data-stu-id="d5a3b-118">Image tag(s)</span></span> | <span data-ttu-id="d5a3b-119">Linux</span><span class="sxs-lookup"><span data-stu-id="d5a3b-119">Linux</span></span> | <span data-ttu-id="d5a3b-120">Note</span><span class="sxs-lookup"><span data-stu-id="d5a3b-120">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="d5a3b-121">3,0-Buster, 3,0</span><span class="sxs-lookup"><span data-stu-id="d5a3b-121">3.0-buster, 3.0</span></span> | <span data-ttu-id="d5a3b-122">Debian 10</span><span class="sxs-lookup"><span data-stu-id="d5a3b-122">Debian 10</span></span> | <span data-ttu-id="d5a3b-123">Immagine predefinita se non è specificata alcuna variante del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-123">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="d5a3b-124">3,0-alpino</span><span class="sxs-lookup"><span data-stu-id="d5a3b-124">3.0-alpine</span></span> | <span data-ttu-id="d5a3b-125">Alpino 3,9</span><span class="sxs-lookup"><span data-stu-id="d5a3b-125">Alpine 3.9</span></span> | <span data-ttu-id="d5a3b-126">Le immagini di base Alpine sono molto più piccole di quelle Debian o Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-126">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="d5a3b-127">3,0-disco</span><span class="sxs-lookup"><span data-stu-id="d5a3b-127">3.0-disco</span></span> | <span data-ttu-id="d5a3b-128">Ubuntu 19,04</span><span class="sxs-lookup"><span data-stu-id="d5a3b-128">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="d5a3b-129">3,0-Bionic</span><span class="sxs-lookup"><span data-stu-id="d5a3b-129">3.0-bionic</span></span> | <span data-ttu-id="d5a3b-130">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d5a3b-130">Ubuntu 18.04</span></span> | |

<span data-ttu-id="d5a3b-131">L'immagine di base Alpina è di circa 100 MB, rispetto a 200 MB per le immagini Debian e Ubuntu, ma alcuni pacchetti software o librerie potrebbero non essere disponibili nella gestione dei pacchetti di Alpine.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images, but some software packages or libraries may not be available in Alpine's package management.</span></span> <span data-ttu-id="d5a3b-132">Se non si è certi dell'immagine da usare, è preferibile attenersi alla Debian predefinita, a meno che non sia necessario usare una distribuzione diversa.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-132">If you're not sure which image to use, it's best to stick to the default Debian unless you have a compelling need to use a different distro.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5a3b-133">Assicurarsi di usare la stessa variante di Linux per la compilazione e il Runtime.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-133">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="d5a3b-134">Le applicazioni compilate e pubblicate in una variante potrebbero non funzionare in un'altra.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-134">Applications built and published on one variant may not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="d5a3b-135">Creare un'immagine Docker</span><span class="sxs-lookup"><span data-stu-id="d5a3b-135">Create a Docker image</span></span>

<span data-ttu-id="d5a3b-136">Un'immagine Docker è definita da un *Dockerfile*, un file di testo che contiene tutti i comandi necessari per compilare l'applicazione e installare le dipendenze necessarie per la compilazione o l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-136">A Docker image is defined by a *Dockerfile*, a text file that contains all the commands that are needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="d5a3b-137">Nell'esempio seguente viene illustrato il Dockerfile più semplice per un'applicazione ASP.NET Core 3,0:</span><span class="sxs-lookup"><span data-stu-id="d5a3b-137">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="d5a3b-138">Il Dockerfile è costituito da due parti: la prima usa l'immagine di base `sdk` per compilare e pubblicare l'applicazione. il secondo crea un'immagine di runtime dalla base `aspnet`.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-138">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="d5a3b-139">Ciò è dovuto al fatto che l'immagine del `sdk` è di circa 900 MB rispetto a circa 200 MB per l'immagine di runtime e la maggior parte del contenuto non è necessaria in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-139">This is because the `sdk` image is around 900 MB compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="d5a3b-140">Procedura di compilazione</span><span class="sxs-lookup"><span data-stu-id="d5a3b-140">The build steps</span></span>

| <span data-ttu-id="d5a3b-141">Passaggio</span><span class="sxs-lookup"><span data-stu-id="d5a3b-141">Step</span></span> | <span data-ttu-id="d5a3b-142">description</span><span class="sxs-lookup"><span data-stu-id="d5a3b-142">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="d5a3b-143">Dichiara l'immagine di base e assegna l'alias di `builder` (vedere la sezione successiva per la spiegazione).</span><span class="sxs-lookup"><span data-stu-id="d5a3b-143">Declares the base image and assigns the `builder` alias (see next section for explanation).</span></span> |
| `WORKDIR /src` | <span data-ttu-id="d5a3b-144">Crea la directory di `/src` e la imposta come directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-144">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="d5a3b-145">Copia tutti gli elementi sotto la directory corrente nell'host nella directory corrente dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-145">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="d5a3b-146">Ripristina tutti i pacchetti esterni (ASP.NET Core Framework 3,0 è preinstallato con l'SDK).</span><span class="sxs-lookup"><span data-stu-id="d5a3b-146">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="d5a3b-147">Compila e pubblica una build di rilascio.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-147">Builds and publishes a Release build.</span></span> <span data-ttu-id="d5a3b-148">Si noti che il flag di `--runtime` non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-148">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="d5a3b-149">Passaggi dell'immagine di runtime</span><span class="sxs-lookup"><span data-stu-id="d5a3b-149">The runtime image steps</span></span>

| <span data-ttu-id="d5a3b-150">Passaggio</span><span class="sxs-lookup"><span data-stu-id="d5a3b-150">Step</span></span> | <span data-ttu-id="d5a3b-151">description</span><span class="sxs-lookup"><span data-stu-id="d5a3b-151">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="d5a3b-152">Dichiara una nuova immagine di base.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-152">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="d5a3b-153">Crea la directory di `/app` e la imposta come directory di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-153">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="d5a3b-154">Copia l'applicazione pubblicata dall'immagine precedente, utilizzando l'alias `builder` dalla prima riga di `FROM`.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-154">Copies the published application from the previous image, using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="d5a3b-155">Imposta il comando da eseguire all'avvio del contenitore.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-155">Sets the command to run when the container starts.</span></span> <span data-ttu-id="d5a3b-156">Il `dotnet` comando nell'immagine di runtime può eseguire solo file DLL.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-156">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="d5a3b-157">HTTPS in Docker</span><span class="sxs-lookup"><span data-stu-id="d5a3b-157">HTTPS in Docker</span></span>

<span data-ttu-id="d5a3b-158">Le immagini di base di Microsoft per Docker impostano la variabile di ambiente `ASPNETCORE_URLS` su `http://+:80`, il che significa che il gheppio viene eseguito senza HTTPS su tale porta.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-158">Microsoft's base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel will run without HTTPS on that port.</span></span> <span data-ttu-id="d5a3b-159">Se si usa HTTPS con un certificato personalizzato (come descritto nella [sezione precedente](self-hosted.md)), è consigliabile eseguire l'override impostando la variabile di ambiente **nella parte relativa alla creazione dell'immagine di runtime** di Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-159">If you're using HTTPS with a custom certificate (as described in [the previous section](self-hosted.md)), you should override this by setting the environment variable **in the runtime image creation part** of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="d5a3b-160">Il file con estensione dockerignore</span><span class="sxs-lookup"><span data-stu-id="d5a3b-160">The .dockerignore file</span></span>

<span data-ttu-id="d5a3b-161">Analogamente ai file `.gitignore` che escludono determinati file e directory dal controllo del codice sorgente, è possibile usare il file `.dockerignore` per escludere file e directory dalla copia nell'immagine durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-161">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="d5a3b-162">In questo modo non solo viene salvata la copia dell'ora, ma è anche possibile evitare alcuni errori di confusione che derivano dalla presenza (in particolare) della directory `obj` dal PC copiato nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-162">This not only saves time copying, but can also avoid some confusing errors that arise from having (particularly) the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="d5a3b-163">È necessario aggiungere almeno voci per `bin` e `obj` al file `.dockerignore`.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-163">You should add at least entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="d5a3b-164">Creare l'immagine</span><span class="sxs-lookup"><span data-stu-id="d5a3b-164">Build the image</span></span>

<span data-ttu-id="d5a3b-165">Per una soluzione con una singola applicazione e quindi un singolo Dockerfile, è più semplice inserire il Dockerfile nella directory di base; ovvero la stessa directory in cui si trova il file di `.sln`.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-165">For a solution with a single application, and thus a single Dockerfile, it is simplest to put the Dockerfile in the base directory; that is, the same directory as the `.sln` file.</span></span> <span data-ttu-id="d5a3b-166">In tal caso, per compilare l'immagine, usare il comando `docker build` seguente dalla directory che contiene Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-166">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="d5a3b-167">Il flag di `--tag` con nome confuso, che può essere abbreviato in `-t`, specifica il nome completo dell'immagine, *incluso* il tag effettivo, se specificato.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-167">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, *including* the actual tag if specified.</span></span> <span data-ttu-id="d5a3b-168">Il `.` alla fine specifica il *contesto* in cui verrà eseguita la compilazione. la directory di lavoro corrente per i comandi `COPY` in Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-168">The `.` at the end specifies the *context* in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="d5a3b-169">Se si dispone di più applicazioni all'interno di una singola soluzione, è possibile mantenere il Dockerfile per ogni applicazione nella propria cartella, accanto al file `.csproj`, ma è comunque necessario eseguire il comando `docker build` dalla directory di base per assicurarsi che la soluzione e tutti i progetti vengano copiati nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-169">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file, but you should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="d5a3b-170">È possibile specificare un Dockerfile sotto la directory corrente usando il flag `--file` (o `-f`).</span><span class="sxs-lookup"><span data-stu-id="d5a3b-170">You can specify a Dockerfile below the current directory using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="d5a3b-171">Eseguire l'immagine in un contenitore del computer</span><span class="sxs-lookup"><span data-stu-id="d5a3b-171">Run the image in a container on your machine</span></span>

<span data-ttu-id="d5a3b-172">Per eseguire l'immagine nell'istanza locale di Docker, usare il comando `docker run`.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-172">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="d5a3b-173">Il flag di `-ti` connette il terminale corrente al terminale del contenitore e viene eseguito in modalità interattiva.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-173">The `-ti` flag connects your current terminal to the container's terminal and runs in interactive mode.</span></span> <span data-ttu-id="d5a3b-174">Il `-p 5000:80` pubblica (collega) la porta 80 sul contenitore sulla porta 80 sull'interfaccia di rete localhost.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-174">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="d5a3b-175">Eseguire il push dell'immagine in un registro</span><span class="sxs-lookup"><span data-stu-id="d5a3b-175">Push the image to a registry</span></span>

<span data-ttu-id="d5a3b-176">Dopo aver verificato il funzionamento dell'immagine, è necessario eseguirne il push in un registro Docker per renderlo disponibile in altri sistemi.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-176">Once you've verified that the image works, you need to push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="d5a3b-177">Le reti interne dovranno eseguire il provisioning di un registro docker.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-177">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="d5a3b-178">Questa operazione può essere semplice quanto l'esecuzione dell' [immagine `registry` di Docker](https://docs.docker.com/registry/deploying/) (a destra, il registro Docker viene eseguito in un contenitore Docker), ma sono disponibili diverse soluzioni più complete.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-178">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (that's right, the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="d5a3b-179">Per la condivisione esterna e l'uso del cloud, sono disponibili diversi registri gestiti, ad esempio [Azure container Registry](https://docs.microsoft.com/azure/container-registry/) o [Hub Docker](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="d5a3b-179">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="d5a3b-180">Per eseguire il push nell'hub Docker, anteporre al nome dell'utente o dell'organizzazione il nome dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-180">To push to the Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="d5a3b-181">Per eseguire il push in un registro privato, anteporre al nome dell'immagine il nome host del registro di sistema e il nome dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-181">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="d5a3b-182">Quando l'immagine si trova in un registro, è possibile distribuirla nei singoli host Docker o in un motore di orchestrazione del contenitore come Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="d5a3b-182">Once the image is in a registry, you can deploy it to individual Docker hosts or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d5a3b-183">[Precedente](self-hosted.md)
>[Successivo](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="d5a3b-183">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
