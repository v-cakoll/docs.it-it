---
title: Introduzione a codice c# e Visual Studio - Guida per c#
description: Informazioni su come creare la prima applicazione .NET Core in C# ed eseguirne il debug tramite Visual Studio Code.
keywords: C#, introduzione, acquisizione, installazione, Visual Studio Code, multipiattaforma
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.openlocfilehash: 3a9de689946507e4b6d89f684461d65049b3375a
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="cbddf-104">Introduzione a C# e Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cbddf-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="cbddf-105">.NET Core offre una piattaforma veloce e modulare per la creazione di applicazioni eseguibili in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="cbddf-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="cbddf-106">Usare Visual Studio Code con l'estensione C# per ottenere un'efficace esperienza di programmazione con il supporto completo per IntelliSense C# (completamento intelligente del codice) e debug.</span><span class="sxs-lookup"><span data-stu-id="cbddf-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cbddf-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cbddf-107">Prerequisites</span></span>

1. <span data-ttu-id="cbddf-108">Installare [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="cbddf-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="cbddf-109">Installare [.NET Core SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="cbddf-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="cbddf-110">Installare l'[estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) da Visual Studio Code Marketplace.</span><span class="sxs-lookup"><span data-stu-id="cbddf-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="cbddf-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="cbddf-111">Hello World</span></span>

<span data-ttu-id="cbddf-112">Si inizia con un semplice programma "Hello World" in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="cbddf-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="cbddf-113">Aprire un progetto:</span><span class="sxs-lookup"><span data-stu-id="cbddf-113">Open a project:</span></span>

    * <span data-ttu-id="cbddf-114">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="cbddf-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="cbddf-115">Fare clic sull'icona Esplora nel menu a sinistra e quindi fare clic su **Apri cartella**.</span><span class="sxs-lookup"><span data-stu-id="cbddf-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="cbddf-116">Selezionare **File** > **Apri cartella** dal menu principale per aprire la cartella si desidera il progetto c# e fare clic su **selezionare la cartella**.</span><span class="sxs-lookup"><span data-stu-id="cbddf-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="cbddf-117">Per questo esempio, si sta creando una cartella per il progetto denominato *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="cbddf-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="cbddf-119">Inizializzare un progetto C#:</span><span class="sxs-lookup"><span data-stu-id="cbddf-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="cbddf-120">Aprire il terminale integrato dal codice di Visual Studio selezionando **vista** > **Terminal integrata** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="cbddf-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="cbddf-121">Nella finestra del terminale digitare `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="cbddf-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="cbddf-122">Questo comando crea un `Program.cs` file nella cartella con un programma semplice "Hello World" già scritto, insieme a un file di progetto c# denominato `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="cbddf-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![Comando new di dotnet](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="cbddf-124">Risolvere le risorse di compilazione:</span><span class="sxs-lookup"><span data-stu-id="cbddf-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="cbddf-125">Per **.NET Core 1. x**, tipo `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="cbddf-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="cbddf-126">L'esecuzione di `dotnet restore` consente di accedere ai pacchetti .NET Core necessari per la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cbddf-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![Comando restore di dotnet](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="cbddf-128">Eseguire il programma "Hello World":</span><span class="sxs-lookup"><span data-stu-id="cbddf-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="cbddf-129">Digitare `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="cbddf-129">Type `dotnet run`.</span></span> 

      ![Comando run di dotnet](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="cbddf-131">Per altre informazioni sull'installazione in [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu), è anche possibile guardare una breve esercitazione video.</span><span class="sxs-lookup"><span data-stu-id="cbddf-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="cbddf-132">Debug</span><span class="sxs-lookup"><span data-stu-id="cbddf-132">Debug</span></span>

1. <span data-ttu-id="cbddf-133">Aprire il file *Program.cs* facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="cbddf-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="cbddf-134">La prima volta che si apre un file c# in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) carica nell'editor.</span><span class="sxs-lookup"><span data-stu-id="cbddf-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![Aprire il file Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="cbddf-136">Codice di Visual Studio segnala la necessità di aggiungere le risorse mancante per compilare ed eseguire il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="cbddf-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="cbddf-137">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="cbddf-137">Select **Yes**.</span></span> 

    ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="cbddf-139">Per aprire la visualizzazione Debug, fare clic sull'icona Debug nel menu di sinistra.</span><span class="sxs-lookup"><span data-stu-id="cbddf-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Aprire la scheda Debug](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="cbddf-141">Individuare la freccia verde nella parte superiore del riquadro.</span><span class="sxs-lookup"><span data-stu-id="cbddf-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="cbddf-142">Verificare che nel menu a discesa accanto alla freccia sia selezionato `.NET Core Launch (console)`.</span><span class="sxs-lookup"><span data-stu-id="cbddf-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![Selezione di .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="cbddf-144">Aggiungere al progetto facendo clic su un punto di interruzione il **editor margine**, ovvero lo spazio a sinistra dei numeri di riga nell'editor, accanto a riga 9.</span><span class="sxs-lookup"><span data-stu-id="cbddf-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9.</span></span>

    ![Impostazione di un punto di interruzione](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="cbddf-146">Per avviare il debug, selezionare <kbd>F5</kbd> o la freccia verde.</span><span class="sxs-lookup"><span data-stu-id="cbddf-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="cbddf-147">Il debugger interrompe l'esecuzione del programma quando raggiunge il punto di interruzione impostato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="cbddf-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="cbddf-148">Durante il debug, è possibile visualizzare le variabili locali nel riquadro superiore sinistro o utilizzare la console di debug.</span><span class="sxs-lookup"><span data-stu-id="cbddf-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![Run e Debug](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="cbddf-150">Selezionare la freccia verde in alto per continuare il debug oppure fare clic sul quadrato rosso per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="cbddf-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="cbddf-151">Per altre informazioni e per suggerimenti sul debug .NET Core con OmniSharp in Visual Studio Code, vedere [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Istruzioni per l'impostazione del debugger .NET Core).</span><span class="sxs-lookup"><span data-stu-id="cbddf-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cbddf-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbddf-152">See also</span></span>
<span data-ttu-id="cbddf-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)  (Impostazione di Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="cbddf-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
<span data-ttu-id="cbddf-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="cbddf-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
