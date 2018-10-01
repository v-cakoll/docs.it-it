---
title: Esecuzione di applicazioni console in Docker
description: Informazioni su come eseguire un'applicazione console .NET Framework esistente in un contenitore Docker di Windows.
author: spboyer
ms.date: 09/28/2016
ms.assetid: 85cca1d5-c9a4-4eb2-93e6-4f878de07fd7
ms.openlocfilehash: f5a38ac63db969a58e920ea79bf4bf10bcfcf64f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193330"
---
# <a name="running-console-applications-in-windows-containers"></a><span data-ttu-id="d8d25-103">Esecuzione di applicazioni console in contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="d8d25-103">Running console applications in Windows containers</span></span>

<span data-ttu-id="d8d25-104">Le applicazioni console vengono usate per scopi diversi, dalla semplice esecuzione di query sullo stato ad attività di elaborazione di immagini documento a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="d8d25-104">Console applications are used for many purposes; from simple querying of a status to long running document image processing tasks.</span></span> <span data-ttu-id="d8d25-105">In ogni caso, la possibilità di avviare e ridimensionare tali applicazioni dipende da limitazioni relative all'acquisizione di hardware, ai tempi di avvio e all'esecuzione di più istanze.</span><span class="sxs-lookup"><span data-stu-id="d8d25-105">In any case, the ability to start up and scale these applications are met with limitations of hardware acquisitions, startup times or running multiple instances.</span></span>

<span data-ttu-id="d8d25-106">Lo spostamento delle applicazioni console per l'uso di contenitori Docker e Windows Server consente di avviare tali applicazioni partendo da uno stato originario, in modo che possano eseguire l'operazione e arrestarsi correttamente.</span><span class="sxs-lookup"><span data-stu-id="d8d25-106">Moving your console applications to use Docker and Windows Server containers allows for starting these applications from a clean state, enabling them to perform the operation and then shutdown cleanly.</span></span> <span data-ttu-id="d8d25-107">In questo argomento verranno illustrati i passaggi necessari per spostare un'applicazione console in un contenitore basato su Windows e avviarla tramite uno script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8d25-107">This topic will show the steps needed to move a console application to a Windows based container and start it using a PowerShell script.</span></span>

<span data-ttu-id="d8d25-108">L'applicazione console di esempio è un esempio semplice che prende un argomento, in questo caso una domanda, e restituisce una risposta casuale.</span><span class="sxs-lookup"><span data-stu-id="d8d25-108">The sample console application is a simple example which takes an argument, a question in this case, and returns a random answer.</span></span> <span data-ttu-id="d8d25-109">Potrebbe trattarsi di prendere un `customer_id` ed elaborarne le imposte o di creare un'anteprima per un argomento `image_url`.</span><span class="sxs-lookup"><span data-stu-id="d8d25-109">This could take a `customer_id` and process their taxes, or create a thumbnail for an `image_url` argument.</span></span>

<span data-ttu-id="d8d25-110">Oltre alla risposta, `Environment.MachineName` è stato aggiunto per illustrare la differenza tra l'esecuzione dell'applicazione in locale e in un contenitore di Windows.</span><span class="sxs-lookup"><span data-stu-id="d8d25-110">In addition to the answer, the `Environment.MachineName` has been added to the response to show the difference between running the application locally and in a Windows container.</span></span> <span data-ttu-id="d8d25-111">Quando si esegue l'applicazione localmente, deve essere restituito il nome del computer locale mentre, durante l'esecuzione in un contenitore di Windows, viene restituito l'id di sessione del contenitore.</span><span class="sxs-lookup"><span data-stu-id="d8d25-111">When running the application locally, your local machine name should be returned and when running in a Windows Container; the container session id is returned.</span></span>

<span data-ttu-id="d8d25-112">L'[esempio completo](https://github.com/dotnet/samples/tree/master/framework/docker/ConsoleRandomAnswerGenerator) è disponibile nel repository dotnet/samples su GitHub.</span><span class="sxs-lookup"><span data-stu-id="d8d25-112">The [complete example](https://github.com/dotnet/samples/tree/master/framework/docker/ConsoleRandomAnswerGenerator) is available in the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="d8d25-113">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="d8d25-113">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="d8d25-114">È necessario avere familiarità con alcuni termini di Docker prima di iniziare lo spostamento dell'applicazione in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="d8d25-114">You need to be familiar with some Docker terms before you begin working on moving your application to a container.</span></span>

> <span data-ttu-id="d8d25-115">Una *immagine Docker* è un modello di sola lettura che definisce l'ambiente per un contenitore in esecuzione, inclusi il sistema operativo, i componenti di sistema e le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d8d25-115">A *Docker image* is a read-only template that defines the environment for a running container, including the operating system (OS), system components, and application(s).</span></span>

<span data-ttu-id="d8d25-116">Una delle caratteristiche principali delle immagini Docker è che sono costituite da un'immagine di base.</span><span class="sxs-lookup"><span data-stu-id="d8d25-116">One important feature of Docker images is that images are composed from a base image.</span></span> <span data-ttu-id="d8d25-117">Ogni nuova immagine aggiunge un piccolo set di funzionalità a un'immagine esistente.</span><span class="sxs-lookup"><span data-stu-id="d8d25-117">Each new image adds a small set of features to an existing image.</span></span> 

> <span data-ttu-id="d8d25-118">Un *contenitore Docker* è un'istanza di un'immagine in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d8d25-118">A *Docker container* is a running instance of an image.</span></span> 

<span data-ttu-id="d8d25-119">Un'applicazione viene ridimensionata eseguendo la stessa immagine in più contenitori.</span><span class="sxs-lookup"><span data-stu-id="d8d25-119">You scale an application by running the same image in many containers.</span></span>
<span data-ttu-id="d8d25-120">Concettualmente, è molto simile all'esecuzione della stessa applicazione in più host.</span><span class="sxs-lookup"><span data-stu-id="d8d25-120">Conceptually, this is similar to running the same application in multiple hosts.</span></span>

<span data-ttu-id="d8d25-121">Per altre informazioni sull'architettura Docker, vedere [Docker Overview](https://docs.docker.com/engine/understanding-docker/) (Panoramica di Docker) nel sito di Docker.</span><span class="sxs-lookup"><span data-stu-id="d8d25-121">You can learn more about the Docker architecture by reading the [Docker Overview](https://docs.docker.com/engine/understanding-docker/) on the Docker site.</span></span> 

<span data-ttu-id="d8d25-122">Lo spostamento dell'applicazione non richiede che pochi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d8d25-122">Moving your console application is a matter of a few steps.</span></span>

1. [<span data-ttu-id="d8d25-123">Compilare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="d8d25-123">Build the application</span></span>](#building-the-application)
1. [<span data-ttu-id="d8d25-124">Creazione di un documento Dockerfile per l'immagine</span><span class="sxs-lookup"><span data-stu-id="d8d25-124">Creating a Dockerfile for the image</span></span>](#creating-the-dockerfile)
1. [<span data-ttu-id="d8d25-125">Processo di compilazione ed esecuzione del contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="d8d25-125">Process to build and run the Docker container</span></span>](#creating-the-image)

## <a name="prerequisites"></a><span data-ttu-id="d8d25-126">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d8d25-126">Prerequisites</span></span>
<span data-ttu-id="d8d25-127">I contenitori di Windows sono supportati in [Aggiornamento dell'anniversario di Windows 10](https://www.microsoft.com/en-us/software-download/windows10/) o [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span><span class="sxs-lookup"><span data-stu-id="d8d25-127">Windows containers are supported on [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) or [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span></span>

> [!NOTE]
><span data-ttu-id="d8d25-128">Se si usa Windows Server 2016, è necessario abilitare manualmente i contenitori poiché il programma di installazione di Docker per Windows non abilita tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d8d25-128">If you are using Windows Server 2016, you must enable containers manually since the Docker for Windows installer will not enable the feature.</span></span> <span data-ttu-id="d8d25-129">Assicurarsi che tutti gli aggiornamenti siano stati eseguiti per il sistema operativo e seguire le istruzioni dell'articolo [Distribuzione di host contenitore - Windows Server](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment) per installare le funzionalità di Docker e dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="d8d25-129">Make sure all updates have run for the OS and then follow the instructions from the [Container Host Deployment](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment) article to install the containers and Docker features.</span></span>

<span data-ttu-id="d8d25-130">Per il supporto dei contenitori Windows è necessario avere Docker per Windows versione 1.12 Beta 26 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d8d25-130">You need to have Docker for Windows, version 1.12 Beta 26 or higher to support Windows containers.</span></span> <span data-ttu-id="d8d25-131">Per impostazione predefinita, Docker abilita contenitori basati su Linux. Per passare ai contenitori Windows, fare clic con il pulsante destro del mouse sull'icona di Docker nell'area di notifica e selezionare **Switch to Windows containers** (Passa a contenitori Windows).</span><span class="sxs-lookup"><span data-stu-id="d8d25-131">By default, Docker enables Linux based containers; switch to Windows containers by right clicking the Docker icon in the system tray and select **Switch to Windows containers**.</span></span> <span data-ttu-id="d8d25-132">Docker eseguirà il processo di modifica e potrebbe essere necessario un riavvio.</span><span class="sxs-lookup"><span data-stu-id="d8d25-132">Docker will run the process to change and a restart may be required.</span></span>

![Contenitori di Windows](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a><span data-ttu-id="d8d25-134">Compilazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d8d25-134">Building the application</span></span>
<span data-ttu-id="d8d25-135">In genere le applicazioni console vengono distribuite attraverso un programma di installazione, FTP o una distribuzione di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="d8d25-135">Typically console applications are distributed through an installer, FTP, or File Share deployment.</span></span> <span data-ttu-id="d8d25-136">Quando si esegue la distribuzione in un contenitore, le risorse devono essere compilate e inserite temporaneamente in un percorso che può essere usato quando viene creata l'immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="d8d25-136">When deploying to a container, the assets need to be compiled and staged to a location that can be used when the Docker image is created.</span></span>

<span data-ttu-id="d8d25-137">In *build.ps1* lo script usa [MSBuild](/visualstudio/msbuild/msbuild) per compilare l'applicazione per completare l'attività di creazione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d8d25-137">In *build.ps1*, the script uses [MSBuild](/visualstudio/msbuild/msbuild) to compile the application to complete the task of building the assets.</span></span> <span data-ttu-id="d8d25-138">Vi sono alcuni parametri che vengono passati a MSBuild per finalizzare le risorse necessarie.</span><span class="sxs-lookup"><span data-stu-id="d8d25-138">There are a few parameters passed to MSBuild to finalize the needed assets.</span></span> <span data-ttu-id="d8d25-139">Il nome del file di progetto o della soluzione da compilare, il percorso dell'output e, infine, la configurazione (Release o Debug).</span><span class="sxs-lookup"><span data-stu-id="d8d25-139">The name of the project file or solution to be compiled, the location for the output and finally the configuration (Release or Debug).</span></span>

<span data-ttu-id="d8d25-140">Nella chiamata a `Invoke-MSBuild` `OutputPath` è impostato su **publish** e `Configuration` è impostato su **Release**.</span><span class="sxs-lookup"><span data-stu-id="d8d25-140">In the call to `Invoke-MSBuild` the `OutputPath` is set to **publish** and  `Configuration` set to **Release**.</span></span> 

```
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj -p:OutputPath=.\publish -p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a><span data-ttu-id="d8d25-141">Creazione del documento Dockerfile</span><span class="sxs-lookup"><span data-stu-id="d8d25-141">Creating the Dockerfile</span></span>
<span data-ttu-id="d8d25-142">L'immagine di base usata per un'applicazione console .NET Framework è `microsoft/windowsservercore`, disponibile pubblicamente nell'[hub Docker](https://hub.docker.com/r/microsoft/windowsservercore/).</span><span class="sxs-lookup"><span data-stu-id="d8d25-142">The base image used for a console .NET Framework application is `microsoft/windowsservercore`, publicly available on [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span></span> <span data-ttu-id="d8d25-143">L'immagine di base contiene un'installazione minima di Windows Server 2016, .NET Framework 4.6.2 e viene usata come immagine di base del sistema operativo per i contenitori Windows.</span><span class="sxs-lookup"><span data-stu-id="d8d25-143">The base image contains a minimal installation of Windows Server 2016, .NET Framework 4.6.2 and serves as the base OS image for Windows Containers.</span></span>

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
<span data-ttu-id="d8d25-144">La prima riga del documento Dockerfile definisce l'immagine di base tramite l'istruzione [`FROM`](https://docs.docker.com/engine/reference/builder/#/from).</span><span class="sxs-lookup"><span data-stu-id="d8d25-144">The first line in the Dockerfile designates the base image using the [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) instruction.</span></span> <span data-ttu-id="d8d25-145">Successivamente, l'istruzione [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) nel file copia le risorse dell'applicazione dalla cartella **publish** alla cartella radice del contenitore. Infine, impostando il valore [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) dell'immagine si indica che questo è il comando o l'applicazione che verrà eseguita all'avvio del contenitore.</span><span class="sxs-lookup"><span data-stu-id="d8d25-145">Next, [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) in the file copies the application assets from the **publish** folder to root folder of the container and last; setting the [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) of the image states that this is the command or application that will run when the container starts.</span></span> 

## <a name="creating-the-image"></a><span data-ttu-id="d8d25-146">Creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="d8d25-146">Creating the image</span></span>
<span data-ttu-id="d8d25-147">Per creare l'immagine Docker, viene aggiunto il codice seguente allo script *build.ps1*.</span><span class="sxs-lookup"><span data-stu-id="d8d25-147">In order to create the Docker image, the following code is added to the *build.ps1* script.</span></span> <span data-ttu-id="d8d25-148">Quando lo script viene eseguito, viene creata l'immagine `console-random-answer-generator` tramite l'uso delle risorse compilate da MSBuild definite nella sezione [Compilazione dell'applicazione](#building-the-application).</span><span class="sxs-lookup"><span data-stu-id="d8d25-148">When the script is run, the `console-random-answer-generator` image is created using the assets compiled from MSBuild defined in the [Building the application](#building-the-application) section.</span></span>

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

<span data-ttu-id="d8d25-149">Eseguire lo script usando `.\build.ps1` al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8d25-149">Run the script using `.\build.ps1` from the PowerShell command prompt.</span></span>

<span data-ttu-id="d8d25-150">Una volta completata la compilazione, usare il comando `docker images` da una riga di comando o al prompt dei comandi di PowerShell. Si noterà che l'immagine è stata creata ed è pronta per essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="d8d25-150">When the build is complete, using the `docker images` command from a command line or PowerShell prompt; you'll see that the image is created and ready to be run.</span></span>

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a><span data-ttu-id="d8d25-151">Esecuzione del contenitore</span><span class="sxs-lookup"><span data-stu-id="d8d25-151">Running the container</span></span>
<span data-ttu-id="d8d25-152">È possibile avviare il contenitore dalla riga di comando tramite i comandi di Docker.</span><span class="sxs-lookup"><span data-stu-id="d8d25-152">You can start the container from the command line using the Docker commands.</span></span>

```
docker run console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="d8d25-153">L'output è</span><span class="sxs-lookup"><span data-stu-id="d8d25-153">The output is</span></span>

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

<span data-ttu-id="d8d25-154">Se si esegue il comando `docker ps -a` da PowerShell, è possibile vedere che il contenitore è ancora presente.</span><span class="sxs-lookup"><span data-stu-id="d8d25-154">If you run the `docker ps -a` command from PowerShell, you can see that the container still exists.</span></span>

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

<span data-ttu-id="d8d25-155">Nella colonna STATUS viene indicato che "About a minute ago" (circa un minuto fa) l'applicazione è stata completata ed è possibile arrestarla.</span><span class="sxs-lookup"><span data-stu-id="d8d25-155">The STATUS column shows at "About a minute ago", the application was complete and could be shut down.</span></span> <span data-ttu-id="d8d25-156">Se il comando fosse stato eseguito un centinaio di volte, vi sarebbero cento contenitori statici, lasciati senza alcuna operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d8d25-156">If the command was run a hundred times, there would be a hundred containers left static with no work to do.</span></span> <span data-ttu-id="d8d25-157">Nello scenario iniziale l'operazione ideale è stata quella di eseguire le operazioni e quindi chiudere o eseguire la pulizia.</span><span class="sxs-lookup"><span data-stu-id="d8d25-157">In the beginning scenario the ideal operation was to do the work and shutdown or cleanup.</span></span> <span data-ttu-id="d8d25-158">Per completare il flusso di lavoro, aggiungere l'opzione `--rm` al comando `docker run` per rimuovere il contenitore non appena viene ricevuto il segnale `Exited`.</span><span class="sxs-lookup"><span data-stu-id="d8d25-158">To accomplish that workflow, adding the `--rm` option to the `docker run` command will remove the container as soon as the `Exited` signal is received.</span></span>

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="d8d25-159">Se si esegue il comando con questa opzione e quindi si esamina l'output del comando `docker ps -a`, si noterà che l'id del contenitore (`Environment.MachineName`) non è presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d8d25-159">Running the command with this option and then looking at the output of `docker ps -a` command; notice that the container id (the `Environment.MachineName`) is not in the list.</span></span>

### <a name="running-the-container-using-powershell"></a><span data-ttu-id="d8d25-160">Esecuzione del contenitore tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8d25-160">Running the container using PowerShell</span></span>
<span data-ttu-id="d8d25-161">Nei file di progetto di esempio è anche disponibile un'istruzione *run.ps1* che è un esempio di come usare PowerShell per eseguire l'applicazione accettando gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="d8d25-161">In the sample project files there is also a *run.ps1* which is an example of how to use PowerShell to run the application accepting the arguments.</span></span>

<span data-ttu-id="d8d25-162">Per l'esecuzione, aprire PowerShell e usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d8d25-162">To run, open PowerShell and use the following command:</span></span>

```
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a><span data-ttu-id="d8d25-163">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d8d25-163">Summary</span></span>
<span data-ttu-id="d8d25-164">È sufficiente aggiungere un documento Dockerfile e pubblicare l'applicazione per eseguire le applicazioni console .NET Framework in un contenitore e poter sfruttare tutti i vantaggi dell'esecuzione di più istanze, avvio e arresto corretti e altre funzionalità di Windows Server 2016 senza apportare modifiche al codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8d25-164">Just by adding a Dockerfile and publishing the application, you can containerize your .NET Framework console applications and now take the advantage of running multiple instances, clean start and stop and more Windows Server 2016 capabilities without making any changes to the application code at all.</span></span>
