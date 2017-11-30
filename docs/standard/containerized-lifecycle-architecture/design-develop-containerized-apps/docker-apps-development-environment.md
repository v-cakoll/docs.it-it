---
title: Ambiente di sviluppo per le app di Docker
description: Ciclo di vita dell'applicazione nei contenitori Docker con strumenti e piattaforma Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: eedba16136ad394bda45cc871944f9b876c8ee38
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2017
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="b9626-104">Ambiente di sviluppo per le app di Docker</span><span class="sxs-lookup"><span data-stu-id="b9626-104">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="b9626-105">Gli strumenti di sviluppo scelte: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="b9626-105">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="b9626-106">Indipendentemente dal fatto se si preferisce un IDE potente e completo o un editor di tipo semplice e agile, Microsoft ha la copertura per quanto riguarda lo sviluppo di applicazioni di Docker.</span><span class="sxs-lookup"><span data-stu-id="b9626-106">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="b9626-107">Visual Studio Code e Docker CLI (strumenti multipiattaforma per Mac, Linux e Windows)</span><span class="sxs-lookup"><span data-stu-id="b9626-107">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="b9626-108">Se si preferisce un editor leggero, multipiattaforma supportare qualsiasi linguaggio di sviluppo, è possibile utilizzare codice di Visual Studio e CLI di Docker.</span><span class="sxs-lookup"><span data-stu-id="b9626-108">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="b9626-109">Questi prodotti forniscono un'esperienza semplice ed efficace, è fondamentale per semplificare il flusso di lavoro di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b9626-109">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="b9626-110">Installando "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori di Docker possono utilizzare un singolo CLI di Docker per creare App per Windows o Linux (ambiente di runtime) per.</span><span class="sxs-lookup"><span data-stu-id="b9626-110">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="b9626-111">Inoltre, codice di Visual Studio supporta le estensioni per Docker con IntelliSense per i Dockerfile e le attività di scelta rapida eseguire i comandi di Docker dall'editor.</span><span class="sxs-lookup"><span data-stu-id="b9626-111">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="b9626-112">Per scaricare codice di Visual Studio, visitare <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="b9626-112">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="b9626-113">Per scaricare Docker per Mac e Windows, visitare <http://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="b9626-113">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="b9626-114">Visual Studio con strumenti di Docker</span><span class="sxs-lookup"><span data-stu-id="b9626-114">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="b9626-115">Quando si utilizza Visual Studio 2015 è possibile installare gli strumenti di componente aggiuntivo "Strumenti di Docker per Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="b9626-115">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="b9626-116">Per Visual Studio 2017, strumenti di Docker provenire incorporati già.</span><span class="sxs-lookup"><span data-stu-id="b9626-116">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="b9626-117">In entrambi i casi che è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker scelto.</span><span class="sxs-lookup"><span data-stu-id="b9626-117">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="b9626-118">F5 (singolo contenitore o più contenitori) l'applicazione direttamente in una Docker host con il debug oppure premere Ctrl + F5 per modificare e aggiornare l'app senza dover ricompilare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="b9626-118">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="b9626-119">Questa è la scelta più semplice e più potente per gli sviluppatori di Windows, la creazione di contenitori di Docker per Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="b9626-119">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="b9626-120">Per scaricare gli strumenti di Docker per Visual Studio, visitare <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="b9626-120">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="b9626-121">Opzioni di lingua e framework</span><span class="sxs-lookup"><span data-stu-id="b9626-121">Language and framework choices</span></span>

<span data-ttu-id="b9626-122">È possibile sviluppare applicazioni di Docker e gli strumenti di Microsoft con i linguaggi più recenti.</span><span class="sxs-lookup"><span data-stu-id="b9626-122">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="b9626-123">Di seguito è riportato un elenco iniziale, ma non si è limitati a esso:</span><span class="sxs-lookup"><span data-stu-id="b9626-123">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="b9626-124">.NET core e ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b9626-124">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="b9626-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="b9626-125">Node.js</span></span>

-   <span data-ttu-id="b9626-126">Golang</span><span class="sxs-lookup"><span data-stu-id="b9626-126">Golang</span></span>

-   <span data-ttu-id="b9626-127">Java</span><span class="sxs-lookup"><span data-stu-id="b9626-127">Java</span></span>

-   <span data-ttu-id="b9626-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="b9626-128">Ruby</span></span>

-   <span data-ttu-id="b9626-129">Python</span><span class="sxs-lookup"><span data-stu-id="b9626-129">Python</span></span>

<span data-ttu-id="b9626-130">In pratica, è possibile utilizzare un moderno linguaggio supportato da Docker in Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="b9626-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b9626-131">[Precedente] (orchestrare-elevata-scalabilità-availability.md) [Avanti] (docker-App-interna-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b9626-131">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
