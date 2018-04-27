---
title: Ambiente di sviluppo per le app di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ddd1006c8c6728d4d315442f409f8fa33e54f9a3
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="55b52-103">Ambiente di sviluppo per le app di Docker</span><span class="sxs-lookup"><span data-stu-id="55b52-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="55b52-104">Opzioni degli strumenti di sviluppo: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="55b52-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="55b52-105">Indipendentemente dal fatto se si preferisce un IDE potente e completo o un editor di tipo semplice e agile, Microsoft ha la copertura per quanto riguarda lo sviluppo di applicazioni di Docker.</span><span class="sxs-lookup"><span data-stu-id="55b52-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="55b52-106">Visual Studio Code e Docker CLI (strumenti multipiattaforma per Mac, Linux e Windows)</span><span class="sxs-lookup"><span data-stu-id="55b52-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="55b52-107">Se si preferisce un editor leggero, multipiattaforma supportare qualsiasi linguaggio di sviluppo, è possibile utilizzare codice di Visual Studio e CLI di Docker.</span><span class="sxs-lookup"><span data-stu-id="55b52-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="55b52-108">Questi prodotti forniscono un'esperienza semplice ed efficace, è fondamentale per semplificare il flusso di lavoro di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="55b52-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="55b52-109">Installando "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori di Docker possono utilizzare un singolo CLI di Docker per creare App per Windows o Linux (ambiente di runtime) per.</span><span class="sxs-lookup"><span data-stu-id="55b52-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="55b52-110">Inoltre, codice di Visual Studio supporta le estensioni per Docker con IntelliSense per i Dockerfile e le attività di scelta rapida eseguire i comandi di Docker dall'editor.</span><span class="sxs-lookup"><span data-stu-id="55b52-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="55b52-111">Per scaricare codice di Visual Studio, visitare <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="55b52-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="55b52-112">Per scaricare Docker per Mac e Windows, visitare <http://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="55b52-112">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="55b52-113">Visual Studio con strumenti di Docker</span><span class="sxs-lookup"><span data-stu-id="55b52-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="55b52-114">Quando si utilizza Visual Studio 2015 è possibile installare gli strumenti di componente aggiuntivo "Strumenti di Docker per Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="55b52-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="55b52-115">Per Visual Studio 2017, strumenti di Docker provenire incorporati già.</span><span class="sxs-lookup"><span data-stu-id="55b52-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="55b52-116">In entrambi i casi che è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker scelto.</span><span class="sxs-lookup"><span data-stu-id="55b52-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="55b52-117">F5 (singolo contenitore o più contenitori) l'applicazione direttamente in una Docker host con il debug oppure premere Ctrl + F5 per modificare e aggiornare l'app senza dover ricompilare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="55b52-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="55b52-118">Questa è la scelta più semplice e più potente per gli sviluppatori di Windows, la creazione di contenitori di Docker per Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="55b52-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="55b52-119">Per scaricare gli strumenti di Docker per Visual Studio, visitare <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="55b52-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="55b52-120">Opzioni di lingua e framework</span><span class="sxs-lookup"><span data-stu-id="55b52-120">Language and framework choices</span></span>

<span data-ttu-id="55b52-121">È possibile sviluppare applicazioni di Docker e gli strumenti di Microsoft con i linguaggi più recenti.</span><span class="sxs-lookup"><span data-stu-id="55b52-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="55b52-122">Di seguito è riportato un elenco iniziale, ma non si è limitati a esso:</span><span class="sxs-lookup"><span data-stu-id="55b52-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="55b52-123">.NET core e ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="55b52-123">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="55b52-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="55b52-124">Node.js</span></span>

-   <span data-ttu-id="55b52-125">Golang</span><span class="sxs-lookup"><span data-stu-id="55b52-125">Golang</span></span>

-   <span data-ttu-id="55b52-126">Java</span><span class="sxs-lookup"><span data-stu-id="55b52-126">Java</span></span>

-   <span data-ttu-id="55b52-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="55b52-127">Ruby</span></span>

-   <span data-ttu-id="55b52-128">Python</span><span class="sxs-lookup"><span data-stu-id="55b52-128">Python</span></span>

<span data-ttu-id="55b52-129">In pratica, è possibile utilizzare un moderno linguaggio supportato da Docker in Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="55b52-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="55b52-130">[Precedente] (orchestrare-elevata-scalabilità-availability.md) [Avanti] (docker-App-interna-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="55b52-130">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
