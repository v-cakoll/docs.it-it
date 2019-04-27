---
title: Ambiente di sviluppo per le app di Docker
description: Conoscere i più importanti opzioni dello strumento di sviluppo che supportano il ciclo di vita di sviluppo Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799320"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="6ada9-103">Ambiente di sviluppo per le app di Docker</span><span class="sxs-lookup"><span data-stu-id="6ada9-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="6ada9-104">Strumenti di sviluppo possibili: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="6ada9-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="6ada9-105">Non importa se si preferisce un IDE potente e completo o un editor semplice e agile, Microsoft ha ti serve se si desidera lo sviluppo di applicazioni di Docker.</span><span class="sxs-lookup"><span data-stu-id="6ada9-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="6ada9-106">Visual Studio Code e CLI di Docker (strumenti multipiattaforma per Mac, Linux e Windows)</span><span class="sxs-lookup"><span data-stu-id="6ada9-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="6ada9-107">Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Visual Studio Code e CLI di Docker.</span><span class="sxs-lookup"><span data-stu-id="6ada9-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="6ada9-108">Questi prodotti forniscono un'esperienza semplice ma efficace, di fondamentale importanza per semplificare il flusso di lavoro per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="6ada9-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="6ada9-109">Tramite l'installazione di "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori Docker possono usare una singola interfaccia CLI di Docker per creare App per Windows o Linux (ambiente di runtime).</span><span class="sxs-lookup"><span data-stu-id="6ada9-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="6ada9-110">Inoltre, Visual Studio Code supporta le estensioni per Docker con IntelliSense per Dockerfile e le attività di collegamento eseguire i comandi di Docker dall'editor.</span><span class="sxs-lookup"><span data-stu-id="6ada9-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
>
> <span data-ttu-id="6ada9-111">Per scaricare Visual Studio Code, visitare <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="6ada9-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="6ada9-112">Per scaricare Docker per Mac e Windows, visitare <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="6ada9-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="6ada9-113">Visual Studio con gli strumenti di Docker (computer di sviluppo Windows)</span><span class="sxs-lookup"><span data-stu-id="6ada9-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="6ada9-114">È consigliabile usare Visual Studio 2017 (o versione successiva) con gli strumenti di Docker predefinita abilitata.</span><span class="sxs-lookup"><span data-stu-id="6ada9-114">We recommend you use Visual Studio 2017 (or later) with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="6ada9-115">Con Visual Studio, è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente Docker selezionato.</span><span class="sxs-lookup"><span data-stu-id="6ada9-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="6ada9-116">Premere F5 per eseguire il debug dell'applicazione (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL+F5 per modificare e aggiornare l'app senza dovere ricompilare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="6ada9-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="6ada9-117">È la scelta più semplice e più potente per gli sviluppatori di Windows creare i contenitori Docker per Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="6ada9-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="6ada9-118">Visual Studio per Mac (computer di sviluppo Mac)</span><span class="sxs-lookup"><span data-stu-id="6ada9-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="6ada9-119">È possibile usare [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) durante lo sviluppo di applicazioni basate su Docker.</span><span class="sxs-lookup"><span data-stu-id="6ada9-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="6ada9-120">Visual Studio per Mac offre un ambiente IDE più avanzato rispetto a Visual Studio Code per Mac.</span><span class="sxs-lookup"><span data-stu-id="6ada9-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="6ada9-121">Opzioni relative a lingua e framework</span><span class="sxs-lookup"><span data-stu-id="6ada9-121">Language and framework choices</span></span>

<span data-ttu-id="6ada9-122">È possibile sviluppare applicazioni Docker con strumenti di Microsoft con i linguaggi più moderni.</span><span class="sxs-lookup"><span data-stu-id="6ada9-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="6ada9-123">Di seguito è riportato un elenco iniziale, ma non è necessario limitarsi a esso:</span><span class="sxs-lookup"><span data-stu-id="6ada9-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="6ada9-124">.NET Core e ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6ada9-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="6ada9-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="6ada9-125">Node.js</span></span>
- <span data-ttu-id="6ada9-126">Vai</span><span class="sxs-lookup"><span data-stu-id="6ada9-126">Go</span></span>
- <span data-ttu-id="6ada9-127">Java</span><span class="sxs-lookup"><span data-stu-id="6ada9-127">Java</span></span>
- <span data-ttu-id="6ada9-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="6ada9-128">Ruby</span></span>
- <span data-ttu-id="6ada9-129">Python</span><span class="sxs-lookup"><span data-stu-id="6ada9-129">Python</span></span>

<span data-ttu-id="6ada9-130">In pratica, è possibile usare qualsiasi linguaggio moderno supportato da Docker in Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="6ada9-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6ada9-131">[Precedente](deploy-azure-kubernetes-service.md)
>[Successivo](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6ada9-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
