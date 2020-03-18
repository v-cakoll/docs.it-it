---
title: Introduzione a .NET Core
description: Trova risorse per imparare a creare applicazioni .NET Core su Windows, Linux e macOS.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 0968d9db1dbfbdc8c586328ee8e02315f17950b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714387"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="3983d-103">Introduzione a .NET Core</span><span class="sxs-lookup"><span data-stu-id="3983d-103">Get started with .NET Core</span></span>

<span data-ttu-id="3983d-104">Questo articolo fornisce informazioni sui concetti introduttivi di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3983d-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="3983d-105">.NET core può essere installato in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="3983d-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="3983d-106">È possibile scrivere il codice nell'editor di testo preferito e produrre applicazioni e librerie multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="3983d-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span>

<span data-ttu-id="3983d-107">Se non si conosce .NET Core o la sua relazione con altre tecnologie .NET, iniziare con la panoramica [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) (Descrizione di .NET).</span><span class="sxs-lookup"><span data-stu-id="3983d-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="3983d-108">In poche parole, .NET Core è un'implementazione open source multipiattaforma di .NET.</span><span class="sxs-lookup"><span data-stu-id="3983d-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="3983d-109">Creare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="3983d-109">Create an application</span></span>

<span data-ttu-id="3983d-110">Per prima cosa scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download) sul computer.</span><span class="sxs-lookup"><span data-stu-id="3983d-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="3983d-111">Aprire quindi un terminale, ad esempio **PowerShell**, **prompt dei comandi**, o **bash**.</span><span class="sxs-lookup"><span data-stu-id="3983d-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="3983d-112">Digitare `dotnet` i comandi seguenti per creare ed eseguire un'applicazione in C:</span><span class="sxs-lookup"><span data-stu-id="3983d-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="3983d-113">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="3983d-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="3983d-114">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="3983d-114">Congratulations!</span></span> <span data-ttu-id="3983d-115">È stata creata una semplice applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3983d-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="3983d-116">Per creare un'applicazione .NET Core, è anche possibile usare [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (solo Windows) oppure [Visual Studio per Mac](./tutorials/using-on-mac-vs.md) (solo macOS).</span><span class="sxs-lookup"><span data-stu-id="3983d-116">You can also use [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](./tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="3983d-117">Esercitazioni</span><span class="sxs-lookup"><span data-stu-id="3983d-117">Tutorials</span></span>

<span data-ttu-id="3983d-118">Iniziare a sviluppare applicazioni .NET Core seguendo queste esercitazioni dettagliate:Get started developing .NET Core applications by following these step-by-step tutorials:</span><span class="sxs-lookup"><span data-stu-id="3983d-118">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="3983d-119">Windows</span><span class="sxs-lookup"><span data-stu-id="3983d-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="3983d-120">Creare la prima applicazione console .NET Core in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3983d-120">Create your first .NET Core console application in Visual Studio 2019</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="3983d-121">Creare una libreria di classi con .NET Standard in Visual StudioBuild a class library with .NET Standard in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3983d-121">Build a class library with .NET Standard in Visual Studio</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="3983d-122">Introduzione a .NET Core con l'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="3983d-122">Get started with .NET Core using the .NET Core CLI</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="3983d-123">![icona della telecamera per un video](./media/video-icon.png "Guardare un video")</span><span class="sxs-lookup"><span data-stu-id="3983d-123">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="3983d-124">Guarda il video [su come installare e usare Visual Studio Code e .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) su Channel 9.</span><span class="sxs-lookup"><span data-stu-id="3983d-124">Watch the [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) video on Channel 9.</span></span> |
| <span data-ttu-id="3983d-125">![icona della telecamera per un video](./media/video-icon.png "Guardare un video")</span><span class="sxs-lookup"><span data-stu-id="3983d-125">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="3983d-126">Guarda i video di [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) su YouTube.</span><span class="sxs-lookup"><span data-stu-id="3983d-126">Watch the [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) videos on YouTube.</span></span> |

<span data-ttu-id="3983d-127">Vedere l'articolo [Dependencies and requirements](install/dependencies.md?pivots=os-windows) di .NET Core per un elenco delle versioni di Windows supportate.</span><span class="sxs-lookup"><span data-stu-id="3983d-127">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linux"></a>[<span data-ttu-id="3983d-128">Linux</span><span class="sxs-lookup"><span data-stu-id="3983d-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="3983d-129">Iniziare a sviluppare applicazioni .NET Core seguendo queste esercitazioni dettagliate:Get started developing .NET Core applications by following these step-by-step tutorials:</span><span class="sxs-lookup"><span data-stu-id="3983d-129">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="3983d-130">Introduzione a .NET Core tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="3983d-130">Get started with .NET Core using the command line</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="3983d-131">![icona della telecamera per un video](./media/video-icon.png "Guardare un video")</span><span class="sxs-lookup"><span data-stu-id="3983d-131">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="3983d-132">Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="3983d-132">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span> |

<span data-ttu-id="3983d-133">Vedere l'articolo [Dipendenze e requisiti](install/dependencies.md?pivots=os-linux) di .NET Core per un elenco delle distribuzioni e delle versioni di Linux supportate.</span><span class="sxs-lookup"><span data-stu-id="3983d-133">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macos"></a>[<span data-ttu-id="3983d-134">Macos</span><span class="sxs-lookup"><span data-stu-id="3983d-134">macOS</span></span>](#tab/macos)

<span data-ttu-id="3983d-135">Iniziare a sviluppare applicazioni .NET Core seguendo queste esercitazioni dettagliate:Get started developing .NET Core applications by following these step-by-step tutorials:</span><span class="sxs-lookup"><span data-stu-id="3983d-135">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="3983d-136">Introduzione all'uso di .NET Core su macOS con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3983d-136">Get started with .NET Core on macOS using Visual Studio Code</span></span>](./tutorials/using-on-macos.md)
- [<span data-ttu-id="3983d-137">Introduzione a .NET Core tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="3983d-137">Get started with .NET Core using the command-line</span></span>](./tutorials/cli-create-console-app.md)
- [<span data-ttu-id="3983d-138">Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="3983d-138">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="3983d-139">Creare una soluzione .NET Core completa in macOS usando Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="3983d-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| <span data-ttu-id="3983d-140">![icona della telecamera per un video](media/video-icon.png "Guardare un video")</span><span class="sxs-lookup"><span data-stu-id="3983d-140">![movie camera icon for video](media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="3983d-141">Guardare un video su come iniziare a usare il codice di [Visual Studio usando C .NET Core in macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="3983d-141">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span> |

<span data-ttu-id="3983d-142">Vedere l'articolo [Dipendenze e requisiti](install/dependencies.md?pivots=os-macos) di .NET Core per un elenco delle versioni di OS X / macOS supportate.</span><span class="sxs-lookup"><span data-stu-id="3983d-142">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
