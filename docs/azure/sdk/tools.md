---
title: Azure per sviluppatori .NET e .NET Core di Azure
description: Ottenere gli strumenti per iniziare a usare le librerie .NET di Azure da un ambiente Windows, Linux e Mac.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "82071941"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="9d21d-103">Azure per sviluppatori .NET e .NET Core di Azure</span><span class="sxs-lookup"><span data-stu-id="9d21d-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="9d21d-104">Download dell'SDK</span><span class="sxs-lookup"><span data-stu-id="9d21d-104">SDK downloads</span></span>

<span data-ttu-id="9d21d-105">Le librerie di Azure per .NET sono implementate come [pacchetti NuGet](https://www.nuget.org/packages?q=windowsazureofficial).</span><span class="sxs-lookup"><span data-stu-id="9d21d-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="9d21d-106">Vedere le informazioni di [riferimento sulle API](/dotnet/api/overview/azure/?view=azure-dotnet) per le istruzioni di installazione organizzate dal servizio di Azure.</span><span class="sxs-lookup"><span data-stu-id="9d21d-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="9d21d-107">Strumenti di sviluppo</span><span class="sxs-lookup"><span data-stu-id="9d21d-107">Development tools</span></span>

<span data-ttu-id="9d21d-108">Visual Studio include strumenti per molti servizi di Azure predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9d21d-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="9d21d-109">Per alcuni servizi di Azure sono disponibili strumenti o emulatori aggiuntivi, ad esempio [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="9d21d-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="9d21d-110">Se necessario, vedere la documentazione relativa al servizio di Azure per eventuali altri strumenti.</span><span class="sxs-lookup"><span data-stu-id="9d21d-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="9d21d-111">Queste istruzioni installano l'ambiente di sviluppo consigliato per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="9d21d-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="9d21d-112">Windows</span><span class="sxs-lookup"><span data-stu-id="9d21d-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="9d21d-113">Visual Studio versione 2017 e successive includono il supporto integrato per lo sviluppo in Azure.</span><span class="sxs-lookup"><span data-stu-id="9d21d-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="9d21d-114">I passaggi seguenti descrivono l'abilitazione del supporto per lo sviluppo di Azure in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9d21d-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="9d21d-115">Per Visual Studio 2015 e versioni precedenti, <a href="vs2015-install.md">seguire queste istruzioni</a>.</span><span class="sxs-lookup"><span data-stu-id="9d21d-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="9d21d-116">Passaggio 1: scaricare Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9d21d-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="9d21d-117">È possibile ignorare questo passaggio se si dispone già di Visual Studio 2019 installato.</span><span class="sxs-lookup"><span data-stu-id="9d21d-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9d21d-118">Scarica Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9d21d-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="9d21d-119">Passaggio 2: Installare i due componenti per Azure</span><span class="sxs-lookup"><span data-stu-id="9d21d-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="9d21d-120">Nel programma di installazione di Visual Studio installare Visual Studio o modificare un'installazione esistente.</span><span class="sxs-lookup"><span data-stu-id="9d21d-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="9d21d-121">Assicurarsi che i carichi di lavoro sviluppo di *Azure* e *ASP.NET e sviluppo Web* siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="9d21d-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="9d21d-122">Passaggio 3: Sviluppare con .NET in Azure</span><span class="sxs-lookup"><span data-stu-id="9d21d-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="9d21d-123">Proseguire con [distribuire la prima app Web ASP.NET Core con servizio app di Azure](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="9d21d-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="9d21d-124">macOS</span><span class="sxs-lookup"><span data-stu-id="9d21d-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="9d21d-125">Visual Studio per Mac include tutti gli elementi necessari per lo sviluppo in Azure.</span><span class="sxs-lookup"><span data-stu-id="9d21d-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="9d21d-126">Passaggio 1: Scaricare Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="9d21d-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9d21d-127">Download di Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="9d21d-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="9d21d-128">Durante l'installazione, gli strumenti di Azure sono selezionati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9d21d-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="9d21d-129">Linux</span><span class="sxs-lookup"><span data-stu-id="9d21d-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="9d21d-130">Visual Studio Code include tutti gli elementi necessari per lo sviluppo di Azure in Linux.</span><span class="sxs-lookup"><span data-stu-id="9d21d-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="9d21d-131">Passaggio 1: Scaricare .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="9d21d-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="9d21d-132">SDK e strumenti da riga di comando per le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d21d-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9d21d-133">Download di .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="9d21d-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="9d21d-134">Passaggio 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9d21d-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="9d21d-135">Modificare ed eseguire il debug di app .NET Core in qualsiasi sistema operativo: Windows, Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="9d21d-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9d21d-136">Download di Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9d21d-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
