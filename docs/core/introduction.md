---
title: Introduzione e panoramica di .NET Core
description: .NET Core è un'implementazione modulare e ad alte prestazioni di .NET per la creazione di app Windows, Linux e macOS. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 03/25/2020
ms.custom: updateeachrelease
ms.openlocfilehash: edd3864d3c3c5c0e9fd8c26ee806ffc9e100423d
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80351701"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="52a6c-104">Introduzione a .NET CoreIntroduction to .NET Core</span><span class="sxs-lookup"><span data-stu-id="52a6c-104">Introduction to .NET Core</span></span>

<span data-ttu-id="52a6c-105">[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) per utilizzo generico gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="52a6c-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="52a6c-106">È multipiattaforma, supporta Windows, macOS e Linux e può essere usata per creare applicazioni per dispositivi, cloud e IoT.</span><span class="sxs-lookup"><span data-stu-id="52a6c-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="52a6c-107">Download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="52a6c-107">Download .NET Core</span></span>

<span data-ttu-id="52a6c-108">Scarica [.NET Core SDK](https://dotnet.microsoft.com/download) per provare .NET Core nel computer Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="52a6c-108">Download the [.NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="52a6c-109">Se si preferisce utilizzare i contenitori Docker, visitare [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="52a6c-109">If you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

## <a name="net-core-31"></a><span data-ttu-id="52a6c-110">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="52a6c-110">.NET Core 3.1</span></span>

<span data-ttu-id="52a6c-111">La versione più recente è .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="52a6c-111">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="52a6c-112">3.1 include miglioramenti minori rispetto a .NET Core 3.0, tuttavia, .NET Core 3.1 è una [versione supportata a lungo termine.](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)</span><span class="sxs-lookup"><span data-stu-id="52a6c-112">3.1 includes minor improvements over .NET Core 3.0, however, .NET Core 3.1 is a [long-term supported release](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span> <span data-ttu-id="52a6c-113">Per ulteriori informazioni sulla versione .NET Core 3.1, vedere [Novità di .NET Core 3.1.](./whats-new/dotnet-core-3-1.md)</span><span class="sxs-lookup"><span data-stu-id="52a6c-113">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

<span data-ttu-id="52a6c-114">Se stai cercando un'altra versione di .NET Core, tutte le versioni sono disponibili in [download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="52a6c-114">If you're looking for another version of .NET Core, all the versions are available at [.NET Core downloads](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="52a6c-115">Creare la prima applicazione</span><span class="sxs-lookup"><span data-stu-id="52a6c-115">Create your first application</span></span>

<span data-ttu-id="52a6c-116">Dopo aver installato .NET Core SDK, aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="52a6c-116">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="52a6c-117">Immettere `dotnet` i comandi seguenti per creare ed eseguire un'applicazione in C:</span><span class="sxs-lookup"><span data-stu-id="52a6c-117">Enter the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="52a6c-118">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="52a6c-118">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="52a6c-119">Supporto</span><span class="sxs-lookup"><span data-stu-id="52a6c-119">Support</span></span>

<span data-ttu-id="52a6c-120">.NET Core è [supportato da Microsoft](https://dotnet.microsoft.com/platform/support/policy) su Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="52a6c-120">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy) on Windows, macOS, and Linux.</span></span> <span data-ttu-id="52a6c-121">Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.</span><span class="sxs-lookup"><span data-stu-id="52a6c-121">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="52a6c-122">Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52a6c-122">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="52a6c-123">[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="52a6c-123">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="52a6c-124">Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="52a6c-124">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="52a6c-125">Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.</span><span class="sxs-lookup"><span data-stu-id="52a6c-125">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52a6c-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="52a6c-126">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="52a6c-127">Esercitazioni di .NET Core</span><span class="sxs-lookup"><span data-stu-id="52a6c-127">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="52a6c-128">Prova .NET Core nel tuo browser</span><span class="sxs-lookup"><span data-stu-id="52a6c-128">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
