---
title: Visual Studio Tools per Docker in Windows
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170795"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="557cf-103">Uso di Visual Studio Tools per Docker (Visual Studio in Windows)</span><span class="sxs-lookup"><span data-stu-id="557cf-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="557cf-104">Visual Studio Tools per flusso di lavoro per gli sviluppatori Docker è simile all'uso di Visual Studio Code e CLI di Docker (cui si basa la CLI di Docker stesso).</span><span class="sxs-lookup"><span data-stu-id="557cf-104">The Visual Studio Tools for Docker developer workflow is similar to using Visual Studio Code and Docker CLI (it is based on the same Docker CLI).</span></span> <span data-ttu-id="557cf-105">Visual Studio Tools per Docker rende ancora più semplice iniziare, semplifica il processo e fornisce una maggiore produttività per la compilazione, esecuzione e la composizione di attività.</span><span class="sxs-lookup"><span data-stu-id="557cf-105">Visual Studio Tools for Docker makes it even easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="557cf-106">Eseguire e il debug dei contenitori tramite semplici azioni, ad esempio **F5** e **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="557cf-106">Execute and debug your containers via simple actions like **F5** and **Ctrl**+**F5**.</span></span>

> [!NOTE]
> <span data-ttu-id="557cf-107">Questo articolo si applica a Visual Studio in Windows e non in Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="557cf-107">This article applies to Visual Studio on Windows, and not Visual Studio for Mac.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="557cf-108">Configurare l'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="557cf-108">Configure your local environment</span></span>

<span data-ttu-id="557cf-109">Con le versioni più recenti di Docker per Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), il programma di installazione semplice semplifica lo sviluppo di applicazioni di Docker.</span><span class="sxs-lookup"><span data-stu-id="557cf-109">With the latest versions of Docker for Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), the straightforward setup makes it easy to develop Docker applications.</span></span>

<span data-ttu-id="557cf-110">Supporto per docker è incluso in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="557cf-110">Docker support is included in Visual Studio 2017.</span></span> <span data-ttu-id="557cf-111">Scaricare Visual Studio 2017 di seguito: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="557cf-111">Download Visual Studio 2017 here: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

## <a name="use-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="557cf-112">Usare gli strumenti di Docker in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="557cf-112">Use Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="557cf-113">Esistono due livelli di supporto di Docker che è possibile aggiungere a un progetto.</span><span class="sxs-lookup"><span data-stu-id="557cf-113">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="557cf-114">Nei progetti di app web .NET Core, puoi semplicemente aggiungere una *Dockerfile* file per il progetto dall'abilitazione del supporto Docker.</span><span class="sxs-lookup"><span data-stu-id="557cf-114">In .NET Core web app projects, you can just add a *Dockerfile* file to the project by enabling Docker support.</span></span> <span data-ttu-id="557cf-115">Il livello successivo è supporto dell'agente di orchestrazione dei contenitori, che consente di aggiungere un *Dockerfile* al progetto (se non esiste già) e una *docker-Compose. yml* file a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="557cf-115">The next level is container orchestrator support, which adds a *Dockerfile* to the project (if it doesn't already exist) and a *docker-compose.yml* file at the solution level.</span></span>

<span data-ttu-id="557cf-116">Il **Add** > **supporto Docker** e **Add** > **supporto dell'agente di orchestrazione dei contenitori** sono comandi il menu di scelta rapida (o menu di scelta rapida) del nodo di progetto per un progetto di app web nello **Esplora soluzioni**, come illustrato nella figura 4-26:</span><span class="sxs-lookup"><span data-stu-id="557cf-116">The **Add** > **Docker Support** and **Add** > **Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for a web app project in **Solution Explorer**, as shown in Figure 4-26:</span></span>

![Aggiungere l'opzione di menu supporto Docker in Visual Studio](media/add-docker-support-menu.png)

<span data-ttu-id="557cf-118">Figura 4-26: aggiunta del supporto Docker a un progetto di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="557cf-118">Figure 4-26: Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="557cf-119">Aggiungi supporto Docker</span><span class="sxs-lookup"><span data-stu-id="557cf-119">Add Docker support</span></span>

<span data-ttu-id="557cf-120">È possibile aggiungere il supporto Docker a un progetto di app web .NET Core esistente selezionando **Add** > **supporto Docker** nella **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="557cf-120">You can add Docker support to an existing .NET Core web app project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="557cf-121">È anche possibile abilitare il supporto di Docker durante la creazione del progetto selezionando **Abilita supporto Docker** nel **nuova applicazione Web di ASP.NET Core** la finestra di dialogo visualizzata dopo aver fatto clic **OK** nella **nuovo progetto** finestra di dialogo, come illustrato nella figura 4-27.</span><span class="sxs-lookup"><span data-stu-id="557cf-121">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-27.</span></span>

![Abilitare il supporto di Docker per la nuova app web ASP.NET Core in Visual Studio](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="557cf-123">Figura 4-27: abilitare il supporto Docker durante la creazione del progetto in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="557cf-123">Figure 4-27: Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="557cf-124">Quando si aggiungono o si abilita supporto per Docker, Visual Studio aggiunge un *Dockerfile* file al progetto.</span><span class="sxs-lookup"><span data-stu-id="557cf-124">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="557cf-125">Quando si abilita il supporto di Docker Compose durante la creazione del progetto per un progetto di app web di .NET Framework (non un progetto .NET Core web app) come illustrato nella figura 4-28, viene inoltre aggiunto il supporto dell'agente di orchestrazione dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="557cf-125">When you enable Docker Compose support during project creation for a .NET Framework web app project (not a .NET Core web app project) as shown in Figure 4-28, container orchestrator support is also added.</span></span>
>
> ![Abilitare Docker compose di supporto per un progetto di app web di .NET Framework](media/enable-docker-compose-support.png)

> <span data-ttu-id="557cf-127">Figura 4-28: attivazione del supporto per Docker Compose in un progetto di app web di .NET Framework in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="557cf-127">Figure 4-28: Enabling Docker Compose support on a .NET Framework web app project in Visual Studio 2017</span></span>

### <a name="add-container-orchestrator-support"></a><span data-ttu-id="557cf-128">Aggiungere il supporto dell'agente di orchestrazione dei contenitori</span><span class="sxs-lookup"><span data-stu-id="557cf-128">Add container orchestrator support</span></span>

<span data-ttu-id="557cf-129">Quando si desidera comporre una soluzione multicontenitore, aggiungere il supporto dell'agente di orchestrazione dei contenitori per i progetti.</span><span class="sxs-lookup"><span data-stu-id="557cf-129">When you want to compose a multicontainer solution, add container orchestrator support to your projects.</span></span> <span data-ttu-id="557cf-130">Quando si aggiunge il supporto dell'agente di orchestrazione dei contenitori, Visual Studio aggiunge un *Dockerfile* al progetto (se non esiste già) e globale *docker-Compose. yml* file a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="557cf-130">When you add container orchestrator support, Visual Studio adds a *Dockerfile* to the project (if it doesn't already exist) and a global *docker-compose.yml* file at the solution level.</span></span> <span data-ttu-id="557cf-131">Ciò consente di eseguire ed eseguire il debug di un gruppo di contenitori (un'intera soluzione) nello stesso momento, se sono definiti nello stesso *docker-Compose. yml* file.</span><span class="sxs-lookup"><span data-stu-id="557cf-131">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span> <span data-ttu-id="557cf-132">Se *docker-Compose. yml* esiste già, Visual Studio aggiunge solo le righe di codice di configurazione necessarie a esso.</span><span class="sxs-lookup"><span data-stu-id="557cf-132">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

<span data-ttu-id="557cf-133">Dopo aver aggiunto il supporto di orchestrazione contenitore al progetto, viene visualizzato un file Docker aggiunti al progetto e un **docker-compose** aggiunto alla soluzione nella cartella **Esplora soluzioni**, come illustrato nella figura 4-29:</span><span class="sxs-lookup"><span data-stu-id="557cf-133">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-29:</span></span>

![File di docker in Esplora soluzioni in Visual Studio](media/docker-support-solution-explorer.png)

<span data-ttu-id="557cf-135">Figura 4-29: file di Docker in Esplora soluzioni in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="557cf-135">Figure 4-29: Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="557cf-136">**Altre informazioni:** per altri dettagli sull'implementazione di servizi e l'uso di Visual Studio Tools per Docker, leggere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="557cf-136">**More information:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="557cf-137">Compilare, eseguire il debug, aggiornare e aggiornare le App in un contenitore Docker locale: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="557cf-137">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="557cf-138">Distribuire un contenitore Docker ASP.NET Core in un registro contenitori: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="557cf-138">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="557cf-139">[Precedente](docker-apps-inner-loop-workflow.md)
[Successivo](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="557cf-139">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>