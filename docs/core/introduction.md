---
title: Introduzione e panoramica di .NET Core
description: .NET Core è un'implementazione modulare e ad alte prestazioni di .NET per la creazione di app Windows, Linux e macOS. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: a20cdda5cbd366d04e7ee9e8df3d1b15d10c1f4a
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391160"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="b931c-104">Introduzione a .NET Core</span><span class="sxs-lookup"><span data-stu-id="b931c-104">Introduction to .NET Core</span></span>

<span data-ttu-id="b931c-105">[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)generica.</span><span class="sxs-lookup"><span data-stu-id="b931c-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="b931c-106">Puoi creare app .NET Core per processori Windows, macOS e Linux per x64, x86, ARM32 e ARM64 usando più linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="b931c-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="b931c-107">Framework e API vengono forniti per [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [interfaccia utente client](/dotnet/desktop-wpf/overview/index)e machine [learning](/dotnet/machine-learning/).</span><span class="sxs-lookup"><span data-stu-id="b931c-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](/dotnet/desktop-wpf/overview/index), and [machine learning](/dotnet/machine-learning/).</span></span>

<span data-ttu-id="b931c-108">[Scaricare .NET Core SDK](https://dotnet.microsoft.com/download) per provare .NET Core nel computer.</span><span class="sxs-lookup"><span data-stu-id="b931c-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="b931c-109">La versione più recente è [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="b931c-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="b931c-110">Download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="b931c-110">Download .NET Core</span></span>

<span data-ttu-id="b931c-111">È possibile ottenere .NET Core nei modi seguenti:You can get .NET Core in the following ways:</span><span class="sxs-lookup"><span data-stu-id="b931c-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="b931c-112">Programmi di installazione per Windows e macOS</span><span class="sxs-lookup"><span data-stu-id="b931c-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="b931c-113">Pacchetti Linux</span><span class="sxs-lookup"><span data-stu-id="b931c-113">Linux packages</span></span>](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [<span data-ttu-id="b931c-114">Contenitori Docker</span><span class="sxs-lookup"><span data-stu-id="b931c-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="b931c-115">zip e palle di catrame</span><span class="sxs-lookup"><span data-stu-id="b931c-115">Zips and tar balls</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="b931c-116">Installare gli script</span><span class="sxs-lookup"><span data-stu-id="b931c-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="b931c-117">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="b931c-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="b931c-118">Creare la prima applicazione</span><span class="sxs-lookup"><span data-stu-id="b931c-118">Create your first application</span></span>

<span data-ttu-id="b931c-119">Dopo aver installato .NET Core SDK, aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b931c-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="b931c-120">Utilizzare i comandi seguenti per creare ed eseguire un'applicazione:Use the following commands to create and run an application:</span><span class="sxs-lookup"><span data-stu-id="b931c-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="b931c-121">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="b931c-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="b931c-122">Contribuire</span><span class="sxs-lookup"><span data-stu-id="b931c-122">Contribute</span></span>

<span data-ttu-id="b931c-123">.NET Core è una piattaforma aperta.</span><span class="sxs-lookup"><span data-stu-id="b931c-123">.NET Core is an open platform.</span></span> <span data-ttu-id="b931c-124">Tutti sono invitati a partecipare.</span><span class="sxs-lookup"><span data-stu-id="b931c-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="b931c-125">Archiviare problemi e domande sul prodotto [nella community degli sviluppatori](https://developercommunity.visualstudio.com/spaces/61/index.html).</span><span class="sxs-lookup"><span data-stu-id="b931c-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="b931c-126">I contributi del prodotto devono essere effettuati in uno dei repository di progetto, ad esempio [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn)o [aspnetcore](https://github.com/dotnet/aspnetcore).</span><span class="sxs-lookup"><span data-stu-id="b931c-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="b931c-127">Per ulteriori informazioni, vedere [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span><span class="sxs-lookup"><span data-stu-id="b931c-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="b931c-128">Supporto</span><span class="sxs-lookup"><span data-stu-id="b931c-128">Support</span></span>

<span data-ttu-id="b931c-129">.NET Core è supportato da Microsoft su Windows, macOS e Linux e da Red Hat su Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="b931c-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b931c-130">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b931c-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b931c-131">Esercitazioni di .NET Core</span><span class="sxs-lookup"><span data-stu-id="b931c-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="b931c-132">Prova .NET Core nel tuo browser</span><span class="sxs-lookup"><span data-stu-id="b931c-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
