---
title: Processo di sviluppo per le applicazioni basate su Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Processo di sviluppo per le applicazioni basate su Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 61bc9ca6fed8f5249dcb125619aa1b07f290ba7e
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106879"
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="1b9f4-103">Processo di sviluppo per le applicazioni basate su Docker</span><span class="sxs-lookup"><span data-stu-id="1b9f4-103">Development Process for Docker-Based Applications</span></span>

<span data-ttu-id="1b9f4-104">*È possibile sviluppare applicazioni .NET incluse in contenitori come si preferisce, sia basandosi su IDE con Visual Studio e Visual Studio Tools per Docker oppure su editor/CLI con CLI di Docker e Visual Studio Code.*</span><span class="sxs-lookup"><span data-stu-id="1b9f4-104">*Develop containerized .NET applications the way you like, either IDE focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="1b9f4-105">Ambiente di sviluppo per le app di Docker</span><span class="sxs-lookup"><span data-stu-id="1b9f4-105">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="1b9f4-106">Strumenti di sviluppo: IDE o editor</span><span class="sxs-lookup"><span data-stu-id="1b9f4-106">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="1b9f4-107">Microsoft include strumenti che è possibile usare per lo sviluppo di applicazioni di Docker, sia se si sceglie un IDE potente e completo che con un editor semplice e agile.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-107">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="1b9f4-108">**Visual Studio (per Windows)**.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-108">**Visual Studio (for Windows)**.</span></span> <span data-ttu-id="1b9f4-109">Per sviluppare applicazioni basate su Docker, usare Visual Studio 2017 o versioni successive in cui sono disponibili gli strumenti per Docker già incorporati.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-109">To develop Docker-based applications, use Visual Studio 2017 or later versions that comes with tools for Docker already built-in.</span></span> <span data-ttu-id="1b9f4-110">Gli strumenti per Docker consentono di sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-110">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="1b9f4-111">È possibile premere F5 per eseguire l'applicazione ed eseguirne il debug (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL + F5 per modificare e aggiornare l'applicazione senza dovere ricompilare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-111">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="1b9f4-112">Questa è la scelta di sviluppo più potente per le app basate su Docker.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-112">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="1b9f4-113">**Visual Studio per Mac**.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-113">**Visual Studio for Mac**.</span></span> <span data-ttu-id="1b9f4-114">È un ambiente IDE, evoluzione di Xamarin Studio, che viene eseguito su macOS e supporta lo sviluppo di applicazioni basate su Docker.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-114">It is an IDE, evolution of Xamarin Studio, that runs on macOS and supports Docker-based application development.</span></span> <span data-ttu-id="1b9f4-115">È la scelta più indicata per gli sviluppatori che lavorano in computer Mac che vogliono anche usare un potente IDE.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-115">This should be the preferred choice for developers working in Mac machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="1b9f4-116">**Visual Studio Code e CLI di Docker**.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-116">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="1b9f4-117">Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Microsoft Visual Studio Code (codice Visual Studio) e l'interfaccia CLI di Docker.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-117">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Microsoft Visual Studio Code (VS Code) and the Docker CLI.</span></span> <span data-ttu-id="1b9f4-118">Questo approccio di sviluppo multipiattaforma è adatto per Mac, Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-118">This is a cross-platform development approach for Mac, Linux, and Windows.</span></span>

<span data-ttu-id="1b9f4-119">Installando gli strumenti di [Docker Community Edition (CE)](https://www.docker.com/community-edition), è possibile usare un'interfaccia CLI di Docker singola per creare app per Windows e Linux.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-119">By installing [Docker Community Edition (CE)](https://www.docker.com/community-edition) tools, you can use a single Docker CLI to build apps for both Windows and Linux.</span></span> <span data-ttu-id="1b9f4-120">Inoltre, Visual Studio Code supporta le estensioni per Docker, quali IntelliSense per Dockerfile e le attività collegamento per eseguire i comandi di Docker dall'editor.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-120">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1b9f4-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1b9f4-121">Additional resources</span></span>

-   <span data-ttu-id="1b9f4-122">**Visual Studio Tools per Docker**
    [*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span><span class="sxs-lookup"><span data-stu-id="1b9f4-122">**Visual Studio Tools for Docker**
[*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>

-   <span data-ttu-id="1b9f4-123">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-123">**Visual Studio Code**.</span></span> <span data-ttu-id="1b9f4-124">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-124">Official site.</span></span>
    [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

-   <span data-ttu-id="1b9f4-125">**Docker Community Edition (CE) per Mac e Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span><span class="sxs-lookup"><span data-stu-id="1b9f4-125">**Docker Community Edition (CE) for Mac and Windows**
[*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span></span>

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="1b9f4-126">Linguaggi e framework .NET per contenitori di Docker</span><span class="sxs-lookup"><span data-stu-id="1b9f4-126">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="1b9f4-127">Come indicato nelle sezioni precedenti di questa guida, è possibile usare .NET Framework, .NET Core o il progetto Mono open source per lo sviluppo di applicazioni .NET incluse in contenitori di Docker.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-127">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="1b9f4-128">È possibile sviluppare in C\#, F\# o Visual Basic quando si usano contenitori di Linux o Windows, a seconda del framework .NET in uso.</span><span class="sxs-lookup"><span data-stu-id="1b9f4-128">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="1b9f4-129">Per altri dettagli sui linguaggi .NET, vedere il post di blog [The .NET Language Strategy (La strategia dei linguaggi .NET)](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span><span class="sxs-lookup"><span data-stu-id="1b9f4-129">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="1b9f4-130">[Precedente](../architect-microservice-container-applications/using-azure-service-fabric.md)
[Successivo](docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1b9f4-130">[Previous](../architect-microservice-container-applications/using-azure-service-fabric.md)
[Next](docker-app-development-workflow.md)</span></span>
