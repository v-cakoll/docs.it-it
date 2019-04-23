---
title: Distribuire un'app in un contenitore con Docker - Esercitazione
description: In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core in un contenitore con Docker.
ms.date: 04/10/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: fcbac0e0d17d2481d42e715a7f2790586e31d085
ms.sourcegitcommit: 8080271c246b57f4fb68c28369634bff46843424
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2019
ms.locfileid: "59553836"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="34269-103">Esercitazione: Distribuire un'app .NET Core in un contenitore</span><span class="sxs-lookup"><span data-stu-id="34269-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="34269-104">Questa esercitazione illustra come compilare un'immagine Docker che contiene un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="34269-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="34269-105">L'immagine può essere usata per creare contenitori per l'ambiente di sviluppo locale, il cloud privato o il cloud pubblico.</span><span class="sxs-lookup"><span data-stu-id="34269-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="34269-106">Si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="34269-106">You'll learn to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="34269-107">Creare e pubblicare un'app .NET Core semplice</span><span class="sxs-lookup"><span data-stu-id="34269-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="34269-108">Creare e configurare un Dockerfile per .NET Core</span><span class="sxs-lookup"><span data-stu-id="34269-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="34269-109">Creare un'immagine Docker</span><span class="sxs-lookup"><span data-stu-id="34269-109">Build a Docker image</span></span>
> * <span data-ttu-id="34269-110">Creare ed eseguire un contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="34269-110">Create and run a Docker container</span></span>

<span data-ttu-id="34269-111">L'esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="34269-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="34269-112">La *piattaforma Docker* usa il *motore Docker* per compilare rapidamente app e inserirle in pacchetti come *immagini Docker*.</span><span class="sxs-lookup"><span data-stu-id="34269-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="34269-113">Queste immagini vengono scritte nel formato *Dockerfile* per la distribuzione e l'esecuzione in un contenitore su più livelli.</span><span class="sxs-lookup"><span data-stu-id="34269-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34269-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="34269-114">Prerequisites</span></span>

<span data-ttu-id="34269-115">Installare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="34269-115">Install the following prerequisites:</span></span>

- <span data-ttu-id="34269-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span><span class="sxs-lookup"><span data-stu-id="34269-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span></span>
<span data-ttu-id="34269-117">Se .NET Core è già installato, usare il comando `dotnet --info` per determinare quale SDK è in uso.</span><span class="sxs-lookup"><span data-stu-id="34269-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="34269-118">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="34269-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="34269-119">Una directory di lavoro temporanea per il *Dockerfile* e l'app .NET Core di esempio.</span><span class="sxs-lookup"><span data-stu-id="34269-119">A temporary working directory for the *Dockerfile* and .NET Core example app.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="34269-120">Usare la versione 2.2 dell'SDK</span><span class="sxs-lookup"><span data-stu-id="34269-120">Use SDK version 2.2</span></span>

<span data-ttu-id="34269-121">Se si usa un SDK più recente, ad esempio la versione 3.0, assicurarsi che nell'app venga forzato l'uso della versione 2.2 dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="34269-121">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="34269-122">Creare un file denominato `global.json` nella directory di lavoro e incollarlo nel codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="34269-122">Create a file named `global.json` in your working directory and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="34269-123">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="34269-123">Save this file.</span></span> <span data-ttu-id="34269-124">La presenza del file forzerà .NET Core a usare la versione 2.2 per qualsiasi comando `dotnet` chiamato da questa directory e dalle relative sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="34269-124">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this directory and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="34269-125">Creare l'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="34269-125">Create .NET Core app</span></span>

<span data-ttu-id="34269-126">È necessario creare un'app .NET Core che verrà eseguita dal contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="34269-126">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="34269-127">Aprire il terminale, creare una directory di lavoro e accedervi.</span><span class="sxs-lookup"><span data-stu-id="34269-127">Open your terminal, create a working directory, and enter it.</span></span> <span data-ttu-id="34269-128">Nella directory di lavoro eseguire il comando seguente per creare un nuovo progetto in una sottodirectory denominata app:</span><span class="sxs-lookup"><span data-stu-id="34269-128">In the working directory, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="34269-129">Questo comando crea una nuova directory denominata *app* e genera un'app "Hello World".</span><span class="sxs-lookup"><span data-stu-id="34269-129">That command creates a new directory named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="34269-130">È possibile testare l'app per vedere come funziona.</span><span class="sxs-lookup"><span data-stu-id="34269-130">You can test this app to see what it does.</span></span> <span data-ttu-id="34269-131">Entrare nella directory *app* ed eseguire il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="34269-131">Enter the *app* directory and execute the command `dotnet run`.</span></span> <span data-ttu-id="34269-132">Verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="34269-132">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="34269-133">Il modello predefinito crea un'app che viene visualizzata sul terminale e quindi viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="34269-133">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="34269-134">Per questa esercitazione si userà un'app che viene eseguita a ciclo continuo.</span><span class="sxs-lookup"><span data-stu-id="34269-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="34269-135">Aprire il file **Program.cs** in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="34269-135">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="34269-136">Attualmente il file dovrebbe essere simile al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="34269-136">It should currently look like the following code:</span></span>

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

<span data-ttu-id="34269-137">Sostituirlo con il codice seguente che conta i numeri ogni secondo:</span><span class="sxs-lookup"><span data-stu-id="34269-137">Replace the file with the following code that counts numbers every second:</span></span>

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
            while(max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="34269-138">Salvare il file e testare di nuovo il programma con `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="34269-138">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="34269-139">Tenere presente che l'app viene eseguita per un tempo illimitato.</span><span class="sxs-lookup"><span data-stu-id="34269-139">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="34269-140">Usare il comando di annullamento <kbd>CTRL + C</kbd> per arrestarla.</span><span class="sxs-lookup"><span data-stu-id="34269-140">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="34269-141">Verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="34269-141">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="34269-142">Se si passa un numero all'app nella riga di comando, verrà eseguito il conteggio fino a quel numero e quindi l'app verrà chiusa.</span><span class="sxs-lookup"><span data-stu-id="34269-142">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="34269-143">Provare con `dotnet run -- 5` per contare fino a cinque.</span><span class="sxs-lookup"><span data-stu-id="34269-143">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="34269-144">Tutti i parametri che seguono `--` vengono passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="34269-144">Any parameters after `--` are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="34269-145">Pubblicare l'app .NET Core</span><span class="sxs-lookup"><span data-stu-id="34269-145">Publish .NET Core app</span></span>

<span data-ttu-id="34269-146">Prima di aggiungere l'app .NET Core all'immagine Docker occorre pubblicarla.</span><span class="sxs-lookup"><span data-stu-id="34269-146">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="34269-147">Il contenitore eseguirà la versione pubblicata dell'app all'avvio.</span><span class="sxs-lookup"><span data-stu-id="34269-147">The container will execute the published version of the app when it's started.</span></span>

<span data-ttu-id="34269-148">Dalla directory di lavoro accedere alla directory **app** nel codice sorgente di esempio ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="34269-148">From the working directory, enter the **app** directory with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="34269-149">Questo comando compila l'app nella cartella **publish** all'interno della cartella di output dell'app.</span><span class="sxs-lookup"><span data-stu-id="34269-149">This command compiles your app to the **publish** folder in the output folder of your app.</span></span> <span data-ttu-id="34269-150">Il percorso della cartella **publish** dalla directory di lavoro deve essere `.\app\bin\Release\netcoreapp2.2\publish\`</span><span class="sxs-lookup"><span data-stu-id="34269-150">The path to the **publish** folder from the working directory should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="34269-151">Ottenere una visualizzazione directory della cartella publish per verificare che **myapp.dll** sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="34269-151">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="34269-152">Dalla directory **app** eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="34269-152">From the **app** directory, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\path-to-working-dir\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/path-to-working-dir/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

<span data-ttu-id="34269-153">Nel terminale salire di una directory fino alla directory di lavoro.</span><span class="sxs-lookup"><span data-stu-id="34269-153">In your terminal, go up a directory to the working directory.</span></span>

## <a name="create-the-dockerfile"></a><span data-ttu-id="34269-154">Creare il Dockerfile</span><span class="sxs-lookup"><span data-stu-id="34269-154">Create the Dockerfile</span></span>

<span data-ttu-id="34269-155">Il file *Dockerfile* viene usato dal comando `docker build` per creare un'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="34269-156">È un file di testo non crittografato denominato *Dockerfile*, senza estensione.</span><span class="sxs-lookup"><span data-stu-id="34269-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span> <span data-ttu-id="34269-157">Creare un file denominato *Dockerfile* nella directory di lavoro e aprirlo in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="34269-157">Create a file named *Dockerfile* in your working directory and open it in a text editor.</span></span> <span data-ttu-id="34269-158">Aggiungere il comando seguente come prima riga del file:</span><span class="sxs-lookup"><span data-stu-id="34269-158">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="34269-159">Il comando `FROM` indica a Docker di scaricare l'immagine con tag **2.2** dal repository **mcr.microsoft.com/dotnet/core/runtime**.</span><span class="sxs-lookup"><span data-stu-id="34269-159">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="34269-160">Assicurarsi di scaricare il runtime di .NET Core corrispondente al runtime dell'SDK in uso.</span><span class="sxs-lookup"><span data-stu-id="34269-160">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="34269-161">Ad esempio, l'app creata nella sezione precedente usava .NET Core 2.2 SDK e ha creato un'app destinata a .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="34269-161">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="34269-162">L'immagine di base a cui viene fatto riferimento nel *Dockerfile* è quindi indentificata dal tag **2.2**.</span><span class="sxs-lookup"><span data-stu-id="34269-162">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="34269-163">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="34269-163">Save the file.</span></span> <span data-ttu-id="34269-164">Dal terminale eseguire `docker build -t myimage .`, che indica a Docker di elaborare ogni riga del *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="34269-164">From your terminal, run `docker build -t myimage .` and Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="34269-165">Il punto `.` nel comando `docker build` indica a Docker di usare la directory corrente per trovare un *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="34269-165">The `.` in the `docker build` command tells docker to use the current directory to find a *Dockerfile*.</span></span> <span data-ttu-id="34269-166">Questo comando compila un'immagine e crea un repository locale denominato **myimage** che punta a tale immagine.</span><span class="sxs-lookup"><span data-stu-id="34269-166">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="34269-167">Dopo l'esecuzione del comando, eseguire `docker images` per visualizzare un elenco delle immagini installate:</span><span class="sxs-lookup"><span data-stu-id="34269-167">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="34269-168">Come si può notare, le due immagini condividono lo stesso valore di **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="34269-168">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="34269-169">Il valore delle due immagini è lo stesso perché l'unico comando nel *Dockerfile* indicava di basare la nuova immagine su un'immagine esistente.</span><span class="sxs-lookup"><span data-stu-id="34269-169">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="34269-170">Ora si aggiungeranno due comandi al *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="34269-170">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="34269-171">Ogni comando crea un nuovo livello di immagine con il comando finale che rappresenta l'immagine a cui il repository **myimage** punterà.</span><span class="sxs-lookup"><span data-stu-id="34269-171">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="34269-172">Il comando `COPY` indica a Docker di copiare la cartella specificata nel computer in una cartella nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-172">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="34269-173">In questo esempio la cartella **publish** viene copiata in una cartella denominata **app** nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-173">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="34269-174">Il comando successivo, `ENTRYPOINT`, indica a Docker di configurare il contenitore in modo che venga eseguito come un eseguibile.</span><span class="sxs-lookup"><span data-stu-id="34269-174">The next command, `ENTRYPOINT`, tells docker to configure the container to run as an executable.</span></span> <span data-ttu-id="34269-175">All'avvio del contenitore viene eseguito il comando `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="34269-175">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="34269-176">Al termine del comando, il contenitore si arresta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="34269-176">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="34269-177">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="34269-177">Save the file.</span></span> <span data-ttu-id="34269-178">Dal terminale eseguire `docker build -t myimage .`, quindi dopo il completamento del comando eseguire `docker images`.</span><span class="sxs-lookup"><span data-stu-id="34269-178">From your terminal, run `docker build -t myimage .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest


> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="34269-179">Ogni comando nel *Dockerfile* ha generato un livello e ha creato un **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="34269-179">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="34269-180">L'**IMAGE ID** finale è **ddcc6646461b** (l'utente ne vedrà uno diverso) e successivamente si creerà un contenitore basato su questa immagine.</span><span class="sxs-lookup"><span data-stu-id="34269-180">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="34269-181">Creare un contenitore</span><span class="sxs-lookup"><span data-stu-id="34269-181">Create a container</span></span>

<span data-ttu-id="34269-182">Ora che si dispone di un'immagine che contiene l'app, è possibile creare un contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-182">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="34269-183">Lo si può fare in due modi.</span><span class="sxs-lookup"><span data-stu-id="34269-183">You can create a container in two ways.</span></span> <span data-ttu-id="34269-184">Prima di tutto, creare un nuovo contenitore arrestato.</span><span class="sxs-lookup"><span data-stu-id="34269-184">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="34269-185">Il comando `docker create` precedente creerà un contenitore basato sull'immagine **myimage**.</span><span class="sxs-lookup"><span data-stu-id="34269-185">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="34269-186">L'output del comando mostra il **CONTAINER ID** (diverso da quello visualizzato dall'utente) del contenitore creato.</span><span class="sxs-lookup"><span data-stu-id="34269-186">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="34269-187">Per visualizzare un elenco di *tutti* i contenitori, usare il comando `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="34269-187">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="34269-188">Gestire il contenitore</span><span class="sxs-lookup"><span data-stu-id="34269-188">Manage the container</span></span>

<span data-ttu-id="34269-189">A ogni contenitore è assegnato un nome casuale che può essere usato per fare riferimento a tale istanza di contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-189">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="34269-190">Ad esempio, per il contenitore creato automaticamente è stato scelto il nome **boring_matsumoto** (l'utente vedrà un nome diverso) e quel nome può essere usato per avviare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-190">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="34269-191">Per sostituire il nome automatico con un nome specifico occorre usare il parametro `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="34269-191">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="34269-192">L'esempio seguente usa il comando `docker start` per avviare il contenitore e quindi usa il comando `docker ps` per visualizzare solo i contenitori in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="34269-192">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="34269-193">Analogamente, il comando `docker stop` arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-193">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="34269-194">L'esempio seguente usa il comando `docker stop` per arrestare il contenitore e quindi usa il comando `docker ps` per mostrare che non è in esecuzione alcun contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-194">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="34269-195">Connettersi a un contenitore</span><span class="sxs-lookup"><span data-stu-id="34269-195">Connect to a container</span></span>

<span data-ttu-id="34269-196">Quando un contenitore è in esecuzione, è possibile connettersi ad esso per visualizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="34269-196">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="34269-197">Usare i comandi `docker start` e `docker attach` per avviare il contenitore e osservare il flusso di output.</span><span class="sxs-lookup"><span data-stu-id="34269-197">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="34269-198">In questo esempio viene usato il comando <kbd>CTRL + C</kbd> per scollegarsi dal contenitore in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34269-198">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="34269-199">Questo comando può effettivamente terminare il processo nel contenitore, arrestando il contenitore stesso.</span><span class="sxs-lookup"><span data-stu-id="34269-199">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="34269-200">Il parametro `--sig-proxy=false` assicura che <kbd>CTRL + C</kbd> non arresti il processo nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-200">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="34269-201">Dopo essersi scollegati dal contenitore, collegarsi di nuovo per verificare che sia ancora in esecuzione e continui a eseguire il conteggio.</span><span class="sxs-lookup"><span data-stu-id="34269-201">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="34269-202">Eliminare un contenitore</span><span class="sxs-lookup"><span data-stu-id="34269-202">Delete a container</span></span>

<span data-ttu-id="34269-203">Ai fini di questo articolo, i contenitori che non servono più possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="34269-203">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="34269-204">Eliminare il contenitore creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="34269-204">Delete the container you previously created.</span></span> <span data-ttu-id="34269-205">Se è in esecuzione, arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="34269-205">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="34269-206">L'esempio seguente elenca tutti i contenitori.</span><span class="sxs-lookup"><span data-stu-id="34269-206">The following example lists all containers.</span></span> <span data-ttu-id="34269-207">Usa poi il comando `docker rm` per eliminare il contenitore e quindi controlla una seconda volta che non ci siano contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34269-207">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="34269-208">Esecuzione singola</span><span class="sxs-lookup"><span data-stu-id="34269-208">Single run</span></span>

<span data-ttu-id="34269-209">Docker fornisce il comando `docker run` per creare ed eseguire il contenitore con un unico comando.</span><span class="sxs-lookup"><span data-stu-id="34269-209">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="34269-210">Questo comando elimina la necessità di eseguire `docker create` e quindi `docker start`.</span><span class="sxs-lookup"><span data-stu-id="34269-210">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="34269-211">È anche possibile impostare il comando in modo che elimini automaticamente il contenitore quando viene arrestato.</span><span class="sxs-lookup"><span data-stu-id="34269-211">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="34269-212">Ad esempio, usare `docker run -it --rm` per eseguire due operazioni, ossia usare automaticamente il terminale corrente per connettersi al contenitore e quindi, al termine dell'esecuzione, rimuovere il contenitore:</span><span class="sxs-lookup"><span data-stu-id="34269-212">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="34269-213">Con `docker run -it`, il comando <kbd>CTRL + C</kbd> arresta il processo in esecuzione nel contenitore, cosa che a sua volta arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-213">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="34269-214">Poiché è stato specificato il parametro `--rm`, il contenitore viene eliminato automaticamente quando viene arrestato il processo.</span><span class="sxs-lookup"><span data-stu-id="34269-214">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="34269-215">Verificare che non esista:</span><span class="sxs-lookup"><span data-stu-id="34269-215">Verify that it does not exist:</span></span>

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="34269-216">Modificare il comando ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="34269-216">Change the ENTRYPOINT</span></span>

<span data-ttu-id="34269-217">Il comando `docker run` consente anche di modificare il comando `ENTRYPOINT` dal *Dockerfile* e di eseguire qualcosa di diverso, ma solo per il contenitore in questione.</span><span class="sxs-lookup"><span data-stu-id="34269-217">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="34269-218">Ad esempio, usare il comando seguente per eseguire `bash` o `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="34269-218">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="34269-219">Modificare il comando in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="34269-219">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="34269-220">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="34269-220">Windows</span></span>
<span data-ttu-id="34269-221">In questo esempio `ENTRYPOINT` viene sostituito con `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="34269-221">In this example the `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="34269-222">Si preme quindi <kbd>CTRL + C</kbd> per terminare il processo e arrestare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-222"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="34269-223">Linux</span><span class="sxs-lookup"><span data-stu-id="34269-223">Linux</span></span>

<span data-ttu-id="34269-224">In questo esempio `ENTRYPOINT` viene sostituito con `bash`.</span><span class="sxs-lookup"><span data-stu-id="34269-224">In this example the `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="34269-225">Viene quindi eseguito il comando `quit` che termina il processo e arresta il contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-225">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="34269-226">Comandi essenziali</span><span class="sxs-lookup"><span data-stu-id="34269-226">Essential commands</span></span>

<span data-ttu-id="34269-227">Docker offre numerosi comandi che consentono di eseguire operazioni diverse sul contenitore e sulle immagini.</span><span class="sxs-lookup"><span data-stu-id="34269-227">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="34269-228">I comandi Docker seguenti sono essenziali per la gestione dei contenitori:</span><span class="sxs-lookup"><span data-stu-id="34269-228">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="34269-229">docker build</span><span class="sxs-lookup"><span data-stu-id="34269-229">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="34269-230">docker run</span><span class="sxs-lookup"><span data-stu-id="34269-230">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="34269-231">docker ps</span><span class="sxs-lookup"><span data-stu-id="34269-231">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="34269-232">docker stop</span><span class="sxs-lookup"><span data-stu-id="34269-232">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="34269-233">docker rm</span><span class="sxs-lookup"><span data-stu-id="34269-233">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="34269-234">docker rmi</span><span class="sxs-lookup"><span data-stu-id="34269-234">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="34269-235">docker image</span><span class="sxs-lookup"><span data-stu-id="34269-235">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="34269-236">Pulire le risorse</span><span class="sxs-lookup"><span data-stu-id="34269-236">Clean up resources</span></span>

<span data-ttu-id="34269-237">Durante questa esercitazione sono stati creati contenitori e immagini.</span><span class="sxs-lookup"><span data-stu-id="34269-237">During this tutorial you created containers and images.</span></span> <span data-ttu-id="34269-238">Se si preferisce, è possibile eliminare queste risorse.</span><span class="sxs-lookup"><span data-stu-id="34269-238">If you want, delete these resources.</span></span> <span data-ttu-id="34269-239">Usare i comandi seguenti per</span><span class="sxs-lookup"><span data-stu-id="34269-239">Use the following commands to</span></span>

01. <span data-ttu-id="34269-240">Elencare tutti i contenitori</span><span class="sxs-lookup"><span data-stu-id="34269-240">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="34269-241">Arrestare i contenitori in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="34269-241">Stop containers that are running.</span></span> <span data-ttu-id="34269-242">`CONTAINER_NAME` rappresenta il nome assegnato automaticamente al contenitore.</span><span class="sxs-lookup"><span data-stu-id="34269-242">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="34269-243">Eliminare il contenitore</span><span class="sxs-lookup"><span data-stu-id="34269-243">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="34269-244">Eliminare quindi le immagini che non si desidera conservare nel computer.</span><span class="sxs-lookup"><span data-stu-id="34269-244">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="34269-245">Eliminare l'immagine creata dal *Dockerfile* e quindi eliminare l'immagine .NET Core su cui è stato basato il *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="34269-245">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="34269-246">È possibile usare l'**IMAGE ID** o la stringa formattata come **REPOSITORY:TAG**.</span><span class="sxs-lookup"><span data-stu-id="34269-246">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="34269-247">Usare il comando `docker images` per visualizzare un elenco delle immagini installate.</span><span class="sxs-lookup"><span data-stu-id="34269-247">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="34269-248">I file di immagine possono essere di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="34269-248">Image files can be large.</span></span> <span data-ttu-id="34269-249">In genere è consigliabile rimuovere i contenitori temporanei creati durante il test e lo sviluppo dell'app.</span><span class="sxs-lookup"><span data-stu-id="34269-249">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="34269-250">Conservare invece le immagini di base con il runtime installato se si prevede di compilare altre immagini basate su quel runtime.</span><span class="sxs-lookup"><span data-stu-id="34269-250">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="34269-251">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="34269-251">Next steps</span></span>

* [<span data-ttu-id="34269-252">Provare l'esercitazione sulla creazione di microservizi ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="34269-252">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [<span data-ttu-id="34269-253">Esaminare i servizi di Azure che supportano i contenitori.</span><span class="sxs-lookup"><span data-stu-id="34269-253">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/en-us/overview/containers/)
* [<span data-ttu-id="34269-254">Leggere le informazioni sui comandi del Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="34269-254">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
