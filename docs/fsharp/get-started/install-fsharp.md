---
title: Installare F#
description: Scopri come installare F , in vari modi diversi.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400246"
---
# <a name="install-f"></a><span data-ttu-id="d9c49-103">Installazione F\#</span><span class="sxs-lookup"><span data-stu-id="d9c49-103">Install F\#</span></span>

<span data-ttu-id="d9c49-104">È possibile installare F , in diversi modi, a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9c49-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="d9c49-105">Installazione di F , con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d9c49-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="d9c49-106">Se si scarica [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) per la prima volta, verrà innanzitutto installato il programma di installazione di Visual Studio.If you're downloading Visual Studio for the first time, it will first install Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="d9c49-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="d9c49-107">Installare l'edizione appropriata di Visual Studio dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="d9c49-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="d9c49-108">Se Visual Studio è già installato in Visual Studio, scegliere **Modifica** accanto all'edizione a cui si vuole aggiungere F.</span><span class="sxs-lookup"><span data-stu-id="d9c49-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="d9c49-109">Nella pagina Carichi di lavoro selezionare il carico di lavoro **di sviluppo Web e ASP.NET,** che include il supporto di F e .NET Core per i progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d9c49-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="d9c49-110">Scegli **Modifica** nell'angolo in basso a destra per installare tutto ciò che hai selezionato.</span><span class="sxs-lookup"><span data-stu-id="d9c49-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="d9c49-111">È quindi possibile aprire Visual Studio con F, scegliendo Avvia nel programma di installazione di Visual Studio.You can then open Visual Studio with F's by choosing **Launch** in Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="d9c49-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="d9c49-112">Installazione di F , con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d9c49-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="d9c49-113">Assicurati di aver installato [git](https://git-scm.com/download) e disponibile sul tuo PATH.</span><span class="sxs-lookup"><span data-stu-id="d9c49-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="d9c49-114">È possibile verificare che sia `git --version` installato correttamente immettendo al prompt dei comandi e premendo **INVIO**.</span><span class="sxs-lookup"><span data-stu-id="d9c49-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="d9c49-115">Installare [.NET Core SDK](https://dotnet.microsoft.com/download) e [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="d9c49-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="d9c49-116">Selezionare l'icona Estensioni e cercare "Ionide":</span><span class="sxs-lookup"><span data-stu-id="d9c49-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="d9c49-117">L'unico plug-in necessario per il supporto F , nel codice di Visual Studio è [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="d9c49-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="d9c49-118">Tuttavia, puoi anche installare [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere il supporto [FAKE](https://fake.build/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) per ottenere il supporto [Paket.](https://fsprojects.github.io/Paket/)</span><span class="sxs-lookup"><span data-stu-id="d9c49-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="d9c49-119">FAKE e Paket sono strumenti aggiuntivi per la community di F per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="d9c49-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="d9c49-120">Installazione di F , con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="d9c49-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="d9c49-121">Per impostazione predefinita, f è installato in [Visual Studio per Mac,](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)indipendentemente dalla configurazione scelta.</span><span class="sxs-lookup"><span data-stu-id="d9c49-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="d9c49-122">Al termine dell'installazione, scegliere **Avvia Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="d9c49-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="d9c49-123">Puoi anche aprire Visual Studio tramite Finder su macOS.You can also open Visual Studio through Finder on macOS.</span><span class="sxs-lookup"><span data-stu-id="d9c49-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="d9c49-124">Installare F in un server di compilazioneInstall F ' on a build server</span><span class="sxs-lookup"><span data-stu-id="d9c49-124">Install F# on a build server</span></span>

<span data-ttu-id="d9c49-125">Se si usa .NET Core o .NET Framework tramite .NET SDK, è sufficiente installare .NET SDK nel server di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d9c49-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="d9c49-126">Ha tutto ciò di cui hai bisogno.</span><span class="sxs-lookup"><span data-stu-id="d9c49-126">It has everything you need.</span></span>

<span data-ttu-id="d9c49-127">Se si utilizza .NET Framework e **non** si utilizza .NET SDK, sarà necessario installare lo SKU degli strumenti di [compilazione](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) di Visual Studio in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d9c49-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="d9c49-128">Nel programma di installazione selezionare Strumenti di **compilazione desktop .NET**, quindi selezionare il componente **del compilatore F,** sul lato destro del menu del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="d9c49-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
