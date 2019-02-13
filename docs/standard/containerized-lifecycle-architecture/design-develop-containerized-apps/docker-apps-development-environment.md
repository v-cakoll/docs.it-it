---
title: Ambiente di sviluppo per le app di Docker
description: Conoscere i più importanti opzioni dello strumento di sviluppo che supportano il ciclo di vita di sviluppo Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 1d22b45a8eee9198d337df9f0b8b4b78371fa31a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219997"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="80355-103">Ambiente di sviluppo per le app di Docker</span><span class="sxs-lookup"><span data-stu-id="80355-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="80355-104">Strumenti di sviluppo possibili: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="80355-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="80355-105">Non importa se si preferisce un IDE potente e completo o un editor semplice e agile, Microsoft ha ti serve se si desidera lo sviluppo di applicazioni di Docker.</span><span class="sxs-lookup"><span data-stu-id="80355-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="80355-106">Visual Studio Code e CLI di Docker (strumenti multipiattaforma per Mac, Linux e Windows)</span><span class="sxs-lookup"><span data-stu-id="80355-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="80355-107">Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Visual Studio Code e CLI di Docker.</span><span class="sxs-lookup"><span data-stu-id="80355-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="80355-108">Questi prodotti forniscono un'esperienza semplice ma efficace, di fondamentale importanza per semplificare il flusso di lavoro per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="80355-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="80355-109">Tramite l'installazione di "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori Docker possono usare una singola interfaccia CLI di Docker per creare App per Windows o Linux (ambiente di runtime).</span><span class="sxs-lookup"><span data-stu-id="80355-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="80355-110">Inoltre, Visual Studio Code supporta le estensioni per Docker con IntelliSense per Dockerfile e le attività di collegamento eseguire i comandi di Docker dall'editor.</span><span class="sxs-lookup"><span data-stu-id="80355-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="80355-111">Per scaricare Visual Studio Code, visitare <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="80355-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="80355-112">Per scaricare Docker per Mac e Windows, visitare <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="80355-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="80355-113">Visual Studio con gli strumenti di Docker</span><span class="sxs-lookup"><span data-stu-id="80355-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="80355-114">Quando si usa Visual Studio 2015 è possibile installare gli strumenti di componente aggiuntivo "Docker Tools per Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="80355-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="80355-115">Per Visual Studio 2017, gli strumenti di Docker vengono incorporati già.</span><span class="sxs-lookup"><span data-stu-id="80355-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="80355-116">In entrambi i casi che è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente Docker selezionato.</span><span class="sxs-lookup"><span data-stu-id="80355-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="80355-117">F5 l'applicazione (con contenitore singolo o più contenitori) direttamente in un Docker ospitare con il debug oppure premere CTRL+F5 per modificare e aggiornare l'app senza dovere ricompilare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="80355-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="80355-118">Questa è la scelta più semplice e più potente per gli sviluppatori Windows la creazione di contenitori Docker per Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="80355-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="80355-119">Per scaricare gli strumenti di Docker per Visual Studio, passare a <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="80355-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="80355-120">Opzioni relative a lingua e framework</span><span class="sxs-lookup"><span data-stu-id="80355-120">Language and framework choices</span></span>

<span data-ttu-id="80355-121">È possibile sviluppare applicazioni di Docker e gli strumenti di Microsoft con i linguaggi più moderni.</span><span class="sxs-lookup"><span data-stu-id="80355-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="80355-122">Di seguito è riportato un elenco iniziale, ma non si è limitati a esso:</span><span class="sxs-lookup"><span data-stu-id="80355-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="80355-123">.NET Core e ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="80355-123">.NET Core and ASP.NET Core</span></span>
-   <span data-ttu-id="80355-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="80355-124">Node.js</span></span>
-   <span data-ttu-id="80355-125">Golang</span><span class="sxs-lookup"><span data-stu-id="80355-125">Golang</span></span>
-   <span data-ttu-id="80355-126">Java</span><span class="sxs-lookup"><span data-stu-id="80355-126">Java</span></span>
-   <span data-ttu-id="80355-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="80355-127">Ruby</span></span>
-   <span data-ttu-id="80355-128">Python</span><span class="sxs-lookup"><span data-stu-id="80355-128">Python</span></span>

<span data-ttu-id="80355-129">In pratica, è possibile usare qualsiasi linguaggio moderno supportato da Docker in Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="80355-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="80355-130">[Precedente](deploy-azure-kubernetes-service.md)
>[Successivo](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="80355-130">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>