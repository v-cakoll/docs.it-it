---
title: Introduzione a .NET Core
description: Risorse per imparare a creare applicazioni .NET Core in Windows, Linux e macOS.
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 78066f2904f6a874b71165e4fe1769b6b778ae41
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428873"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="ce196-103">Introduzione a .NET Core</span><span class="sxs-lookup"><span data-stu-id="ce196-103">Get started with .NET Core</span></span>

<span data-ttu-id="ce196-104">Questo articolo fornisce informazioni sui concetti introduttivi di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce196-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="ce196-105">.NET core può essere installato in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="ce196-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="ce196-106">È possibile scrivere il codice nell'editor di testo preferito e produrre applicazioni e librerie multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="ce196-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="ce196-107">Se non si conosce .NET Core o la sua relazione con altre tecnologie .NET, iniziare con la panoramica [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) (Descrizione di .NET).</span><span class="sxs-lookup"><span data-stu-id="ce196-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="ce196-108">In poche parole, .NET Core è un'implementazione open source multipiattaforma di .NET.</span><span class="sxs-lookup"><span data-stu-id="ce196-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="ce196-109">Creare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="ce196-109">Create an application</span></span>

<span data-ttu-id="ce196-110">Per prima cosa scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download) sul computer.</span><span class="sxs-lookup"><span data-stu-id="ce196-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="ce196-111">Aprire quindi un terminale, ad esempio **PowerShell**, **prompt dei comandi**, o **bash**.</span><span class="sxs-lookup"><span data-stu-id="ce196-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="ce196-112">Type the following `dotnet` commands to create and run a C# application:</span><span class="sxs-lookup"><span data-stu-id="ce196-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="ce196-113">È necessario visualizzare il seguente output:</span><span class="sxs-lookup"><span data-stu-id="ce196-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="ce196-114">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ce196-114">Congratulations!</span></span> <span data-ttu-id="ce196-115">È stata creata una semplice applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce196-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="ce196-116">Per creare un'applicazione .NET Core, è anche possibile usare [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (solo Windows) oppure [Visual Studio per Mac](tutorials/using-on-mac-vs.md) (solo macOS).</span><span class="sxs-lookup"><span data-stu-id="ce196-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="ce196-117">Esercitazioni</span><span class="sxs-lookup"><span data-stu-id="ce196-117">Tutorials</span></span>

<span data-ttu-id="ce196-118">È possibile iniziare lo sviluppo di applicazioni .NET Core seguendo queste esercitazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="ce196-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="ce196-119">Windows</span><span class="sxs-lookup"><span data-stu-id="ce196-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="ce196-120">Compilare un'applicazione Hello World usando C# con .NET Core in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ce196-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="ce196-121">Creazione di una libreria di classi con C# con .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce196-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="ce196-122">Creazione di un'applicazione Hello World in Visual Basic con .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce196-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)
- [<span data-ttu-id="ce196-123">Creazione di una libreria di classi con Visual Basic e .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ce196-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  
- <span data-ttu-id="ce196-124">Guardare un video su [come installare e usare Visual Studio Code e .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span><span class="sxs-lookup"><span data-stu-id="ce196-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>
- <span data-ttu-id="ce196-125">Guardare un video su [come installare e usare Visual Studio 2017 e .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span><span class="sxs-lookup"><span data-stu-id="ce196-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>
- [<span data-ttu-id="ce196-126">Introduzione all'uso di .NET Core usando la riga di comando</span><span class="sxs-lookup"><span data-stu-id="ce196-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

<span data-ttu-id="ce196-127">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) article for a list of the supported Windows versions.</span><span class="sxs-lookup"><span data-stu-id="ce196-127">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="ce196-128">Linux</span><span class="sxs-lookup"><span data-stu-id="ce196-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="ce196-129">You can get started developing .NET Core application by following these step-by-step tutorials:</span><span class="sxs-lookup"><span data-stu-id="ce196-129">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="ce196-130">Introduzione all'uso di .NET Core usando la riga di comando</span><span class="sxs-lookup"><span data-stu-id="ce196-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)
- <span data-ttu-id="ce196-131">Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="ce196-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="ce196-132">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux) article for a list of the supported Linux distros and versions.</span><span class="sxs-lookup"><span data-stu-id="ce196-132">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="ce196-133">macOS</span><span class="sxs-lookup"><span data-stu-id="ce196-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="ce196-134">You can get started developing .NET Core application by following these step-by-step tutorials:</span><span class="sxs-lookup"><span data-stu-id="ce196-134">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- <span data-ttu-id="ce196-135">Guardare un video sull'[Introduzione a Visual Studio Code con C# e .NET Core in macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span><span class="sxs-lookup"><span data-stu-id="ce196-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>
- [<span data-ttu-id="ce196-136">Introduzione all'uso di .NET Core su macOS con Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ce196-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)
- [<span data-ttu-id="ce196-137">Introduzione all'uso di .NET Core usando la riga di comando</span><span class="sxs-lookup"><span data-stu-id="ce196-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)
- [<span data-ttu-id="ce196-138">Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="ce196-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="ce196-139">Creazione di una soluzione .NET Core completa in macOS con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="ce196-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="ce196-140">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos) article for a list of the supported OS X / macOS versions.</span><span class="sxs-lookup"><span data-stu-id="ce196-140">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
