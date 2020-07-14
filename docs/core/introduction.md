---
title: Introduzione e Panoramica di .NET Core
description: .NET Core è un'implementazione modulare e a elevate prestazioni di .NET per la creazione di app Windows, Linux e macOS. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: b28ad965e54680e2e1134c389266741ade28084f
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226582"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="8cc71-104">Introduzione a .NET Core</span><span class="sxs-lookup"><span data-stu-id="8cc71-104">Introduction to .NET Core</span></span>

<span data-ttu-id="8cc71-105">[.NET Core](about.md) è una piattaforma di sviluppo [Open Source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)per utilizzo generico.</span><span class="sxs-lookup"><span data-stu-id="8cc71-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="8cc71-106">È possibile creare app .NET Core per Windows, macOS e Linux per processori x64, x86, ARM32 e ARM64 usando più linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8cc71-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="8cc71-107">I Framework e le API sono forniti [cloud](/aspnet/core/)per cloud [, Internet delle cose,](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0) [interfaccia utente client](../desktop-wpf/overview/index.md)e [Machine Learning](/dotnet/machine-learning/).</span><span class="sxs-lookup"><span data-stu-id="8cc71-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](../desktop-wpf/overview/index.md), and [machine learning](/dotnet/machine-learning/).</span></span>

<span data-ttu-id="8cc71-108">[Scaricare il .NET Core SDK](https://dotnet.microsoft.com/download) per provare .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="8cc71-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="8cc71-109">La versione più recente è [.NET Core 3,1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="8cc71-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="8cc71-110">Download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="8cc71-110">Download .NET Core</span></span>

<span data-ttu-id="8cc71-111">È possibile ottenere .NET Core nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cc71-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="8cc71-112">Programmi di installazione per Windows e macOS</span><span class="sxs-lookup"><span data-stu-id="8cc71-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="8cc71-113">Pacchetti Linux</span><span class="sxs-lookup"><span data-stu-id="8cc71-113">Linux packages</span></span>](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [<span data-ttu-id="8cc71-114">Contenitori Docker</span><span class="sxs-lookup"><span data-stu-id="8cc71-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="8cc71-115">Zip e tarball</span><span class="sxs-lookup"><span data-stu-id="8cc71-115">Zips and tarballs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="8cc71-116">Script di installazione</span><span class="sxs-lookup"><span data-stu-id="8cc71-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="8cc71-117">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="8cc71-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="8cc71-118">Creare la prima applicazione</span><span class="sxs-lookup"><span data-stu-id="8cc71-118">Create your first application</span></span>

<span data-ttu-id="8cc71-119">Dopo aver installato .NET Core SDK, aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8cc71-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="8cc71-120">Usare i comandi seguenti per creare ed eseguire un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="8cc71-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="8cc71-121">Dovrebbe venire visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="8cc71-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="8cc71-122">Collabora</span><span class="sxs-lookup"><span data-stu-id="8cc71-122">Contribute</span></span>

<span data-ttu-id="8cc71-123">.NET Core è una piattaforma aperta.</span><span class="sxs-lookup"><span data-stu-id="8cc71-123">.NET Core is an open platform.</span></span> <span data-ttu-id="8cc71-124">Tutti gli utenti sono invitati a partecipare.</span><span class="sxs-lookup"><span data-stu-id="8cc71-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="8cc71-125">Problemi relativi ai prodotti e alle domande [della community degli sviluppatori](https://developercommunity.visualstudio.com/spaces/61/index.html).</span><span class="sxs-lookup"><span data-stu-id="8cc71-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="8cc71-126">I contributi ai prodotti devono essere effettuati in uno dei repository del progetto, ad esempio [DotNet/Runtime](https://github.com/dotnet/runtime), [DotNet/SDK](https://github.com/dotnet/sdk), [DotNet/Rosyln](https://github.com/dotnet/roslyn)o [aspnetcore](https://github.com/dotnet/aspnetcore).</span><span class="sxs-lookup"><span data-stu-id="8cc71-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="8cc71-127">Per altre informazioni, vedere [repository di .NET Core](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span><span class="sxs-lookup"><span data-stu-id="8cc71-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="8cc71-128">Supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="8cc71-128">Support</span></span>

<span data-ttu-id="8cc71-129">.NET Core è supportato da Microsoft in Windows, macOS e Linux e da Red Hat su Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="8cc71-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8cc71-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8cc71-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8cc71-131">Esercitazioni su .NET Core</span><span class="sxs-lookup"><span data-stu-id="8cc71-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="8cc71-132">Prova .NET Core nel browser</span><span class="sxs-lookup"><span data-stu-id="8cc71-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
