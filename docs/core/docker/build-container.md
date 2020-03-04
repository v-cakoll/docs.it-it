---
title: Distribuire un'app in un contenitore con Docker - Esercitazione
description: In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core con Docker.
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e1904430a591b0e74a69d50a53869a130fc0a248
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157830"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="d0467-103">Esercitazione: distribuire un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="d0467-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="d0467-104">Questa esercitazione illustra come compilare un'immagine Docker che contiene un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d0467-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="d0467-105">L'immagine può essere usata per creare contenitori per l'ambiente di sviluppo locale, il cloud privato o il cloud pubblico.</span><span class="sxs-lookup"><span data-stu-id="d0467-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="d0467-106">Si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="d0467-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="d0467-107">Creare e pubblicare un'app .NET Core semplice</span><span class="sxs-lookup"><span data-stu-id="d0467-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="d0467-108">Creare e configurare un Dockerfile per .NET Core</span><span class="sxs-lookup"><span data-stu-id="d0467-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="d0467-109">Creare un'immagine Docker</span><span class="sxs-lookup"><span data-stu-id="d0467-109">Build a Docker image</span></span>
> - <span data-ttu-id="d0467-110">Creare ed eseguire un contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="d0467-110">Create and run a Docker container</span></span>

<span data-ttu-id="d0467-111">L'esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d0467-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="d0467-112">La *piattaforma Docker* usa il *motore Docker* per compilare rapidamente app e inserirle in pacchetti come *immagini Docker*.</span><span class="sxs-lookup"><span data-stu-id="d0467-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="d0467-113">Queste immagini vengono scritte nel formato *Dockerfile* per la distribuzione e l'esecuzione in un contenitore su più livelli.</span><span class="sxs-lookup"><span data-stu-id="d0467-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!TIP]
> <span data-ttu-id="d0467-114">Se si usa un'applicazione ASP.NET Core esistente, vedere l'esercitazione [informazioni su come distribuire un'applicazione ASP.NET Core](/aspnet/core/host-and-deploy/docker/building-net-docker-images) .</span><span class="sxs-lookup"><span data-stu-id="d0467-114">If you're working with an existing ASP.NET Core application, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0467-115">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="d0467-115">Prerequisites</span></span>

<span data-ttu-id="d0467-116">Installare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0467-116">Install the following prerequisites:</span></span>

- <span data-ttu-id="d0467-117">\ [SDK per .NET Core 3,1](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="d0467-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)\</span></span>
<span data-ttu-id="d0467-118">Se .NET Core è già installato, usare il comando `dotnet --info` per determinare quale SDK è in uso.</span><span class="sxs-lookup"><span data-stu-id="d0467-118">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="d0467-119">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="d0467-119">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="d0467-120">Una cartella di lavoro temporanea per il *Dockerfile* e l'app .NET Core di esempio.</span><span class="sxs-lookup"><span data-stu-id="d0467-120">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="d0467-121">In questa esercitazione il nome *Docker-working* viene usato come cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d0467-121">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="d0467-122">Creare un'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="d0467-122">Create .NET Core app</span></span>

<span data-ttu-id="d0467-123">È necessario creare un'app .NET Core che verrà eseguita dal contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="d0467-123">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="d0467-124">Aprire il terminale in uso, creare una cartella di lavoro se non è già stata creata e passare alla cartella.</span><span class="sxs-lookup"><span data-stu-id="d0467-124">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="d0467-125">Nella cartella di lavoro, eseguire il comando seguente per creare un nuovo progetto in una sottodirectory denominata *app*:</span><span class="sxs-lookup"><span data-stu-id="d0467-125">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="d0467-126">La struttura di cartelle sarà simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d0467-126">Your folder tree will look like the following:</span></span>

```
docker-working
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.dgspec.json
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="d0467-127">Il comando `dotnet new` crea una nuova directory denominata *app* e genera un'app "Hello World".</span><span class="sxs-lookup"><span data-stu-id="d0467-127">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="d0467-128">Passare alla cartella *app* ed eseguire il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="d0467-128">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="d0467-129">Verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="d0467-129">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="d0467-130">Il modello predefinito crea un'app che viene visualizzata sul terminale e quindi viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="d0467-130">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="d0467-131">Per questa esercitazione si userà un'app che viene eseguita a ciclo continuo.</span><span class="sxs-lookup"><span data-stu-id="d0467-131">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="d0467-132">Aprire il file *Program.cs* in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="d0467-132">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="d0467-133">Attualmente il file dovrebbe essere simile al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d0467-133">It should currently look like the following code:</span></span>

```csharp
using System;

namespace myapp
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

<span data-ttu-id="d0467-134">Sostituirlo con il codice seguente che conta i numeri ogni secondo:</span><span class="sxs-lookup"><span data-stu-id="d0467-134">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="d0467-135">Salvare il file e testare di nuovo il programma con `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="d0467-135">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="d0467-136">Tenere presente che l'app viene eseguita per un tempo illimitato.</span><span class="sxs-lookup"><span data-stu-id="d0467-136">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="d0467-137">Usare il comando Annulla <kbd>CTRL</kbd>+<kbd>C</kbd> per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="d0467-137">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="d0467-138">Verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="d0467-138">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="d0467-139">Se si passa un numero all'app nella riga di comando, verrà eseguito il conteggio fino a quel numero e quindi l'app verrà chiusa.</span><span class="sxs-lookup"><span data-stu-id="d0467-139">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="d0467-140">Provare con `dotnet run -- 5` per contare fino a cinque.</span><span class="sxs-lookup"><span data-stu-id="d0467-140">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="d0467-141">I parametri dopo `--` non vengono passati al comando `dotnet run` e vengono invece passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0467-141">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="d0467-142">Pubblicare l'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="d0467-142">Publish .NET Core app</span></span>

<span data-ttu-id="d0467-143">Prima di aggiungere l'app .NET Core all'immagine Docker occorre pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="d0467-143">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="d0467-144">Si vuole garantire che il contenitore esegua la versione pubblicata dell'app all'avvio.</span><span class="sxs-lookup"><span data-stu-id="d0467-144">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="d0467-145">Dalla cartella di lavoro accedere alla cartella *app* nel codice sorgente di esempio ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d0467-145">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="d0467-146">Questo comando compila l'app nella cartella *publish*.</span><span class="sxs-lookup"><span data-stu-id="d0467-146">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="d0467-147">Il percorso della cartella *publish* dalla cartella di lavoro deve essere `.\app\bin\Release\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="d0467-147">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp3.1\publish\`</span></span>

<span data-ttu-id="d0467-148">Dalla cartella dell' *app* , ottenere un elenco di directory della cartella di pubblicazione per verificare che il file *MyApp. dll* sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="d0467-148">From the *app* folder, get a directory listing of the publish folder to verify that the *myapp.dll* file was created.</span></span>

```console
> dir bin\Release\netcoreapp3.1\publish

    Directory:  C:\docker-working\app\bin\Release\netcoreapp3.1\publish

01/09/2020  11:41 AM    <DIR>          .
01/09/2020  11:41 AM    <DIR>          ..
01/09/2020  11:41 AM               407 myapp.deps.json
01/09/2020  12:15 PM             4,608 myapp.dll
01/09/2020  12:15 PM           169,984 myapp.exe
01/09/2020  12:15 PM               736 myapp.pdb
01/09/2020  11:41 AM               154 myapp.runtimeconfig.json
```

<span data-ttu-id="d0467-149">Se si usa Linux o macOS, usare il comando `ls` per ottenere un elenco di directory e verificare che il file *MyApp. dll* sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="d0467-149">If you're using Linux or macOS, use the `ls` command to get a directory listing and verify that the *myapp.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="d0467-150">Creare il Dockerfile</span><span class="sxs-lookup"><span data-stu-id="d0467-150">Create the Dockerfile</span></span>

<span data-ttu-id="d0467-151">Il file *Dockerfile* viene usato dal comando `docker build` per creare un'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-151">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="d0467-152">Si tratta di un file di testo denominato *Dockerfile* che non dispone di un'estensione.</span><span class="sxs-lookup"><span data-stu-id="d0467-152">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="d0467-153">Nel terminale passare alla cartella di lavoro creata all'inizio.</span><span class="sxs-lookup"><span data-stu-id="d0467-153">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="d0467-154">Creare un file con nome *Dockerfile* nella cartella di lavoro e aprirlo in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="d0467-154">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="d0467-155">A seconda del tipo di applicazione che si intende distribuire, scegliere il runtime di ASP.NET Core o il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d0467-155">Depending on the type of application you're going to containerize, you'll choose either the ASP.NET Core runtime or the .NET Core runtime.</span></span> <span data-ttu-id="d0467-156">In caso di dubbi, scegliere il runtime di ASP.NET Core, che include il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d0467-156">When in doubt, choose the ASP.NET Core runtime, which includes the .NET Core runtime.</span></span> <span data-ttu-id="d0467-157">Questa esercitazione userà l'immagine di runtime ASP.NET Core, ma l'applicazione creata nelle sezioni precedenti è un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d0467-157">This tutorial will use the ASP.NET Core runtime image, but the application created in the previous sections is an .NET Core application.</span></span>

- <span data-ttu-id="d0467-158">ASP.NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="d0467-158">ASP.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- <span data-ttu-id="d0467-159">Runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d0467-159">.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

<span data-ttu-id="d0467-160">Il comando `FROM` indica a Docker di estrarre l'immagine con tag **3,1** dal repository specificato.</span><span class="sxs-lookup"><span data-stu-id="d0467-160">The `FROM` command tells Docker to pull down the image tagged **3.1** from the specified repository.</span></span> <span data-ttu-id="d0467-161">Assicurarsi di eseguire il pull della versione runtime corrispondente al runtime di destinazione dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="d0467-161">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="d0467-162">Ad esempio, l'app creata nella sezione precedente usava .NET Core 3,1 SDK e l'immagine di base a cui si fa riferimento in *Dockerfile* è contrassegnata con **3,1**.</span><span class="sxs-lookup"><span data-stu-id="d0467-162">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="d0467-163">Salvare il file *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="d0467-163">Save the *Dockerfile* file.</span></span> <span data-ttu-id="d0467-164">La struttura directory della cartella di lavoro deve avere un aspetto simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="d0467-164">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="d0467-165">Alcuni file e directory nei livelli più profondi sono stati tagliati per risparmiare spazio nell'articolo:</span><span class="sxs-lookup"><span data-stu-id="d0467-165">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp3.1
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.exe
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="d0467-166">Dal terminale eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d0467-166">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="d0467-167">Docker elaborerà ogni riga nel *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="d0467-167">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="d0467-168">Il punto `.` nel comando `docker build` indica a Docker di usare la cartella corrente per trovare un *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="d0467-168">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="d0467-169">Questo comando compila un'immagine e crea un repository locale denominato **myimage** che punta a tale immagine.</span><span class="sxs-lookup"><span data-stu-id="d0467-169">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="d0467-170">Dopo l'esecuzione del comando, eseguire `docker images` per visualizzare un elenco delle immagini installate:</span><span class="sxs-lookup"><span data-stu-id="d0467-170">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="d0467-171">Come si può notare, le due immagini condividono lo stesso valore di **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="d0467-171">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="d0467-172">Il valore delle due immagini è lo stesso perché l'unico comando nel *Dockerfile* indicava di basare la nuova immagine su un'immagine esistente.</span><span class="sxs-lookup"><span data-stu-id="d0467-172">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="d0467-173">Ora si aggiungeranno due comandi al *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="d0467-173">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="d0467-174">Ogni comando crea un nuovo livello immagine con il comando finale che rappresenta l'immagine a cui punta la voce del repository di **Immagini** .</span><span class="sxs-lookup"><span data-stu-id="d0467-174">Each command creates a new image layer with the final command representing the image the **myimage** repository entry points to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="d0467-175">Il comando `COPY` indica a Docker di copiare la cartella specificata nel computer in una cartella nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-175">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="d0467-176">In questo esempio la cartella *publish* viene copiata in una cartella denominata *app* nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-176">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="d0467-177">Il comando successivo, `ENTRYPOINT`, indica a Docker di configurare il contenitore in modo che venga eseguito come un eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d0467-177">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="d0467-178">All'avvio del contenitore viene eseguito il comando `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="d0467-178">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="d0467-179">Al termine del comando, il contenitore si arresta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d0467-179">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="d0467-180">Dal terminale eseguire `docker build -t myimage -f Dockerfile .`, quindi dopo il completamento del comando eseguire `docker images`.</span><span class="sxs-lookup"><span data-stu-id="d0467-180">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  1.624MB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> 38db0eb8f648
Step 2/3 : COPY app/bin/Release/netcoreapp3.1/publish/ app/
 ---> 37873673e468
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in d8deb7b3aa9e
Removing intermediate container d8deb7b3aa9e
 ---> 0d602ca35c1d
Successfully built 0d602ca35c1d
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              0d602ca35c1d        4 seconds ago       346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="d0467-181">Ogni comando nel *Dockerfile* ha generato un livello e ha creato un **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="d0467-181">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="d0467-182">L'**IMAGE ID** finale è **ddcc6646461b** (l'utente ne vedrà uno diverso) e successivamente si creerà un contenitore basato su questa immagine.</span><span class="sxs-lookup"><span data-stu-id="d0467-182">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="d0467-183">Creare un contenitore</span><span class="sxs-lookup"><span data-stu-id="d0467-183">Create a container</span></span>

<span data-ttu-id="d0467-184">Ora che si dispone di un'immagine che contiene l'app, è possibile creare un contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-184">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="d0467-185">Lo si può fare in due modi.</span><span class="sxs-lookup"><span data-stu-id="d0467-185">You can create a container in two ways.</span></span> <span data-ttu-id="d0467-186">Prima di tutto, creare un nuovo contenitore arrestato.</span><span class="sxs-lookup"><span data-stu-id="d0467-186">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

<span data-ttu-id="d0467-187">Il comando `docker create` precedente creerà un contenitore basato sull'immagine **myimage**.</span><span class="sxs-lookup"><span data-stu-id="d0467-187">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="d0467-188">L'output del comando mostra il **CONTAINER ID** (diverso da quello visualizzato dall'utente) del contenitore creato.</span><span class="sxs-lookup"><span data-stu-id="d0467-188">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="d0467-189">Per visualizzare un elenco di *tutti* i contenitori, usare il comando `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="d0467-189">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a><span data-ttu-id="d0467-190">Gestire il contenitore</span><span class="sxs-lookup"><span data-stu-id="d0467-190">Manage the container</span></span>

<span data-ttu-id="d0467-191">A ogni contenitore è assegnato un nome casuale che può essere usato per fare riferimento a tale istanza di contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-191">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="d0467-192">Ad esempio, il contenitore creato automaticamente sceglie il nome **gallant_lehmann** (il nome sarà diverso) e tale nome potrà essere usato per avviare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-192">For example, the container that was created automatically chose the name **gallant_lehmann** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="d0467-193">Per sostituire il nome automatico con un nome specifico occorre usare il parametro `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="d0467-193">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="d0467-194">L'esempio seguente usa il comando `docker start` per avviare il contenitore e quindi usa il comando `docker ps` per visualizzare solo i contenitori in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="d0467-194">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

<span data-ttu-id="d0467-195">Analogamente, il comando `docker stop` arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-195">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="d0467-196">Nell'esempio seguente viene usato il comando `docker stop` per arrestare il contenitore, quindi viene usato il comando `docker ps` per indicare che non è in esecuzione alcun contenitore:</span><span class="sxs-lookup"><span data-stu-id="d0467-196">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="d0467-197">Connettersi a un contenitore</span><span class="sxs-lookup"><span data-stu-id="d0467-197">Connect to a container</span></span>

<span data-ttu-id="d0467-198">Quando un contenitore è in esecuzione, è possibile connettersi ad esso per visualizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="d0467-198">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="d0467-199">Usare i comandi `docker start` e `docker attach` per avviare il contenitore e osservare il flusso di output.</span><span class="sxs-lookup"><span data-stu-id="d0467-199">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="d0467-200">In questo esempio, la sequenza di tasti <kbd>CTRL + C</kbd> viene usata per scollegare il contenitore in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0467-200">In this example, the <kbd>CTRL + C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="d0467-201">Questa sequenza di tasti può effettivamente terminare il processo nel contenitore, che arresterà il contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-201">This keystroke may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="d0467-202">Il parametro `--sig-proxy=false` assicura che <kbd>CTRL+C</kbd> non arresti il processo nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-202">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="d0467-203">Dopo essersi scollegati dal contenitore, collegarsi di nuovo per verificare che sia ancora in esecuzione e continui a eseguire il conteggio.</span><span class="sxs-lookup"><span data-stu-id="d0467-203">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker attach --sig-proxy=false gallant_lehmann
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false gallant_lehmann
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="d0467-204">Eliminare un contenitore</span><span class="sxs-lookup"><span data-stu-id="d0467-204">Delete a container</span></span>

<span data-ttu-id="d0467-205">Ai fini di questo articolo, i contenitori che non servono più possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="d0467-205">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="d0467-206">Eliminare il contenitore creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d0467-206">Delete the container you previously created.</span></span> <span data-ttu-id="d0467-207">Se è in esecuzione, arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="d0467-207">If the container is running, stop it.</span></span>

```console
> docker stop gallant_lehmann
```

<span data-ttu-id="d0467-208">L'esempio seguente elenca tutti i contenitori.</span><span class="sxs-lookup"><span data-stu-id="d0467-208">The following example lists all containers.</span></span> <span data-ttu-id="d0467-209">Usa poi il comando `docker rm` per eliminare il contenitore e quindi controlla una seconda volta che non ci siano contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0467-209">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="d0467-210">Esecuzione singola</span><span class="sxs-lookup"><span data-stu-id="d0467-210">Single run</span></span>

<span data-ttu-id="d0467-211">Docker fornisce il comando `docker run` per creare ed eseguire il contenitore con un unico comando.</span><span class="sxs-lookup"><span data-stu-id="d0467-211">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="d0467-212">Questo comando elimina la necessità di eseguire `docker create` e quindi `docker start`.</span><span class="sxs-lookup"><span data-stu-id="d0467-212">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="d0467-213">È anche possibile impostare il comando in modo che elimini automaticamente il contenitore quando viene arrestato.</span><span class="sxs-lookup"><span data-stu-id="d0467-213">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="d0467-214">Ad esempio, usare `docker run -it --rm` per eseguire due operazioni, ossia usare automaticamente il terminale corrente per connettersi al contenitore e quindi, al termine dell'esecuzione, rimuovere il contenitore:</span><span class="sxs-lookup"><span data-stu-id="d0467-214">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="d0467-215">Con `docker run -it`, il comando <kbd>CTRL + C</kbd> arresta il processo in esecuzione nel contenitore, cosa che a sua volta arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-215">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="d0467-216">Poiché è stato specificato il parametro `--rm`, il contenitore viene eliminato automaticamente quando viene arrestato il processo.</span><span class="sxs-lookup"><span data-stu-id="d0467-216">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="d0467-217">Verificare che non esista:</span><span class="sxs-lookup"><span data-stu-id="d0467-217">Verify that it doesn't exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="d0467-218">Modificare il comando ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="d0467-218">Change the ENTRYPOINT</span></span>

<span data-ttu-id="d0467-219">Il comando `docker run` consente anche di modificare il comando `ENTRYPOINT` dal *Dockerfile* e di eseguire qualcosa di diverso, ma solo per il contenitore in questione.</span><span class="sxs-lookup"><span data-stu-id="d0467-219">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="d0467-220">Ad esempio, usare il comando seguente per eseguire `bash` o `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="d0467-220">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="d0467-221">Modificare il comando in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d0467-221">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="d0467-222">Windows</span><span class="sxs-lookup"><span data-stu-id="d0467-222">Windows</span></span>

<span data-ttu-id="d0467-223">In questo esempio `ENTRYPOINT` viene sostituito con `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="d0467-223">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="d0467-224">Premere <kbd>CTRL</kbd>+<kbd>C</kbd> per terminare il processo e arrestare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-224"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

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

#### <a name="linux"></a><span data-ttu-id="d0467-225">Linux</span><span class="sxs-lookup"><span data-stu-id="d0467-225">Linux</span></span>

<span data-ttu-id="d0467-226">In questo esempio `ENTRYPOINT` viene sostituito con `bash`.</span><span class="sxs-lookup"><span data-stu-id="d0467-226">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="d0467-227">Viene quindi eseguito il comando `quit` che termina il processo e arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-227">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="d0467-228">Comandi essenziali</span><span class="sxs-lookup"><span data-stu-id="d0467-228">Essential commands</span></span>

<span data-ttu-id="d0467-229">Docker offre numerosi comandi che consentono di eseguire operazioni diverse sul contenitore e sulle immagini.</span><span class="sxs-lookup"><span data-stu-id="d0467-229">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="d0467-230">I comandi Docker seguenti sono essenziali per la gestione dei contenitori:</span><span class="sxs-lookup"><span data-stu-id="d0467-230">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="d0467-231">docker build</span><span class="sxs-lookup"><span data-stu-id="d0467-231">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="d0467-232">docker run</span><span class="sxs-lookup"><span data-stu-id="d0467-232">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="d0467-233">docker ps</span><span class="sxs-lookup"><span data-stu-id="d0467-233">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="d0467-234">docker stop</span><span class="sxs-lookup"><span data-stu-id="d0467-234">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="d0467-235">docker rm</span><span class="sxs-lookup"><span data-stu-id="d0467-235">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="d0467-236">docker rmi</span><span class="sxs-lookup"><span data-stu-id="d0467-236">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="d0467-237">docker image</span><span class="sxs-lookup"><span data-stu-id="d0467-237">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="d0467-238">Pulire le risorse</span><span class="sxs-lookup"><span data-stu-id="d0467-238">Clean up resources</span></span>

<span data-ttu-id="d0467-239">Durante questa esercitazione sono stati creati contenitori e immagini.</span><span class="sxs-lookup"><span data-stu-id="d0467-239">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="d0467-240">Se si preferisce, è possibile eliminare queste risorse.</span><span class="sxs-lookup"><span data-stu-id="d0467-240">If you want, delete these resources.</span></span> <span data-ttu-id="d0467-241">Usare i comandi seguenti per</span><span class="sxs-lookup"><span data-stu-id="d0467-241">Use the following commands to</span></span>

01. <span data-ttu-id="d0467-242">Elencare tutti i contenitori</span><span class="sxs-lookup"><span data-stu-id="d0467-242">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="d0467-243">Arrestare i contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0467-243">Stop containers that are running.</span></span> <span data-ttu-id="d0467-244">`CONTAINER_NAME` rappresenta il nome assegnato automaticamente al contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-244">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="d0467-245">Eliminare il contenitore</span><span class="sxs-lookup"><span data-stu-id="d0467-245">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="d0467-246">Eliminare quindi le immagini che non si desidera conservare nel computer.</span><span class="sxs-lookup"><span data-stu-id="d0467-246">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="d0467-247">Eliminare l'immagine creata dal *Dockerfile* e quindi eliminare l'immagine .NET Core su cui è stato basato il *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="d0467-247">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="d0467-248">È possibile usare l'**IMAGE ID** o la stringa formattata come **REPOSITORY:TAG**.</span><span class="sxs-lookup"><span data-stu-id="d0467-248">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="d0467-249">Usare il comando `docker images` per visualizzare un elenco delle immagini installate.</span><span class="sxs-lookup"><span data-stu-id="d0467-249">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="d0467-250">I file di immagine possono essere di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d0467-250">Image files can be large.</span></span> <span data-ttu-id="d0467-251">In genere è consigliabile rimuovere i contenitori temporanei creati durante il test e lo sviluppo dell'app.</span><span class="sxs-lookup"><span data-stu-id="d0467-251">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="d0467-252">Conservare invece le immagini di base con il runtime installato se si prevede di compilare altre immagini basate su quel runtime.</span><span class="sxs-lookup"><span data-stu-id="d0467-252">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0467-253">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d0467-253">Next steps</span></span>

- [<span data-ttu-id="d0467-254">Vedere le informazioni su come distribuire un'applicazione ASP.NET Core in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="d0467-254">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="d0467-255">Provare l'esercitazione sulla creazione di microservizi ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d0467-255">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="d0467-256">Esaminare i servizi di Azure che supportano i contenitori.</span><span class="sxs-lookup"><span data-stu-id="d0467-256">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="d0467-257">Leggere le informazioni sui comandi del Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="d0467-257">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="d0467-258">Esplorare gli strumenti per contenitori di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d0467-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
