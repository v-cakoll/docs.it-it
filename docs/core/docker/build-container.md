---
title: Distribuire un'app in un contenitore con Docker - Esercitazione
description: In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core con Docker.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c5e6648539af45f3ce615bfc183e6f95a62b085a
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200028"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="2fdeb-103">Esercitazione: distribuire un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="2fdeb-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="2fdeb-104">In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core con Docker.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-104">In this tutorial, you'll learn how to containerize a .NET Core application with Docker.</span></span> <span data-ttu-id="2fdeb-105">I contenitori offrono numerose funzionalità e vantaggi, ad esempio un'infrastruttura non modificabile, un'architettura portatile e l'abilitazione della scalabilità.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-105">Containers have many features and benefits, such as being an immutable infrastructure, providing a portable architecture, and enabling scalability.</span></span> <span data-ttu-id="2fdeb-106">L'immagine può essere usata per creare contenitori per l'ambiente di sviluppo locale, il cloud privato o il cloud pubblico.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-106">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="2fdeb-107">In questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-107">In this tutorial, you:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="2fdeb-108">Creare e pubblicare un'app .NET Core semplice</span><span class="sxs-lookup"><span data-stu-id="2fdeb-108">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="2fdeb-109">Creare e configurare un Dockerfile per .NET Core</span><span class="sxs-lookup"><span data-stu-id="2fdeb-109">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="2fdeb-110">Creare un'immagine Docker</span><span class="sxs-lookup"><span data-stu-id="2fdeb-110">Build a Docker image</span></span>
> - <span data-ttu-id="2fdeb-111">Creare ed eseguire un contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="2fdeb-111">Create and run a Docker container</span></span>

<span data-ttu-id="2fdeb-112">L'esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-112">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="2fdeb-113">La *piattaforma Docker* usa il *motore Docker* per compilare e creare pacchetti di app in modo rapido come *Immagini Docker*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-113">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="2fdeb-114">Queste immagini vengono scritte nel formato *Dockerfile* per la distribuzione e l'esecuzione in un contenitore su più livelli.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-114">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!NOTE]
> <span data-ttu-id="2fdeb-115">Questa esercitazione **non è** destinata alle app ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-115">This tutorial **is not** for ASP.NET Core apps.</span></span> <span data-ttu-id="2fdeb-116">Se si usa ASP.NET Core, vedere l'esercitazione [informazioni su come distribuire un'applicazione ASP.NET Core](/aspnet/core/host-and-deploy/docker/building-net-docker-images) .</span><span class="sxs-lookup"><span data-stu-id="2fdeb-116">If you're using ASP.NET Core, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fdeb-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2fdeb-117">Prerequisites</span></span>

<span data-ttu-id="2fdeb-118">Installare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-118">Install the following prerequisites:</span></span>

- <span data-ttu-id="2fdeb-119">[SDK di .NET Core 3,1](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="2fdeb-119">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="2fdeb-120">Se .NET Core è già installato, usare il comando `dotnet --info` per determinare quale SDK è in uso.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-120">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>
- [<span data-ttu-id="2fdeb-121">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="2fdeb-121">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)
- <span data-ttu-id="2fdeb-122">Una cartella di lavoro temporanea per il *Dockerfile* e l'app .NET Core di esempio.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-122">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="2fdeb-123">In questa esercitazione il nome *Docker-working* viene usato come cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-123">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="2fdeb-124">Creare un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="2fdeb-124">Create .NET Core app</span></span>

<span data-ttu-id="2fdeb-125">È necessario creare un'app .NET Core che verrà eseguita dal contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-125">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="2fdeb-126">Aprire il terminale in uso, creare una cartella di lavoro se non è già stata creata e passare alla cartella.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-126">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="2fdeb-127">Nella cartella di lavoro, eseguire il comando seguente per creare un nuovo progetto in una sottodirectory denominata *app*:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-127">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

<span data-ttu-id="2fdeb-128">La struttura di cartelle sarà simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-128">Your folder tree will look like the following:</span></span>

```
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
```

<span data-ttu-id="2fdeb-129">Il `dotnet new` comando crea una nuova cartella denominata *app* e genera un'applicazione console "Hello World".</span><span class="sxs-lookup"><span data-stu-id="2fdeb-129">The `dotnet new` command creates a new folder named *App* and generates a "Hello World" console application.</span></span> <span data-ttu-id="2fdeb-130">Cambiare directory e passare alla cartella dell' *app* , dalla sessione del terminale.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-130">Change directories and navigate into the *App* folder, from your terminal session.</span></span> <span data-ttu-id="2fdeb-131">Usare il `dotnet run` comando per avviare l'app.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-131">Use the `dotnet run` command to start the app.</span></span> <span data-ttu-id="2fdeb-132">L'applicazione viene eseguita e viene stampata `Hello World!` sotto il comando:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-132">The application will run, and print `Hello World!` below the command:</span></span>

```dotnetcli
dotnet run
Hello World!
```

<span data-ttu-id="2fdeb-133">Il modello predefinito crea un'app che stampa nel terminale e quindi termina immediatamente.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-133">The default template creates an app that prints to the terminal and then immediately terminates.</span></span> <span data-ttu-id="2fdeb-134">Per questa esercitazione si userà un'app che viene eseguita a ciclo continuo.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="2fdeb-135">Aprire il file *Program.cs* in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-135">Open the *Program.cs* file in a text editor.</span></span>

> [!TIP]
> <span data-ttu-id="2fdeb-136">Se si usa Visual Studio Code, nella sessione terminal precedente digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-136">If you're using Visual Studio Code, from the previous terminal session type the following command:</span></span>
>
> ```
> code .
> ```
>
> <span data-ttu-id="2fdeb-137">Verrà aperta la cartella dell' *app* che contiene il progetto in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-137">This will open the *App* folder that contains the project in Visual Studio Code.</span></span>

<span data-ttu-id="2fdeb-138">Il *Program.cs* dovrebbe essere simile al codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-138">The *Program.cs* should look like the following C# code:</span></span>

```csharp
using System;

namespace NetCore.Docker
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="2fdeb-139">Sostituirlo con il codice seguente che conta i numeri ogni secondo:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-139">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace NetCore.Docker
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                Console.WriteLine($"Counter: {++counter}");
                await Task.Delay(1000);
            }
        }
    }
}
```

<span data-ttu-id="2fdeb-140">Salvare il file e testare di nuovo il programma con `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-140">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="2fdeb-141">Tenere presente che l'app viene eseguita per un tempo illimitato.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-141">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="2fdeb-142">Usare il comando Annulla <kbd>CTRL + C</kbd> per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-142">Use the cancel command <kbd>Ctrl+C</kbd> to stop it.</span></span> <span data-ttu-id="2fdeb-143">Di seguito è riportato un esempio di output:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-143">The following is an example output:</span></span>

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="2fdeb-144">Se si passa un numero all'app nella riga di comando, verrà eseguito il conteggio fino a quel numero e quindi l'app verrà chiusa.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-144">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="2fdeb-145">Provare con `dotnet run -- 5` per contare fino a cinque.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-145">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fdeb-146">I parametri dopo `--` non vengono passati al comando `dotnet run` e vengono invece passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-146">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="2fdeb-147">Pubblicare l'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="2fdeb-147">Publish .NET Core app</span></span>

<span data-ttu-id="2fdeb-148">Prima di aggiungere l'app .NET Core all'immagine Docker, è prima necessario pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-148">Before adding the .NET Core app to the Docker image, first it must be published.</span></span> <span data-ttu-id="2fdeb-149">È consigliabile fare in modo che il contenitore esegua la versione pubblicata dell'app.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-149">It is best to have the container run the published version of the app.</span></span> <span data-ttu-id="2fdeb-150">Per pubblicare l'app, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-150">To publish the app, run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="2fdeb-151">Questo comando compila l'app nella cartella *publish*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-151">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="2fdeb-152">Il percorso della cartella *publish* dalla cartella di lavoro deve essere `.\App\bin\Release\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="2fdeb-152">The path to the *publish* folder from the working folder should be `.\App\bin\Release\netcoreapp3.1\publish\`</span></span>

#### <a name="windows"></a>[<span data-ttu-id="2fdeb-153">Windows</span><span class="sxs-lookup"><span data-stu-id="2fdeb-153">Windows</span></span>](#tab/windows)

<span data-ttu-id="2fdeb-154">Dalla cartella dell' *app* , ottenere un elenco di directory della cartella di pubblicazione per verificare che sia stato creato il file *Netcore. docker. dll* .</span><span class="sxs-lookup"><span data-stu-id="2fdeb-154">From the *App* folder, get a directory listing of the publish folder to verify that the *NetCore.Docker.dll* file was created.</span></span>

```powershell
dir .\bin\Release\netcoreapp3.1\publish\

    Directory: C:\Users\dapine\App\bin\Release\netcoreapp3.1\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[<span data-ttu-id="2fdeb-155">Linux</span><span class="sxs-lookup"><span data-stu-id="2fdeb-155">Linux</span></span>](#tab/linux)

<span data-ttu-id="2fdeb-156">Usare il `ls` comando per ottenere un elenco di directory e verificare che sia stato creato il file *Netcore. docker. dll* .</span><span class="sxs-lookup"><span data-stu-id="2fdeb-156">Use the `ls` command to get a directory listing and verify that the *NetCore.Docker.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a><span data-ttu-id="2fdeb-157">Creare il Dockerfile</span><span class="sxs-lookup"><span data-stu-id="2fdeb-157">Create the Dockerfile</span></span>

<span data-ttu-id="2fdeb-158">Il file *Dockerfile* viene usato dal comando `docker build` per creare un'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-158">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="2fdeb-159">Si tratta di un file di testo denominato *Dockerfile* che non dispone di un'estensione.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-159">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="2fdeb-160">Creare un file denominato *Dockerfile* nella directory contenente il file con *estensione csproj* e aprirlo in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-160">Create a file named *Dockerfile* in directory containing the *.csproj* and open it in a text editor.</span></span> <span data-ttu-id="2fdeb-161">Questa esercitazione userà l'immagine di runtime ASP.NET Core (che contiene l'immagine di runtime di .NET Core) e corrisponde all'applicazione console .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-161">This tutorial will use the ASP.NET Core runtime image (which contains the .NET Core runtime image) and corresponds with the .NET Core console application.</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
```

> [!NOTE]
> <span data-ttu-id="2fdeb-162">L'immagine di runtime ASP.NET Core viene utilizzata intenzionalmente, sebbene `mcr.microsoft.com/dotnet/core/runtime:3.1` sia possibile utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-162">The ASP.NET Core runtime image is used intentionally here, although the `mcr.microsoft.com/dotnet/core/runtime:3.1` image could have been used.</span></span>

<span data-ttu-id="2fdeb-163">La `FROM` parola chiave richiede un nome completo dell'immagine del contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-163">The `FROM` keyword requires a fully qualified Docker container image name.</span></span> <span data-ttu-id="2fdeb-164">Microsoft Container Registry (mcr.microsoft.com) è un consorzio di Docker Hub, che ospita i contenitori accessibili pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-164">The Microsoft Container Registry (MCR, mcr.microsoft.com) is a syndicate of Docker Hub - which hosts publicly accessible containers.</span></span> <span data-ttu-id="2fdeb-165">Il `dotnet/core` segmento è il repository del contenitore, dove come `aspnet` segmento è il nome dell'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-165">The `dotnet/core` segment is the container repository, where as the `aspnet` segment is the container image name.</span></span> <span data-ttu-id="2fdeb-166">L'immagine è contrassegnata `3.1`con, che viene usata per il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-166">The image is tagged with `3.1`, which is used for versioning.</span></span> <span data-ttu-id="2fdeb-167">Quindi, `mcr.microsoft.com/dotnet/core/aspnet:3.1` è il runtime di .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-167">Thus, `mcr.microsoft.com/dotnet/core/aspnet:3.1` is the .NET Core 3.1 runtime.</span></span> <span data-ttu-id="2fdeb-168">Assicurarsi di eseguire il pull della versione runtime corrispondente al runtime di destinazione dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-168">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="2fdeb-169">Ad esempio, l'app creata nella sezione precedente usava .NET Core 3,1 SDK e l'immagine di base a cui si fa riferimento in *Dockerfile* è contrassegnata con **3,1**.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-169">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="2fdeb-170">Salvare il file *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-170">Save the *Dockerfile* file.</span></span> <span data-ttu-id="2fdeb-171">La struttura directory della cartella di lavoro deve avere un aspetto simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-171">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="2fdeb-172">Alcuni file e cartelle di livello più profondo sono stati omessi per risparmiare spazio nell'articolo:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-172">Some of the deeper-level files and folders have been omitted to save space in the article:</span></span>

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──netcoreapp3.1
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

<span data-ttu-id="2fdeb-173">Dal terminale eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-173">From your terminal, run the following command:</span></span>

```Docker
docker build -t counter-image -f Dockerfile .
```

<span data-ttu-id="2fdeb-174">Docker elaborerà ogni riga nel *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-174">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="2fdeb-175">`.` Nel `docker build` comando indica a Docker di usare la cartella corrente per trovare un *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-175">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="2fdeb-176">Questo comando compila l'immagine e crea un repository locale denominato **Counter-image** che punta a tale immagine.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-176">This command builds the image and creates a local repository named **counter-image** that points to that image.</span></span> <span data-ttu-id="2fdeb-177">Dopo l'esecuzione del comando, eseguire `docker images` per visualizzare un elenco delle immagini installate:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-177">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```Docker
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="2fdeb-178">Come si può notare, le due immagini condividono lo stesso valore di **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-178">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="2fdeb-179">Il valore delle due immagini è lo stesso perché l'unico comando nel *Dockerfile* indicava di basare la nuova immagine su un'immagine esistente.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-179">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="2fdeb-180">Si aggiungono tre comandi a *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-180">Let's add three commands to the *Dockerfile*.</span></span> <span data-ttu-id="2fdeb-181">Ogni comando crea un nuovo livello immagine con il comando finale che rappresenta i punti di ingresso del repository di **Immagini contatore** a.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-181">Each command creates a new image layer with the final command representing the **counter-image** repository entry points to.</span></span>

```dockerfile
COPY bin/Release/netcoreapp3.1/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

<span data-ttu-id="2fdeb-182">Il comando `COPY` indica a Docker di copiare la cartella specificata nel computer in una cartella nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-182">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="2fdeb-183">In questo esempio, la cartella di *pubblicazione* viene copiata in una cartella denominata *app* nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-183">In this example, the *publish* folder is copied to a folder named *App* in the container.</span></span>

<span data-ttu-id="2fdeb-184">Il `WORKDIR` comando modifica la **directory corrente** all'interno del contenitore in *app*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-184">The `WORKDIR` command changes the **current directory** inside of the container to *App*.</span></span>

<span data-ttu-id="2fdeb-185">Il comando successivo, `ENTRYPOINT`, indica a Docker di configurare il contenitore in modo che venga eseguito come un eseguibile.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-185">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="2fdeb-186">All'avvio del contenitore viene eseguito il comando `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-186">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="2fdeb-187">Al termine del comando, il contenitore si arresta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-187">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="2fdeb-188">Dal terminale eseguire `docker build -t counter-image -f Dockerfile .`, quindi dopo il completamento del comando eseguire `docker images`.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-188">From your terminal, run `docker build -t counter-image -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```Docker
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> e6780479db63
Step 2/4 : COPY bin/Release/netcoreapp3.1/publish/ App/
 ---> d1732740eed2
Step 3/4 : WORKDIR /App
 ---> Running in b1701a42f3ff
Removing intermediate container b1701a42f3ff
 ---> 919aab5b95e3
Step 4/4 : ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
 ---> Running in c12aebd26ced
Removing intermediate container c12aebd26ced
 ---> cd11c3df9b19
Successfully built cd11c3df9b19
Successfully tagged counter-image:latest

docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              cd11c3df9b19        41 seconds ago      190MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 e6780479db63        4 days ago          190MB
```

<span data-ttu-id="2fdeb-189">Ogni comando nel *Dockerfile* ha generato un livello e ha creato un **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-189">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="2fdeb-190">L' **ID immagine** finale (il valore sarà diverso) è **cd11c3df9b19** e successivamente verrà creato un contenitore basato su questa immagine.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-190">The final **IMAGE ID** (yours will be different) is **cd11c3df9b19** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="2fdeb-191">Creare un contenitore</span><span class="sxs-lookup"><span data-stu-id="2fdeb-191">Create a container</span></span>

<span data-ttu-id="2fdeb-192">Ora che si dispone di un'immagine che contiene l'app, è possibile creare un contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-192">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="2fdeb-193">Lo si può fare in due modi.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-193">You can create a container in two ways.</span></span> <span data-ttu-id="2fdeb-194">Prima di tutto, creare un nuovo contenitore arrestato.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-194">First, create a new container that is stopped.</span></span>

```Docker
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

<span data-ttu-id="2fdeb-195">Il `docker create` comando precedente creerà un contenitore in base all'immagine del **contatore** .</span><span class="sxs-lookup"><span data-stu-id="2fdeb-195">The `docker create` command from above will create a container based on the **counter-image** image.</span></span> <span data-ttu-id="2fdeb-196">L'output del comando mostra il **CONTAINER ID** (diverso da quello visualizzato dall'utente) del contenitore creato.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-196">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="2fdeb-197">Per visualizzare un elenco di *tutti* i contenitori, usare il comando `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-197">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```Docker
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a><span data-ttu-id="2fdeb-198">Gestire il contenitore</span><span class="sxs-lookup"><span data-stu-id="2fdeb-198">Manage the container</span></span>

<span data-ttu-id="2fdeb-199">Il contenitore è stato creato con un nome `core-counter`specifico, questo nome viene usato per gestire il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-199">The container was created with a specific name `core-counter`, this name is used to manage the container.</span></span> <span data-ttu-id="2fdeb-200">L'esempio seguente usa il comando `docker start` per avviare il contenitore e quindi usa il comando `docker ps` per visualizzare solo i contenitori in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-200">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```Docker
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

<span data-ttu-id="2fdeb-201">Analogamente, il comando `docker stop` arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-201">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="2fdeb-202">Nell'esempio seguente viene usato `docker stop` il comando per arrestare il contenitore e quindi viene usato `docker ps` il comando per indicare che non è in esecuzione alcun contenitore:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-202">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```Docker
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="2fdeb-203">Connettersi a un contenitore</span><span class="sxs-lookup"><span data-stu-id="2fdeb-203">Connect to a container</span></span>

<span data-ttu-id="2fdeb-204">Quando un contenitore è in esecuzione, è possibile connettersi ad esso per visualizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-204">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="2fdeb-205">Usare i comandi `docker start` e `docker attach` per avviare il contenitore e osservare il flusso di output.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-205">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="2fdeb-206">In questo esempio, la sequenza di tasti <kbd>CTRL + C</kbd> viene usata per scollegare il contenitore in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-206">In this example, the <kbd>Ctrl+C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="2fdeb-207">Questa sequenza di tasti termina il processo nel contenitore se non diversamente specificato, in modo da arrestare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-207">This keystroke will end the process in the container unless otherwise specified, which would stop the container.</span></span> <span data-ttu-id="2fdeb-208">Il `--sig-proxy=false` parametro garantisce che la <kbd>combinazione di tasti CTRL + C</kbd> non arresterà il processo nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-208">The `--sig-proxy=false` parameter ensures that <kbd>Ctrl+C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="2fdeb-209">Dopo essersi scollegati dal contenitore, collegarsi di nuovo per verificare che sia ancora in esecuzione e continui a eseguire il conteggio.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-209">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```Docker
docker start core-counter
core-counter

docker attach --sig-proxy=false core-counter
Counter: 7
Counter: 8
Counter: 9
^C

docker attach --sig-proxy=false core-counter
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="2fdeb-210">Eliminare un contenitore</span><span class="sxs-lookup"><span data-stu-id="2fdeb-210">Delete a container</span></span>

<span data-ttu-id="2fdeb-211">Ai fini di questo articolo, i contenitori che non servono più possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-211">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="2fdeb-212">Eliminare il contenitore creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-212">Delete the container you previously created.</span></span> <span data-ttu-id="2fdeb-213">Se è in esecuzione, arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-213">If the container is running, stop it.</span></span>

```Docker
docker stop core-counter
```

<span data-ttu-id="2fdeb-214">L'esempio seguente elenca tutti i contenitori.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-214">The following example lists all containers.</span></span> <span data-ttu-id="2fdeb-215">Usa poi il comando `docker rm` per eliminare il contenitore e quindi controlla una seconda volta che non ci siano contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-215">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```Docker
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="2fdeb-216">Esecuzione singola</span><span class="sxs-lookup"><span data-stu-id="2fdeb-216">Single run</span></span>

<span data-ttu-id="2fdeb-217">Docker fornisce il comando `docker run` per creare ed eseguire il contenitore con un unico comando.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-217">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="2fdeb-218">Questo comando elimina la necessità di eseguire `docker create` e quindi `docker start`.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-218">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="2fdeb-219">È anche possibile impostare il comando in modo che elimini automaticamente il contenitore quando viene arrestato.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-219">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="2fdeb-220">Ad esempio, usare `docker run -it --rm` per eseguire due operazioni, ossia usare automaticamente il terminale corrente per connettersi al contenitore e quindi, al termine dell'esecuzione, rimuovere il contenitore:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-220">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```Docker
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="2fdeb-221">Il contenitore passa anche i parametri nell'esecuzione dell'app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-221">The container also passes parameters into the execution of the .NET Core app.</span></span> <span data-ttu-id="2fdeb-222">Per indicare all'app .NET Core di contare solo su 3, passare 3.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-222">To instruct the .NET Core app to count only to 3 pass in 3.</span></span>

```Docker
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

<span data-ttu-id="2fdeb-223">Con `docker run -it`, il comando <kbd>CTRL + C</kbd> arresterà il processo in esecuzione nel contenitore, che a sua volta interrompe il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-223">With `docker run -it`, the <kbd>Ctrl+C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="2fdeb-224">Poiché è stato specificato il parametro `--rm`, il contenitore viene eliminato automaticamente quando viene arrestato il processo.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-224">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="2fdeb-225">Verificare che non esista:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-225">Verify that it doesn't exist:</span></span>

```Docker
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="2fdeb-226">Modificare il comando ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="2fdeb-226">Change the ENTRYPOINT</span></span>

<span data-ttu-id="2fdeb-227">Il comando `docker run` consente anche di modificare il comando `ENTRYPOINT` dal *Dockerfile* e di eseguire qualcosa di diverso, ma solo per il contenitore in questione.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-227">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="2fdeb-228">Ad esempio, usare il comando seguente per eseguire `bash` o `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-228">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="2fdeb-229">Modificare il comando in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-229">Edit the command as necessary.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="2fdeb-230">Windows</span><span class="sxs-lookup"><span data-stu-id="2fdeb-230">Windows</span></span>](#tab/windows)

<span data-ttu-id="2fdeb-231">In questo esempio `ENTRYPOINT` viene sostituito con `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-231">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="2fdeb-232">Premere <kbd>CTRL + C</kbd> per terminare il processo e arrestare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-232"><kbd>Ctrl+C</kbd> is pressed to end the process and stop the container.</span></span>

```Docker
docker run -it --rm --entrypoint "cmd.exe" counter-image

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>[<span data-ttu-id="2fdeb-233">Linux</span><span class="sxs-lookup"><span data-stu-id="2fdeb-233">Linux</span></span>](#tab/linux)

<span data-ttu-id="2fdeb-234">In questo esempio `ENTRYPOINT` viene sostituito con `bash`.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-234">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="2fdeb-235">Viene quindi eseguito il comando `exit` che termina il processo e arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-235">The `exit` command is run which ends the process and stop the container.</span></span>

```bash
docker run -it --rm --entrypoint "bash" counter-image
root@b735b9799abf:/App# ls
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.exe  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
root@b735b9799abf:/App# dotnet NetCore.Docker.dll 3
Counter: 1
Counter: 2
Counter: 3
root@b735b9799abf:/App# exit
exit
```

---

## <a name="essential-commands"></a><span data-ttu-id="2fdeb-236">Comandi essenziali</span><span class="sxs-lookup"><span data-stu-id="2fdeb-236">Essential commands</span></span>

<span data-ttu-id="2fdeb-237">Docker dispone di diversi comandi che consentono di creare, gestire e interagire con contenitori e immagini.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-237">Docker has many different commands that create, manage, and interact with containers and images.</span></span> <span data-ttu-id="2fdeb-238">I comandi Docker seguenti sono essenziali per la gestione dei contenitori:</span><span class="sxs-lookup"><span data-stu-id="2fdeb-238">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="2fdeb-239">docker build</span><span class="sxs-lookup"><span data-stu-id="2fdeb-239">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="2fdeb-240">docker run</span><span class="sxs-lookup"><span data-stu-id="2fdeb-240">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="2fdeb-241">docker ps</span><span class="sxs-lookup"><span data-stu-id="2fdeb-241">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="2fdeb-242">docker stop</span><span class="sxs-lookup"><span data-stu-id="2fdeb-242">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="2fdeb-243">docker rm</span><span class="sxs-lookup"><span data-stu-id="2fdeb-243">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="2fdeb-244">docker rmi</span><span class="sxs-lookup"><span data-stu-id="2fdeb-244">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="2fdeb-245">immagine Docker</span><span class="sxs-lookup"><span data-stu-id="2fdeb-245">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="2fdeb-246">Pulizia delle risorse</span><span class="sxs-lookup"><span data-stu-id="2fdeb-246">Clean up resources</span></span>

<span data-ttu-id="2fdeb-247">Durante questa esercitazione sono stati creati contenitori e immagini.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-247">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="2fdeb-248">Se si preferisce, è possibile eliminare queste risorse.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-248">If you want, delete these resources.</span></span> <span data-ttu-id="2fdeb-249">Usare i comandi seguenti per</span><span class="sxs-lookup"><span data-stu-id="2fdeb-249">Use the following commands to</span></span>

01. <span data-ttu-id="2fdeb-250">Elencare tutti i contenitori</span><span class="sxs-lookup"><span data-stu-id="2fdeb-250">List all containers</span></span>

    ```Docker
    docker ps -a
    ```

02. <span data-ttu-id="2fdeb-251">Arrestare i contenitori in esecuzione con il nome.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-251">Stop containers that are running by their name.</span></span>

    ```Docker
    docker stop counter-image
    ```

03. <span data-ttu-id="2fdeb-252">Eliminare il contenitore</span><span class="sxs-lookup"><span data-stu-id="2fdeb-252">Delete the container</span></span>

    ```Docker
    docker rm counter-image
    ```

<span data-ttu-id="2fdeb-253">Eliminare quindi le immagini che non si desidera conservare nel computer.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-253">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="2fdeb-254">Eliminare l'immagine creata dal *Dockerfile* e quindi eliminare l'immagine .NET Core su cui è stato basato il *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-254">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="2fdeb-255">È possibile usare l'**IMAGE ID** o la stringa formattata come **REPOSITORY:TAG**.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-255">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```Docker
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="2fdeb-256">Usare il comando `docker images` per visualizzare un elenco delle immagini installate.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-256">Use the `docker images` command to see a list of images installed.</span></span>

> [!TIP]
> <span data-ttu-id="2fdeb-257">I file di immagine possono essere di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-257">Image files can be large.</span></span> <span data-ttu-id="2fdeb-258">In genere è consigliabile rimuovere i contenitori temporanei creati durante il test e lo sviluppo dell'app.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-258">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="2fdeb-259">Conservare invece le immagini di base con il runtime installato se si prevede di compilare altre immagini basate su quel runtime.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-259">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2fdeb-260">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2fdeb-260">Next steps</span></span>

- [<span data-ttu-id="2fdeb-261">Vedere le informazioni su come distribuire un'applicazione ASP.NET Core in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-261">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="2fdeb-262">Provare l'esercitazione sulla creazione di microservizi ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-262">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="2fdeb-263">Esaminare i servizi di Azure che supportano i contenitori.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-263">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="2fdeb-264">Leggere le informazioni sui comandi del Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-264">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="2fdeb-265">Esplorare gli strumenti per contenitori di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2fdeb-265">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
