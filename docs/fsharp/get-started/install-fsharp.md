---
title: Installare F#
description: Informazioni su come installare F# in diversi modi.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346556"
---
# <a name="install-f"></a><span data-ttu-id="5a67d-103">Installare F\#</span><span class="sxs-lookup"><span data-stu-id="5a67d-103">Install F\#</span></span>

<span data-ttu-id="5a67d-104">È possibile installare F# in diversi modi, a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="5a67d-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="5a67d-105">Eseguire F# l'installazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a67d-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="5a67d-106">Se si sta scaricando [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) per la prima volta, verrà prima di tutto installato programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5a67d-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="5a67d-107">Installare la versione appropriata di Visual Studio dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="5a67d-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="5a67d-108">Se Visual Studio è già installato, scegliere **modifica** accanto all'edizione a cui si desidera aggiungere F# .</span><span class="sxs-lookup"><span data-stu-id="5a67d-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="5a67d-109">Nella pagina carichi di lavoro selezionare il carico di lavoro **sviluppo Web e ASP.NET** , che F# include il supporto per .NET Core e per i progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5a67d-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="5a67d-110">Scegliere **modifica** nell'angolo in basso a destra per installare tutti gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="5a67d-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="5a67d-111">È quindi possibile aprire Visual Studio con F# scegliendo **Avvia** in programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5a67d-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="5a67d-112">Installare F# con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5a67d-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="5a67d-113">Assicurarsi che [git](https://git-scm.com/download) sia installato e disponibile nel percorso.</span><span class="sxs-lookup"><span data-stu-id="5a67d-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="5a67d-114">È possibile verificare che sia installato correttamente immettendo `git --version` al prompt dei comandi e premendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="5a67d-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="5a67d-115">Installare il [.NET Core SDK](https://dotnet.microsoft.com/download) e [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="5a67d-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="5a67d-116">Selezionare l'icona delle estensioni e cercare "Ionide":</span><span class="sxs-lookup"><span data-stu-id="5a67d-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="5a67d-117">Il solo plug-in F# necessario per il supporto nel Visual Studio Code è [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="5a67d-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="5a67d-118">Tuttavia, è anche possibile installare [Ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere supporto [Fake](https://fake.build/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) per ottenere il supporto di [Paket](https://fsprojects.github.io/Paket/) .</span><span class="sxs-lookup"><span data-stu-id="5a67d-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="5a67d-119">FAKE e pake sono strumenti aggiuntivi F# della community per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="5a67d-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="5a67d-120">Installare F# con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="5a67d-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="5a67d-121">F#viene installato per impostazione predefinita in [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), indipendentemente dalla configurazione scelta.</span><span class="sxs-lookup"><span data-stu-id="5a67d-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="5a67d-122">Al termine dell'installazione, scegliere **Avvia Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="5a67d-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="5a67d-123">È anche possibile aprire Visual Studio tramite il Finder in macOS.</span><span class="sxs-lookup"><span data-stu-id="5a67d-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="5a67d-124">Installare F# in un server di compilazione</span><span class="sxs-lookup"><span data-stu-id="5a67d-124">Install F# on a build server</span></span>

<span data-ttu-id="5a67d-125">Se si usa .NET Core o .NET Framework tramite .NET SDK, è sufficiente installare .NET SDK nel server di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5a67d-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="5a67d-126">Sono disponibili tutti gli elementi necessari.</span><span class="sxs-lookup"><span data-stu-id="5a67d-126">It has everything you need.</span></span>

<span data-ttu-id="5a67d-127">Se si usa .NET Framework e **non** si usa .NET SDK, è necessario installare lo [SKU Visual Studio Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) nel server Windows.</span><span class="sxs-lookup"><span data-stu-id="5a67d-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="5a67d-128">Nel programma di installazione selezionare **strumenti di compilazione desktop .NET**, quindi selezionare il **F#** componente del compilatore sul lato destro del menu programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="5a67d-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
