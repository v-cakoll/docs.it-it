---
title: InstallareF#
description: Informazioni su come installare F# nel proprio ambiente.
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331975"
---
# <a name="install-f"></a><span data-ttu-id="5c396-103">Installare F\#</span><span class="sxs-lookup"><span data-stu-id="5c396-103">Install F\#</span></span>

<span data-ttu-id="5c396-104">È possibile installare F# in diversi modi, a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="5c396-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="5c396-105">Installare F# con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5c396-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="5c396-106">Se si sta scaricando [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per la prima volta, verranno installati prima il programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5c396-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="5c396-107">Installare l'appropriato dello SKU di Visual Studio dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="5c396-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="5c396-108">Se già installato, fare clic su **Modify**.</span><span class="sxs-lookup"><span data-stu-id="5c396-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="5c396-109">Successivamente, si verrà visualizzato un elenco dei carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5c396-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="5c396-110">Selezionare **sviluppo ASP.NET e web** che verrà installato F# supporto di supporto e .NET Core per progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5c396-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="5c396-111">Fare quindi clic **Modify** nel lato inferiore destro.</span><span class="sxs-lookup"><span data-stu-id="5c396-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="5c396-112">Verranno installati tutti gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="5c396-112">This will install everything you have selected.</span></span> <span data-ttu-id="5c396-113">È quindi possibile aprire Visual Studio 2017 con F# supporto del linguaggio facendo **avvio veloce**.</span><span class="sxs-lookup"><span data-stu-id="5c396-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="5c396-114">Installare F# con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="5c396-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="5c396-115">F#viene installato per impostazione predefinita in [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), indipendentemente dal quale configurazione scelto.</span><span class="sxs-lookup"><span data-stu-id="5c396-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="5c396-116">Al termine dell'installazione, scegliere "Avvia Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="5c396-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="5c396-117">È anche possibile avviarla tramite Finder in macOS.</span><span class="sxs-lookup"><span data-stu-id="5c396-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="5c396-118">Installare F# con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5c396-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="5c396-119">È necessario disporre [git installato](https://git-scm.com/download) ed è disponibile nel percorso desiderato per rendere utilizzare modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="5c396-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="5c396-120">È possibile verificare che sia installato correttamente, digitando `git --version` in un prompt dei comandi e premendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="5c396-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="5c396-121">macOS</span><span class="sxs-lookup"><span data-stu-id="5c396-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="5c396-122">[Mono](https://www.mono-project.com) serve [ F# Interactive](../tutorials/fsharp-interactive/index.md) supportano.</span><span class="sxs-lookup"><span data-stu-id="5c396-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="5c396-123">Il modo più semplice per installare Mono in macOS è tramite Homebrew.</span><span class="sxs-lookup"><span data-stu-id="5c396-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="5c396-124">È sufficiente digitare quanto segue nel terminale:</span><span class="sxs-lookup"><span data-stu-id="5c396-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="5c396-125">Installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="5c396-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="5c396-126">Linux</span><span class="sxs-lookup"><span data-stu-id="5c396-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="5c396-127">[Mono](https://www.mono-project.com) serve [ F# Interactive](../tutorials/fsharp-interactive/index.md) supportano.</span><span class="sxs-lookup"><span data-stu-id="5c396-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="5c396-128">Se si usa Ubuntu o Debian, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5c396-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="5c396-129">Installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="5c396-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="5c396-130">Windows</span><span class="sxs-lookup"><span data-stu-id="5c396-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="5c396-131">Installare [di Visual Studio con F# supportano](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="5c396-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="5c396-132">Ciò consente di installare tutti i componenti necessari per scrivere, compilare ed eseguire F# codice.</span><span class="sxs-lookup"><span data-stu-id="5c396-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="5c396-133">Installare anche il [.NET Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="5c396-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="5c396-134">Sarà quindi necessario [Visual Studio Code](https://code.visualstudio.com) installato.</span><span class="sxs-lookup"><span data-stu-id="5c396-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="5c396-135">Successivamente, fare clic sull'icona delle estensioni e cercare "Ionide":</span><span class="sxs-lookup"><span data-stu-id="5c396-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="5c396-136">Il plug-in unico necessari per F# è il supporto in Visual Studio Code [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="5c396-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="5c396-137">Tuttavia, è anche possibile installare [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere [FAKE](https://fsharp.github.io/FAKE/) supportano e [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) ottenere [Paket](https://fsprojects.github.io/Paket/) supportano.</span><span class="sxs-lookup"><span data-stu-id="5c396-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="5c396-138">SIMULARE e Paket sono descritti altri F# strumenti della community per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="5c396-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
