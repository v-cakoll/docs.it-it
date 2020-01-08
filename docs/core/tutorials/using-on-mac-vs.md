---
title: Introduzione a .NET Core con Visual Studio per Mac
description: In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.
author: mairaw
ms.date: 12/19/2019
ms.custom: seodec18
ms.openlocfilehash: f6faf5519109202a2865b0f316251bd2c85a5606
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342958"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="ecd9f-103">Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="ecd9f-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="ecd9f-104">Visual Studio per Mac offre un ambiente di sviluppo integrato completo per lo sviluppo di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="ecd9f-105">Questo articolo illustra la creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-105">This article walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="ecd9f-106">Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-106">Your feedback is highly valued.</span></span> <span data-ttu-id="ecd9f-107">Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="ecd9f-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="ecd9f-108">In Visual Studio per Mac scegliere **Aiuto** > **Segnala un problema** dal menu o **Segnala un problema** dalla schermata iniziale per visualizzare una finestra per l'archiviazione di un report sul bug.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="ecd9f-109">È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="ecd9f-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="ecd9f-110">Per inviare un suggerimento, scegliere **Aiuto** > **Invia un suggerimento** dal menu o **Invia un suggerimento** dalla schermata iniziale per aprire la [pagina Web Developer Community di Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="ecd9f-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ecd9f-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ecd9f-111">Prerequisites</span></span>

<span data-ttu-id="ecd9f-112">Vedere l'articolo [dipendenze e requisiti di .NET Core](../install/dependencies.md?pivots=os-macos) .</span><span class="sxs-lookup"><span data-stu-id="ecd9f-112">See the [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-macos) article.</span></span>

<span data-ttu-id="ecd9f-113">Per assicurarsi di usare una versione supportata di .NET Core, vedere l'articolo del [supporto tecnico di .NET Core](/visualstudio/mac/net-core-support) .</span><span class="sxs-lookup"><span data-stu-id="ecd9f-113">Check the [.NET Core Support](/visualstudio/mac/net-core-support) article to ensure you're using a supported version of .NET Core.</span></span>

## <a name="get-started"></a><span data-ttu-id="ecd9f-114">Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="ecd9f-114">Get started</span></span>

<span data-ttu-id="ecd9f-115">Se i prerequisiti e Visual Studio per Mac sono già installati, ignorare questa sezione e passare a [Creazione di un progetto](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="ecd9f-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="ecd9f-116">Seguire questa procedura per installare i prerequisiti e Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="ecd9f-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="ecd9f-117">Scaricare il [programma di installazione di Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="ecd9f-117">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="ecd9f-118">Eseguire il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-118">Run the installer.</span></span> <span data-ttu-id="ecd9f-119">Leggere e accettare il contratto di licenza.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-119">Read and accept the license agreement.</span></span> <span data-ttu-id="ecd9f-120">Durante l'installazione selezionare l'opzione per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-120">During the install, select the option to install .NET Core.</span></span> <span data-ttu-id="ecd9f-121">Viene offerta la possibilità di installare Xamarin, una tecnologia per lo sviluppo di app per dispositivi mobili multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-121">You're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="ecd9f-122">L'installazione di Xamarin e dei relativi componenti è facoltativa per lo sviluppo di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-122">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="ecd9f-123">Per una descrizione dettagliata del processo di installazione di Visual Studio per Mac, vedere la [documentazione di Visual Studio per Mac](/visualstudio/mac/).</span><span class="sxs-lookup"><span data-stu-id="ecd9f-123">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="ecd9f-124">Al termine dell'installazione, avviare l'IDE di Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-124">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="ecd9f-125">Creazione di un progetto</span><span class="sxs-lookup"><span data-stu-id="ecd9f-125">Creating a project</span></span>

1. <span data-ttu-id="ecd9f-126">Selezionare **nuovo** nella finestra di avvio.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-126">Select **New** on the start window.</span></span>

   ![Pulsante Nuovo nella schermata iniziale di Visual Studio per Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="ecd9f-128">Nella finestra di dialogo **Nuovo progetto** selezionare **App** sotto il nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-128">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="ecd9f-129">Selezionare il modello **Applicazione console** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-129">Select the **Console Application** template followed by **Next**.</span></span>

   ![Nuovo elenco di modelli di progetto](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="ecd9f-131">Se è installata più di una versione di .NET Core, selezionare il framework di destinazione per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-131">If you have more than one version of .NET Core installed, select the target framework for your project.</span></span>

1. <span data-ttu-id="ecd9f-132">Digitare "HelloWorld" nel campo **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-132">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="ecd9f-133">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-133">Select **Create**.</span></span>

   ![Finestra di dialogo di configurazione della nuova applicazione console](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="ecd9f-135">Attendere che vengano ripristinate le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-135">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="ecd9f-136">Il progetto è costituito da un unico file C#, *Program.cs*, contenente una classe `Program` con un metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-136">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="ecd9f-137">L'istruzione `Console.WriteLine` consentirà la visualizzazione di "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="ecd9f-137">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="ecd9f-138">nella console all'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-138">to the console when the app is run.</span></span>

   ![Finestra principale con il file Program.cs aperto](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="ecd9f-140">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ecd9f-140">Run the application</span></span>

<span data-ttu-id="ecd9f-141">Eseguire l'app in modalità debug usando ⌘ ↵ (Comando + Invio) o in modalità versione usando ⌥ ⌘ ↵ (Opzione + Comando + Invio).</span><span class="sxs-lookup"><span data-stu-id="ecd9f-141">Run the app in Debug mode using ⌘ ↵ (command + enter) or in Release mode using ⌥ ⌘ ↵ (option + command + enter).</span></span>

![Nel riquadro di output dell'applicazione viene visualizzato Hello World!](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="ecd9f-143">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ecd9f-143">Next step</span></span>

<span data-ttu-id="ecd9f-144">L'argomento [Creazione di una soluzione .NET Core completa in macOS con Visual Studio per Mac](using-on-mac-vs-full-solution.md) illustra come creare una soluzione .NET Core completa contenente librerie riutilizzabili e unit test.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-144">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
