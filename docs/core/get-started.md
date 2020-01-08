---
title: Introduzione a .NET Core
description: Risorse per imparare a creare applicazioni .NET Core in Windows, Linux e macOS.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bcf9ea0bb9a8346284c49060786afefa0f77745e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341384"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="a473c-103">Introduzione a .NET Core</span><span class="sxs-lookup"><span data-stu-id="a473c-103">Get started with .NET Core</span></span>

<span data-ttu-id="a473c-104">Questo articolo fornisce informazioni sui concetti introduttivi di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a473c-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="a473c-105">.NET core può essere installato in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="a473c-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="a473c-106">È possibile scrivere il codice nell'editor di testo preferito e produrre applicazioni e librerie multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="a473c-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span>

<span data-ttu-id="a473c-107">Se non si conosce .NET Core o la sua relazione con altre tecnologie .NET, iniziare con la panoramica [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) (Descrizione di .NET).</span><span class="sxs-lookup"><span data-stu-id="a473c-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="a473c-108">In poche parole, .NET Core è un'implementazione open source multipiattaforma di .NET.</span><span class="sxs-lookup"><span data-stu-id="a473c-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="a473c-109">Creare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="a473c-109">Create an application</span></span>

<span data-ttu-id="a473c-110">Per prima cosa scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download) sul computer.</span><span class="sxs-lookup"><span data-stu-id="a473c-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="a473c-111">Aprire quindi un terminale, ad esempio **PowerShell**, **prompt dei comandi**, o **bash**.</span><span class="sxs-lookup"><span data-stu-id="a473c-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="a473c-112">Digitare i seguenti comandi di `dotnet` per creare ed eseguire C# un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="a473c-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="a473c-113">È necessario visualizzare il seguente output:</span><span class="sxs-lookup"><span data-stu-id="a473c-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="a473c-114">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="a473c-114">Congratulations!</span></span> <span data-ttu-id="a473c-115">È stata creata una semplice applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a473c-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="a473c-116">Per creare un'applicazione .NET Core, è anche possibile usare [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (solo Windows) oppure [Visual Studio per Mac](./tutorials/using-on-mac-vs.md) (solo macOS).</span><span class="sxs-lookup"><span data-stu-id="a473c-116">You can also use [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](./tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="a473c-117">Esercitazioni</span><span class="sxs-lookup"><span data-stu-id="a473c-117">Tutorials</span></span>

<span data-ttu-id="a473c-118">Per iniziare a sviluppare applicazioni .NET Core, seguire queste esercitazioni dettagliate:</span><span class="sxs-lookup"><span data-stu-id="a473c-118">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="a473c-119">Windows</span><span class="sxs-lookup"><span data-stu-id="a473c-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="a473c-120">Creare la prima applicazione console .NET Core in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a473c-120">Create your first .NET Core console application in Visual Studio 2019</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="a473c-121">Creare una libreria di classi con .NET Standard in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a473c-121">Build a class library with .NET Standard in Visual Studio</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="a473c-122">Introduzione a .NET Core con la interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a473c-122">Get started with .NET Core using the .NET Core CLI</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="a473c-123">![icona della telecamera per un video](./media/video-icon.png "Guarda un video")</span><span class="sxs-lookup"><span data-stu-id="a473c-123">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a473c-124">Vedere le [procedure per installare e usare Visual Studio Code e](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) il video di .NET Core su Channel 9.</span><span class="sxs-lookup"><span data-stu-id="a473c-124">Watch the [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) video on Channel 9.</span></span> |
| <span data-ttu-id="a473c-125">![icona della telecamera per un video](./media/video-icon.png "Guarda un video")</span><span class="sxs-lookup"><span data-stu-id="a473c-125">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a473c-126">Guarda i video su [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) su YouTube.</span><span class="sxs-lookup"><span data-stu-id="a473c-126">Watch the [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) videos on YouTube.</span></span> |

<span data-ttu-id="a473c-127">Per un elenco delle versioni supportate di Windows, vedere l'articolo relativo alle [dipendenze e ai requisiti di .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-windows) .</span><span class="sxs-lookup"><span data-stu-id="a473c-127">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) article for a list of the supported Windows versions.</span></span>

<span data-ttu-id="a473c-128">Per un elenco delle versioni supportate di Windows, vedere l'articolo sulle [dipendenze .NET Core SDK e di runtime](install/dependencies.md?pivots=os-windows) .</span><span class="sxs-lookup"><span data-stu-id="a473c-128">See the [.NET Core SDK and runtime dependencies](install/dependencies.md?pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="a473c-129">Linux</span><span class="sxs-lookup"><span data-stu-id="a473c-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="a473c-130">Per iniziare a sviluppare applicazioni .NET Core, seguire queste esercitazioni dettagliate:</span><span class="sxs-lookup"><span data-stu-id="a473c-130">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="a473c-131">Introduzione a .NET Core tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="a473c-131">Get started with .NET Core using the command-line</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="a473c-132">![icona della telecamera per un video](./media/video-icon.png "Guarda un video")</span><span class="sxs-lookup"><span data-stu-id="a473c-132">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a473c-133">Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="a473c-133">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span> |

<span data-ttu-id="a473c-134">Per un elenco delle distribuzioni e delle versioni di Linux supportate, vedere l'articolo sulle [dipendenze di .NET Core SDK e Runtime](install/dependencies.md?pivots=os-linux) .</span><span class="sxs-lookup"><span data-stu-id="a473c-134">See the [.NET Core SDK and runtime dependencies](install/dependencies.md?pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="a473c-135">macOS</span><span class="sxs-lookup"><span data-stu-id="a473c-135">macOS</span></span>](#tab/macos)

<span data-ttu-id="a473c-136">Per iniziare a sviluppare applicazioni .NET Core, seguire queste esercitazioni dettagliate:</span><span class="sxs-lookup"><span data-stu-id="a473c-136">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="a473c-137">Introduzione a .NET Core su macOS con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a473c-137">Get started with .NET Core on macOS using Visual Studio Code</span></span>](./tutorials/using-on-macos.md)
- [<span data-ttu-id="a473c-138">Introduzione a .NET Core tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="a473c-138">Get started with .NET Core using the command-line</span></span>](./tutorials/cli-create-console-app.md)
- [<span data-ttu-id="a473c-139">Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="a473c-139">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="a473c-140">Creare una soluzione .NET Core completa in macOS usando Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="a473c-140">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| <span data-ttu-id="a473c-141">![icona della telecamera per un video](media/video-icon.png "Guarda un video")</span><span class="sxs-lookup"><span data-stu-id="a473c-141">![movie camera icon for video](media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a473c-142">Guarda un video su [come iniziare a usare C# Visual Studio Code con e .NET Core in MacOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="a473c-142">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span> |

<span data-ttu-id="a473c-143">Per un elenco delle versioni di OS X/macOS supportate, vedere l'articolo sulle [dipendenze .NET Core SDK e di runtime](install/dependencies.md?pivots=os-macos) .</span><span class="sxs-lookup"><span data-stu-id="a473c-143">See the [.NET Core SDK and runtime dependencies](install/dependencies.md?pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
