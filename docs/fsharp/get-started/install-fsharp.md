---
title: Installare F#
description: Informazioni su come installare F# in base all'ambiente in uso.
ms.date: 09/05/2019
ms.openlocfilehash: dffa30eac0bdb59c85a66dca6cafd62b25daa572
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855794"
---
# <a name="install-f"></a><span data-ttu-id="31f54-103">Installare F\#</span><span class="sxs-lookup"><span data-stu-id="31f54-103">Install F\#</span></span>

<span data-ttu-id="31f54-104">È possibile installare F# in diversi modi, a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="31f54-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="31f54-105">Eseguire F# l'installazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31f54-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="31f54-106">Se si sta scaricando [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per la prima volta, verrà prima installato il programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31f54-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="31f54-107">Installare lo SKU di Visual Studio appropriato dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="31f54-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="31f54-108">Se è già installato, fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="31f54-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="31f54-109">Verrà visualizzato un elenco di carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="31f54-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="31f54-110">Selezionare **ASP.NET e sviluppo Web** per installare F# il supporto e il supporto di .NET Core per i progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="31f54-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="31f54-111">Quindi, fare clic su **modifica** nella parte inferiore destra.</span><span class="sxs-lookup"><span data-stu-id="31f54-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="31f54-112">Verrà installato tutto ciò che è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="31f54-112">This will install everything you have selected.</span></span> <span data-ttu-id="31f54-113">È quindi possibile aprire Visual Studio 2017 con F# supporto per la lingua facendo clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="31f54-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="31f54-114">Installare F# con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="31f54-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="31f54-115">F#viene installato per impostazione predefinita in [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), indipendentemente dalla configurazione scelta.</span><span class="sxs-lookup"><span data-stu-id="31f54-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="31f54-116">Al termine dell'installazione, scegliere "avvia Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="31f54-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="31f54-117">È anche possibile avviarlo tramite il Finder in macOS.</span><span class="sxs-lookup"><span data-stu-id="31f54-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="31f54-118">Installare F# con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="31f54-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="31f54-119">Per usare i modelli di progetto, è necessario che [git sia installato](https://git-scm.com/download) e disponibile nel percorso.</span><span class="sxs-lookup"><span data-stu-id="31f54-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="31f54-120">È possibile verificare che sia installato correttamente digitando `git --version` al prompt dei comandi e premendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="31f54-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="31f54-121">macOS</span><span class="sxs-lookup"><span data-stu-id="31f54-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="31f54-122">[Mono](https://www.mono-project.com) viene usato per [ F# ](../tutorials/fsharp-interactive/index.md) il supporto interattivo.</span><span class="sxs-lookup"><span data-stu-id="31f54-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="31f54-123">Il modo più semplice per installare Mono in macOS è tramite Homebrew.</span><span class="sxs-lookup"><span data-stu-id="31f54-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="31f54-124">È sufficiente digitare quanto segue nel terminale:</span><span class="sxs-lookup"><span data-stu-id="31f54-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="31f54-125">Installare anche il [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="31f54-125">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="31f54-126">Linux</span><span class="sxs-lookup"><span data-stu-id="31f54-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="31f54-127">[Mono](https://www.mono-project.com) viene usato per [ F# ](../tutorials/fsharp-interactive/index.md) il supporto interattivo.</span><span class="sxs-lookup"><span data-stu-id="31f54-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="31f54-128">Se si è in Debian o Ubuntu, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="31f54-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="31f54-129">Installare anche il [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="31f54-129">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="31f54-130">Windows</span><span class="sxs-lookup"><span data-stu-id="31f54-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="31f54-131">Installare [Visual Studio con F# supporto](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="31f54-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="31f54-132">In questo modo vengono installati tutti i componenti necessari per scrivere, compilare F# ed eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="31f54-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="31f54-133">Installare anche il [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="31f54-133">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

---

<span data-ttu-id="31f54-134">Sarà quindi necessario [Visual Studio Code](https://code.visualstudio.com) installato.</span><span class="sxs-lookup"><span data-stu-id="31f54-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="31f54-135">Fare quindi clic sull'icona delle estensioni e cercare "Ionide":</span><span class="sxs-lookup"><span data-stu-id="31f54-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="31f54-136">Il solo plug-in F# necessario per il supporto nel Visual Studio Code è [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="31f54-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="31f54-137">Tuttavia, è anche possibile installare [Ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere supporto [Fake](https://fsharp.github.io/FAKE/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) per ottenere il supporto di [Paket](https://fsprojects.github.io/Paket/) .</span><span class="sxs-lookup"><span data-stu-id="31f54-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="31f54-138">FAKE e pake sono strumenti aggiuntivi F# della community per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="31f54-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="31f54-139">Installare F# in un server di compilazione</span><span class="sxs-lookup"><span data-stu-id="31f54-139">Install F# on a Build Server</span></span>

<span data-ttu-id="31f54-140">Se si usa .NET Core o .NET Framework tramite .NET SDK, è sufficiente installare .NET SDK nel server di compilazione.</span><span class="sxs-lookup"><span data-stu-id="31f54-140">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="31f54-141">Sono disponibili tutti gli elementi necessari.</span><span class="sxs-lookup"><span data-stu-id="31f54-141">It has everything you need.</span></span>

<span data-ttu-id="31f54-142">Se si usa .NET Framework e **non** si usa .NET SDK, sarà necessario installare lo [SKU di Visual Studio Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="31f54-142">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="31f54-143">Nel programma di installazione selezionare **strumenti di compilazione desktop .NET** , quindi selezionare **F#** il componente del compilatore sul lato destro del menu programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="31f54-143">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
