---
title: Guida a .NET Core
description: .NET core è un'implementazione modulare ad alte prestazioni di .NET per la creazione di app di Windows, Mac e Linux. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837012"
---
# <a name="net-core-guide"></a><span data-ttu-id="d98e8-104">Guida a .NET Core</span><span class="sxs-lookup"><span data-stu-id="d98e8-104">.NET Core Guide</span></span>

<span data-ttu-id="d98e8-105">[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) per utilizzo generico gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="d98e8-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="d98e8-106">È multipiattaforma, supporta Windows, macOS e Linux e può essere usata per creare applicazioni per dispositivi, cloud e IoT.</span><span class="sxs-lookup"><span data-stu-id="d98e8-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="d98e8-107">Vedere [Informazioni su .NET Core](about.md) per altre informazioni su .NET Core, inclusi le caratteristiche, i linguaggi e i framework supportati e le principali API.</span><span class="sxs-lookup"><span data-stu-id="d98e8-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="d98e8-108">Per imparare a creare una semplice applicazione .NET Core, vedere le [Esercitazioni di .NET Core](tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="d98e8-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="d98e8-109">Sono necessari pochi minuti per realizzare ed eseguire la prima app.</span><span class="sxs-lookup"><span data-stu-id="d98e8-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="d98e8-110">Se si vuole provare .NET Core nel browser, vedere l'esercitazione online [Numeri in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).</span><span class="sxs-lookup"><span data-stu-id="d98e8-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="d98e8-111">Download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d98e8-111">Download .NET Core</span></span>

<span data-ttu-id="d98e8-112">Scaricare il [.NET Core SDK](https://www.microsoft.com/net/download) per provare .NET Core nel computer Windows, MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="d98e8-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="d98e8-113">Se si preferisce usare i contenitori Docker, visitare l' [Hub Docker di .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="d98e8-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="d98e8-114">Tutte le versioni di .NET Core sono disponibili nella pagina [Download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core) se si sta cercando un'altra versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d98e8-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="d98e8-115">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="d98e8-115">.NET Core 3.1</span></span>

<span data-ttu-id="d98e8-116">La versione più recente è .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="d98e8-116">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="d98e8-117">Che include miglioramenti secondari rispetto a .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="d98e8-117">Which includes minor improvements over .NET Core 3.0.</span></span> <span data-ttu-id="d98e8-118">Tuttavia, .NET Core 3,1 è una versione supportata a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="d98e8-118">However, .NET Core 3.1 is a long-term supported release.</span></span> <span data-ttu-id="d98e8-119">Per ulteriori informazioni sulla versione di .NET Core 3,1, vedere Novità [di .net core 3,1](./whats-new/dotnet-core-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="d98e8-119">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="d98e8-120">Creare la prima applicazione</span><span class="sxs-lookup"><span data-stu-id="d98e8-120">Create your first application</span></span>

<span data-ttu-id="d98e8-121">Dopo aver installato .NET Core SDK, aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d98e8-121">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="d98e8-122">Digitare i seguenti comandi di `dotnet` per creare ed eseguire C# un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="d98e8-122">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="d98e8-123">È necessario visualizzare il seguente output:</span><span class="sxs-lookup"><span data-stu-id="d98e8-123">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="d98e8-124">Supporto</span><span class="sxs-lookup"><span data-stu-id="d98e8-124">Support</span></span>

<span data-ttu-id="d98e8-125">.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy), in Windows, MacOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="d98e8-125">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="d98e8-126">Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.</span><span class="sxs-lookup"><span data-stu-id="d98e8-126">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="d98e8-127">Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d98e8-127">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="d98e8-128">[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="d98e8-128">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="d98e8-129">Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="d98e8-129">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="d98e8-130">Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.</span><span class="sxs-lookup"><span data-stu-id="d98e8-130">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
