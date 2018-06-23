---
title: Con Visual Studio Tools per Docker (Visual Studio in Windows)
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 62da6a3ff595422e42450cb1341976424acc5a52
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314711"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="dd1e4-103">Con Visual Studio Tools per Docker (Visual Studio in Windows)</span><span class="sxs-lookup"><span data-stu-id="dd1e4-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="dd1e4-104">Il flusso di lavoro di sviluppo quando si utilizza Visual Studio Tools per Docker è simile al flusso di lavoro quando si utilizza Visual Studio Code e Docker CLI (in realtà, si basa la stessa di Docker CLI), ma è più facile iniziare, semplifica il processo e offre una maggiore produttività per la compilazione, esecuzione e la composizione di attività.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-104">The developer workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI (in fact, it is based on the same Docker CLI), but it is easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="dd1e4-105">È inoltre in grado di eseguire ed eseguire il debug ai contenitori tramite le operazioni più semplici, ad esempio F5 e Ctrl + F5 da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-105">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="dd1e4-106">Ancora più con Visual Studio 2017, oltre a essere in grado di eseguire ed eseguire il debug di un singolo contenitore, è anche possibile eseguire e il debug di un gruppo di contenitori (una soluzione completa) nello stesso momento se sono definiti nello stesso file docker compose.yml a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-106">Even more, with Visual Studio 2017, in addition to being able to run and debug a single container, you also can run and debug a group of containers (a whole solution) at the same time if they are defined in the same docker-compose.yml file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="dd1e4-107">Configurazione dell'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="dd1e4-107">Configuring your local environment</span></span>

<span data-ttu-id="dd1e4-108">Con le versioni più recenti di Docker per Windows, risulta più semplice che mai, per sviluppare applicazioni Docker perché il programma di installazione è semplice, come illustrato nei riferimenti ai seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-108">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="dd1e4-109">**Altre informazioni:** per ulteriori informazioni sull'installazione di Docker per Windows, passare a <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-109">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="dd1e4-110">Se si usa Visual Studio 2015, è necessario disporre Update 3 o versione successiva con Visual Studio Tools per Docker.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-110">If you're using Visual Studio 2015, you must have Update 3 or a later version plus the Visual Studio Tools for Docker.</span></span>

<span data-ttu-id="dd1e4-111">**Altre informazioni:** per istruzioni sull'installazione di Visual Studio, passare alla [ https://visualstudio.microsoft.com/\ edizioni dei prodotti/vs-2015-prodotto](https://visualstudio.microsoft.com/products/vs-2015-product-editions).</span><span class="sxs-lookup"><span data-stu-id="dd1e4-111">**More info:** For instructions on installing Visual Studio, go to [https://visualstudio.microsoft.com/\ products/vs-2015-product-editions](https://visualstudio.microsoft.com/products/vs-2015-product-editions).</span></span>

<span data-ttu-id="dd1e4-112">Per visualizzare altre informazioni sull'installazione di Visual Studio Tools per Docker, passare a <http://aka.ms/vstoolsfordocker> e <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-112">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span></span>

<span data-ttu-id="dd1e4-113">Se si usa Visual Studio 2017, il supporto di Docker è già incluso.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-113">If you're using Visual Studio 2017, Docker support is already included.</span></span>

## <a name="using-docker-tools-in-visual-studio-2015"></a><span data-ttu-id="dd1e4-114">Utilizzando gli strumenti di Docker in Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="dd1e4-114">Using Docker Tools in Visual Studio 2015</span></span>

<span data-ttu-id="dd1e4-115">Visual Studio Tools per Docker offre un sistema coerente per sviluppare e convalidare i ai contenitori di Docker in locale per Linux in un host Linux Docker o macchina virtuale o i contenitori di Windows direttamente in Windows.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-115">The Visual Studio Tools for Docker provides a consistent way to develop and validate locally your Docker containers for Linux in a Linux Docker host or VM, or your Windows Containers directly on Windows.</span></span>

<span data-ttu-id="dd1e4-116">Se si usa un singolo contenitore, per abilitare il supporto di Docker nel progetto .NET Core è la prima cosa che occorre per iniziare.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-116">If you're using a single container, the first thing you need to begin is to turn on Docker support into your .NET Core project.</span></span> <span data-ttu-id="dd1e4-117">A tale scopo, fare clic sul file di progetto, come illustrato nella figura 4-25.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-117">To do this, right-click your project file, as shown in Figure 4-25.</span></span>

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

<span data-ttu-id="dd1e4-118">Figura 4-25: l'attivazione del supporto di Docker per il progetto di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dd1e4-118">Figure 4-25: Turning on Docker support for your Visual Studio project</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="dd1e4-119">Utilizzando gli strumenti di Docker in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="dd1e4-119">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="dd1e4-120">Quando si aggiunge il supporto di Docker per un progetto di servizio nella soluzione (vedere Figura 4-26), Visual Studio è non appena aggiunta di un DockerFile file al progetto, anche aggiunge una sezione di servizio per la soluzione docker compose.yml file (o creare i file se essi non sono stati esiste).</span><span class="sxs-lookup"><span data-stu-id="dd1e4-120">When you add Docker support to a service project in your solution (see Figure 4-26), Visual Studio is not just adding a DockerFile file to your project, it also is adding a service section in your solution's docker-compose.yml files (or creating the files if they didn't exist).</span></span> <span data-ttu-id="dd1e4-121">È un modo semplice per iniziare la composizione della soluzione multicontainer; è quindi possibile aprire i file di docker compose.yml e aggiornarle con funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-121">It's an easy way to begin composing your multicontainer solution; you then can open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image32.png)

<span data-ttu-id="dd1e4-122">Figura 4-26: l'attivazione del supporto di soluzioni di Docker in un progetto di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="dd1e4-122">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

<span data-ttu-id="dd1e4-123">Questa azione aggiunge non solo il DockerFile al progetto, aggiunge anche le righe di configurazione necessarie di codice per un globale compose.yml docker impostato a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-123">This action not only adds the DockerFile to your project, it also adds the required configuration lines of code to a global docker-compose.yml set at the solution level.</span></span>

<span data-ttu-id="dd1e4-124">È anche possibile attivare il supporto di Docker quando si crea un progetto ASP.NET Core in Visual Studio 2017, come illustrato nella figura 4-27.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-124">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![](./media/image33.png)

<span data-ttu-id="dd1e4-125">Figura 4-27: l'attivazione del supporto di Docker durante la creazione di un progetto</span><span class="sxs-lookup"><span data-stu-id="dd1e4-125">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="dd1e4-126">Dopo aver aggiunto il supporto di Docker per la soluzione in Visual Studio, è inoltre verrà visualizzato un nuovo albero di nodi in Esplora soluzioni con file aggiunti docker-compose.yml, come illustrato nella figura 4-28.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-126">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in Solution Explorer with the added docker-compose.yml files, as depicted in Figure 4-28.</span></span>

![](./media/image34.PNG)

<span data-ttu-id="dd1e4-127">Figura 4-28: file compose.yml docker è ora visualizzato in Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="dd1e4-127">Figure 4-28: docker-compose.yml files now display in Solution Explorer</span></span>

<span data-ttu-id="dd1e4-128">È possibile distribuire un multicontainer applicazione utilizzando un file docker-compose.yml solo quando si esegue docker-comporre; Tuttavia, Visual Studio aggiunge un gruppo di essi, in modo è possibile eseguire l'override di valori a seconda dell'ambiente (sviluppo e produzione) e l'esecuzione del tipo (release e debug).</span><span class="sxs-lookup"><span data-stu-id="dd1e4-128">You could deploy a multicontainer application by using a single docker-compose.yml file when you run docker-compose up; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="dd1e4-129">Questa funzionalità verrà spiegata meglio nei capitoli successivi.</span><span class="sxs-lookup"><span data-stu-id="dd1e4-129">This capability will be better explained in later chapters.</span></span>

<span data-ttu-id="dd1e4-130">**Altre informazioni:** per altri dettagli di implementazione di servizi e l'utilizzo di Visual Studio Tools per Docker, leggere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd1e4-130">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="dd1e4-131">Compilare, eseguire il debug, aggiornare e aggiornare le App in un contenitore Docker locale: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="dd1e4-131">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="dd1e4-132">Distribuire un contenitore di ASP.NET in un host Docker remoto: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="dd1e4-132">Deploy an ASP.NET container to a remote Docker host: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dd1e4-133">[Precedente] (docker-App-interna-loop-workflow.md) [Avanti] (set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="dd1e4-133">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span></span>
