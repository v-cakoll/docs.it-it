---
title: Ambiente di sviluppo per le app di Docker
description: Informazioni sulle opzioni più importanti dello strumento di sviluppo che supportano il ciclo di vita di sviluppo Docker.
ms.date: 04/16/2020
ms.openlocfilehash: b1df16db88fa85f794407c989f5428030c4cddf7
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394893"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="94790-103">Ambiente di sviluppo per le app di Docker</span><span class="sxs-lookup"><span data-stu-id="94790-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="94790-104">Opzioni degli strumenti di sviluppo: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="94790-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="94790-105">Indipendentemente dal fatto che si preferisca usare un IDE completo e potente o un editor leggero e flessibile, Microsoft offre tutti gli strumenti necessari per lo sviluppo delle applicazioni Docker.</span><span class="sxs-lookup"><span data-stu-id="94790-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="94790-106">Visual Studio Code e interfaccia della riga di comando di Docker (strumenti multipiattaforma per Mac, Linux e Windows)</span><span class="sxs-lookup"><span data-stu-id="94790-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="94790-107">Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Visual Studio Code e l'interfaccia della riga di comando di Docker.</span><span class="sxs-lookup"><span data-stu-id="94790-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="94790-108">Questi prodotti offrono un'esperienza semplice ed efficace che consente di ottimizzare il flusso di lavoro di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="94790-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="94790-109">Installando "Docker per Mac" o "Docker per Windows" (ambiente di sviluppo), gli sviluppatori Docker possono usare una singola interfaccia della riga di comando di Docker per creare app per Windows o Linux (ambiente di runtime).</span><span class="sxs-lookup"><span data-stu-id="94790-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="94790-110">Inoltre, Visual Studio Code supporta le estensioni per Docker con IntelliSense per Dockerfile e le attività collegamento per eseguire i comandi Docker dall'editor.</span><span class="sxs-lookup"><span data-stu-id="94790-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="94790-111">Per scaricare Visual Studio Code, visitare <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="94790-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="94790-112">Per scaricare Docker per Mac e Windows, visitare <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="94790-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="94790-113">Visual Studio con strumenti Docker (computer di sviluppo Windows)</span><span class="sxs-lookup"><span data-stu-id="94790-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="94790-114">È consigliabile usare Visual Studio 2019 con gli strumenti Docker predefiniti abilitati.</span><span class="sxs-lookup"><span data-stu-id="94790-114">We recommend you use Visual Studio 2019 with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="94790-115">Con Visual Studio è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente Docker selezionato.</span><span class="sxs-lookup"><span data-stu-id="94790-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="94790-116">Premere F5 per eseguire il debug dell'applicazione (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL+F5 per modificare e aggiornare l'applicazione senza dovere ricompilare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="94790-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="94790-117">Questa è la soluzione più semplice ed efficace per gli sviluppatori di Windows per creare contenitori di Docker per Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="94790-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="94790-118">Visual Studio per Mac (computer di sviluppo Mac)</span><span class="sxs-lookup"><span data-stu-id="94790-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="94790-119">È possibile usare [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per lo sviluppo di applicazioni basate su Docker.</span><span class="sxs-lookup"><span data-stu-id="94790-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="94790-120">Visual Studio per Mac offre un ambiente IDE più avanzato rispetto a Visual Studio Code per Mac.</span><span class="sxs-lookup"><span data-stu-id="94790-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="94790-121">Linguaggio e framework</span><span class="sxs-lookup"><span data-stu-id="94790-121">Language and framework choices</span></span>

<span data-ttu-id="94790-122">È possibile sviluppare applicazioni Docker con gli strumenti Microsoft con i linguaggi più moderni.</span><span class="sxs-lookup"><span data-stu-id="94790-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="94790-123">L'elenco riportato di seguito è un elenco iniziale non completo:</span><span class="sxs-lookup"><span data-stu-id="94790-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="94790-124">.NET Core e ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="94790-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="94790-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="94790-125">Node.js</span></span>
- <span data-ttu-id="94790-126">Go</span><span class="sxs-lookup"><span data-stu-id="94790-126">Go</span></span>
- <span data-ttu-id="94790-127">Java</span><span class="sxs-lookup"><span data-stu-id="94790-127">Java</span></span>
- <span data-ttu-id="94790-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="94790-128">Ruby</span></span>
- <span data-ttu-id="94790-129">Python</span><span class="sxs-lookup"><span data-stu-id="94790-129">Python</span></span>

<span data-ttu-id="94790-130">In pratica, è possibile usare qualsiasi linguaggio moderno supportato da Docker in Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="94790-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="94790-131">[Precedente](deploy-azure-kubernetes-service.md) 
> [Avanti](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="94790-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
