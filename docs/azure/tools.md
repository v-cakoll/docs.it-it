---
title: Strumenti per gli sviluppatori .NET in Azure
description: Ottenere gli strumenti per iniziare a usare le librerie .NET di Azure da un ambiente Windows, Linux e Mac.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174926"
---
# <a name="azure-tools-for-developing-with-net"></a><span data-ttu-id="958da-103">Strumenti di Azure per lo sviluppo con .NET</span><span class="sxs-lookup"><span data-stu-id="958da-103">Azure tools for developing with .NET</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="958da-104">Download dell'SDK</span><span class="sxs-lookup"><span data-stu-id="958da-104">SDK downloads</span></span>

<span data-ttu-id="958da-105">Le librerie di Azure per .NET sono implementate come [pacchetti NuGet](https://www.nuget.org/packages?q=windowsazureofficial).</span><span class="sxs-lookup"><span data-stu-id="958da-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="958da-106">Vedere le informazioni di [riferimento sulle API](/dotnet/api/overview/azure/?view=azure-dotnet) per la documentazione di riferimento organizzata dal servizio di Azure.</span><span class="sxs-lookup"><span data-stu-id="958da-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for reference documentation organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="958da-107">Strumenti di sviluppo</span><span class="sxs-lookup"><span data-stu-id="958da-107">Development tools</span></span>

<span data-ttu-id="958da-108">Visual Studio include strumenti per molti servizi di Azure predefiniti.</span><span class="sxs-lookup"><span data-stu-id="958da-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="958da-109">Per alcuni servizi di Azure sono disponibili strumenti o emulatori aggiuntivi, ad esempio [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span><span class="sxs-lookup"><span data-stu-id="958da-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="958da-110">Se necessario, vedere la documentazione relativa al servizio di Azure per eventuali altri strumenti.</span><span class="sxs-lookup"><span data-stu-id="958da-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="958da-111">Selezionare l'ambiente di sviluppo preferito.</span><span class="sxs-lookup"><span data-stu-id="958da-111">Select your preferred development environment below.</span></span>

## <a name="visual-studio-on-windows"></a>[<span data-ttu-id="958da-112">Visual Studio su Windows</span><span class="sxs-lookup"><span data-stu-id="958da-112">Visual Studio on Windows</span></span>](#tab/vs)

<span data-ttu-id="958da-113">Visual Studio versione 2017 e successive includono il supporto integrato per lo sviluppo in Azure.</span><span class="sxs-lookup"><span data-stu-id="958da-113">Visual Studio version 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="958da-114">I passaggi seguenti descrivono l'abilitazione del supporto per lo sviluppo di Azure in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="958da-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="958da-115">Per Visual Studio 2015 e versioni precedenti, <a href="vs2015-install.md">seguire queste istruzioni</a>.</span><span class="sxs-lookup"><span data-stu-id="958da-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="958da-116">Passaggio 1: scaricare Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="958da-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="958da-117">È possibile ignorare questo passaggio se si dispone già di Visual Studio 2019 installato.</span><span class="sxs-lookup"><span data-stu-id="958da-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="958da-118">Scarica Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="958da-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="958da-119">Passaggio 2: Installare i due componenti per Azure</span><span class="sxs-lookup"><span data-stu-id="958da-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="958da-120">Nel programma di installazione di Visual Studio installare Visual Studio o modificare un'installazione esistente.</span><span class="sxs-lookup"><span data-stu-id="958da-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="958da-121">Assicurarsi che i carichi di lavoro sviluppo di *Azure* e *ASP.NET e sviluppo Web* siano selezionati.</span><span class="sxs-lookup"><span data-stu-id="958da-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="958da-122">Passaggio 3: Sviluppare con .NET in Azure</span><span class="sxs-lookup"><span data-stu-id="958da-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="958da-123">Proseguire con [distribuire la prima app Web ASP.NET Core con servizio app di Azure](/azure/app-service-web/app-service-web-get-started-dotnet).</span><span class="sxs-lookup"><span data-stu-id="958da-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="visual-studio-code-cross-platform"></a>[<span data-ttu-id="958da-124">Visual Studio Code (multipiattaforma)</span><span class="sxs-lookup"><span data-stu-id="958da-124">Visual Studio Code (cross-platform)</span></span>](#tab/vscode)

<span data-ttu-id="958da-125">Visual Studio Code dispone di tutto il necessario per lo sviluppo di Azure multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="958da-125">Visual Studio Code has everything you need for cross-platform Azure development.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="958da-126">Passaggio 1: Scaricare .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="958da-126">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="958da-127">SDK e strumenti da riga di comando per le app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="958da-127">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="958da-128">Download di .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="958da-128">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="958da-129">Passaggio 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="958da-129">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="958da-130">Modificare ed eseguire il debug di app .NET Core in qualsiasi sistema operativo: Windows, Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="958da-130">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="958da-131">Download di Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="958da-131">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a><span data-ttu-id="958da-132">Passaggio 3: estensione degli strumenti di Azure</span><span class="sxs-lookup"><span data-stu-id="958da-132">Step 3: Azure Tools extension</span></span>

<span data-ttu-id="958da-133">Installare l'estensione strumenti di Azure in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="958da-133">Install the Azure Tools extension in Visual Studio Code.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="958da-134">Installare l'estensione degli strumenti di Azure</span><span class="sxs-lookup"><span data-stu-id="958da-134">Install Azure Tools extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a><span data-ttu-id="958da-135">Passaggio 4: sviluppare con .NET in Azure</span><span class="sxs-lookup"><span data-stu-id="958da-135">Step 4: Develop with .NET on Azure</span></span>

<span data-ttu-id="958da-136">Per iniziare, [distribuire la prima app Web di ASP.NET Core nel servizio app Azure in Linux](/azure/app-service/containers/quickstart-dotnetcore).</span><span class="sxs-lookup"><span data-stu-id="958da-136">Get started by [deploying your first ASP.NET Core web app on Azure App Service on Linux](/azure/app-service/containers/quickstart-dotnetcore).</span></span>

---
