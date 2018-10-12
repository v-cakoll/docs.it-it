---
title: Guida a .NET Core
description: .NET core è un'implementazione modulare ad alte prestazioni di .NET per la creazione di app di Windows, Mac e Linux. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: b302b6fc7e097a811c718d2244f603246cb5c259
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49121038"
---
# <a name="net-core-guide"></a><span data-ttu-id="431d1-104">Guida a .NET Core</span><span class="sxs-lookup"><span data-stu-id="431d1-104">.NET Core Guide</span></span>

<span data-ttu-id="431d1-105">[.NET Core](about.md) è una piattaforma [open source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) di sviluppo generale gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="431d1-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="431d1-106">È multipiattaforma, supporta Windows, macOS e Linux e può essere usata in applicazioni per dispositivi, cloud e IoT.</span><span class="sxs-lookup"><span data-stu-id="431d1-106">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and IoT applications.</span></span>

<span data-ttu-id="431d1-107">Vedere [Informazioni su .NET Core](about.md) per altre informazioni su .NET Core, inclusi le caratteristiche, i linguaggi e i framework supportati e le principali API.</span><span class="sxs-lookup"><span data-stu-id="431d1-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="431d1-108">Per imparare a creare una semplice applicazione .NET Core, vedere le [Esercitazioni di .NET Core](tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="431d1-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="431d1-109">Sono necessari pochi minuti per realizzare ed eseguire la prima app.</span><span class="sxs-lookup"><span data-stu-id="431d1-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="431d1-110">Se si vuole provare .NET Core nel browser, vedere la guida introduttiva [Numeri in C#](https://docs.microsoft.com/dotnet/csharp/quick-starts/numbers-in-csharp).</span><span class="sxs-lookup"><span data-stu-id="431d1-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](https://docs.microsoft.com/dotnet/csharp/quick-starts/numbers-in-csharp) quickstart.</span></span>

## <a name="download-net-core-21"></a><span data-ttu-id="431d1-111">Scaricare .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="431d1-111">Download .NET Core 2.1</span></span>

<span data-ttu-id="431d1-112">Scaricare [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) per provare .NET Core nel computer Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="431d1-112">Download the [.NET Core  2.1 SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="431d1-113">Visitare [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) se si preferisce usare i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="431d1-113">Visit [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) if you prefer to use Docker containers.</span></span>

<span data-ttu-id="431d1-114">Tutte le versioni di .NET Core sono disponibili nella pagina [Download di .NET Core](https://www.microsoft.com/net/download/archives) se si sta cercando un'altra versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="431d1-114">All .NET Core versions are available at [.NET Core Downloads](https://www.microsoft.com/net/download/archives) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="431d1-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="431d1-115">.NET Core 2.1</span></span>

<span data-ttu-id="431d1-116">La versione più recente è [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span><span class="sxs-lookup"><span data-stu-id="431d1-116">The latest version is [.NET Core 2.1](whats-new/dotnet-core-2-1.md).</span></span> <span data-ttu-id="431d1-117">Le nuove funzionalità includono: strumenti globali, API ad alte prestazioni (ad esempio <xref:System.Span%601?displayProperty=nameWithType>), compilazione JIT a livelli, miglioramenti della [compilazione](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) e [miglioramenti delle prestazioni di runtime](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/) e il supporto per Alpine e ARM32.</span><span class="sxs-lookup"><span data-stu-id="431d1-117">New features include: global tools, high-performance APIs (such as <xref:System.Span%601?displayProperty=nameWithType>), tiered JIT compilation, [build](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and [runtime performance improvements](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/), and support for Alpine and ARM32.</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="431d1-118">Creare la prima applicazione</span><span class="sxs-lookup"><span data-stu-id="431d1-118">Create your first application</span></span>

<span data-ttu-id="431d1-119">Dopo aver installato .NET Core SDK, aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="431d1-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="431d1-120">Digitare i seguenti comandi `dotnet` per creare ed eseguire un'applicazione C#.</span><span class="sxs-lookup"><span data-stu-id="431d1-120">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="431d1-121">È necessario visualizzare il seguente output:</span><span class="sxs-lookup"><span data-stu-id="431d1-121">You should see the following output:</span></span>

```console
Hello World!
```

## <a name="support"></a><span data-ttu-id="431d1-122">Supporto</span><span class="sxs-lookup"><span data-stu-id="431d1-122">Support</span></span>

<span data-ttu-id="431d1-123">.NET Core è [supportato da Microsoft](https://www.microsoft.com/net/support/policy) in Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="431d1-123">.NET Core is [supported by Microsoft](https://www.microsoft.com/net/support/policy), on Windows, macOS and Linux.</span></span> <span data-ttu-id="431d1-124">Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.</span><span class="sxs-lookup"><span data-stu-id="431d1-124">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="431d1-125">Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="431d1-125">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="431d1-126">[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="431d1-126">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="431d1-127">Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="431d1-127">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="431d1-128">Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.</span><span class="sxs-lookup"><span data-stu-id="431d1-128">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
