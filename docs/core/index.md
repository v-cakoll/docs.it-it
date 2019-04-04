---
title: Guida a .NET Core
description: .NET core è un'implementazione modulare ad alte prestazioni di .NET per la creazione di app di Windows, Mac e Linux. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 79a0c09074159160dd01b0c7970612f7058cc3fc
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920623"
---
# <a name="net-core-guide"></a><span data-ttu-id="26368-104">Guida a .NET Core</span><span class="sxs-lookup"><span data-stu-id="26368-104">.NET Core Guide</span></span>

<span data-ttu-id="26368-105">[.NET Core](about.md) è una piattaforma di sviluppo [open source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) per utilizzo generico gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="26368-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="26368-106">È multipiattaforma, supporta Windows, macOS e Linux e può essere usata per creare applicazioni per dispositivi, cloud e IoT.</span><span class="sxs-lookup"><span data-stu-id="26368-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="26368-107">Vedere [Informazioni su .NET Core](about.md) per altre informazioni su .NET Core, inclusi le caratteristiche, i linguaggi e i framework supportati e le principali API.</span><span class="sxs-lookup"><span data-stu-id="26368-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="26368-108">Per imparare a creare una semplice applicazione .NET Core, vedere le [Esercitazioni di .NET Core](tutorials/index.md).</span><span class="sxs-lookup"><span data-stu-id="26368-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="26368-109">Sono necessari pochi minuti per realizzare ed eseguire la prima app.</span><span class="sxs-lookup"><span data-stu-id="26368-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="26368-110">Se si vuole provare .NET Core nel browser, vedere l'esercitazione online [Numeri in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).</span><span class="sxs-lookup"><span data-stu-id="26368-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core-22"></a><span data-ttu-id="26368-111">Scaricare .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="26368-111">Download .NET Core 2.2</span></span>

<span data-ttu-id="26368-112">Scaricare [.NET Core 2.2 SDK](https://www.microsoft.com/net/download) per provare .NET Core nel computer Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="26368-112">Download the [.NET Core  2.2 SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="26368-113">Visitare [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) se si preferisce usare i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="26368-113">Visit [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) if you prefer to use Docker containers.</span></span>

<span data-ttu-id="26368-114">Tutte le versioni di .NET Core sono disponibili nella pagina [Download di .NET Core](https://www.microsoft.com/net/download/archives) se si sta cercando un'altra versione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="26368-114">All .NET Core versions are available at [.NET Core Downloads](https://www.microsoft.com/net/download/archives) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-22"></a><span data-ttu-id="26368-115">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="26368-115">.NET Core 2.2</span></span>

<span data-ttu-id="26368-116">La versione più recente è [.NET Core 2.2](whats-new/dotnet-core-2-2.md).</span><span class="sxs-lookup"><span data-stu-id="26368-116">The latest version is [.NET Core 2.2](whats-new/dotnet-core-2-2.md).</span></span> <span data-ttu-id="26368-117">Le nuove funzionalità includono: distribuzioni dipendenti dal framework, hook di avvio, autenticazione AAD con SQL di Azure e il supporto per Windows ARM32.</span><span class="sxs-lookup"><span data-stu-id="26368-117">New features include: framework-dependent deployments, startup hooks, AAD authentication with Azure SQL, and support for Windows ARM32.</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="26368-118">Creare la prima applicazione</span><span class="sxs-lookup"><span data-stu-id="26368-118">Create your first application</span></span>

<span data-ttu-id="26368-119">Dopo aver installato .NET Core SDK, aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="26368-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="26368-120">Digitare i seguenti comandi `dotnet` per creare ed eseguire un'applicazione C#.</span><span class="sxs-lookup"><span data-stu-id="26368-120">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="26368-121">È necessario visualizzare il seguente output:</span><span class="sxs-lookup"><span data-stu-id="26368-121">You should see the following output:</span></span>

```console
Hello World!
```

## <a name="support"></a><span data-ttu-id="26368-122">Supporto</span><span class="sxs-lookup"><span data-stu-id="26368-122">Support</span></span>

<span data-ttu-id="26368-123">.NET Core è [supportato da Microsoft](https://www.microsoft.com/net/support/policy) in Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="26368-123">.NET Core is [supported by Microsoft](https://www.microsoft.com/net/support/policy), on Windows, macOS and Linux.</span></span> <span data-ttu-id="26368-124">Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.</span><span class="sxs-lookup"><span data-stu-id="26368-124">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="26368-125">Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26368-125">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="26368-126">[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="26368-126">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="26368-127">Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="26368-127">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="26368-128">Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.</span><span class="sxs-lookup"><span data-stu-id="26368-128">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
