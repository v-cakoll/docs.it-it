---
title: Introduzione a C# e Visual Studio Code - Guida a C# | Microsoft Docs
description: Informazioni su come creare la prima applicazione .NET Core in C# ed eseguirne il debug tramite Visual Studio Code.
keywords: C#, introduzione, acquisizione, installazione, Visual Studio Code, multipiattaforma
author: kendrahavens
ms.author: mairaw
ms.date: 8/01/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.translationtype: HT
ms.sourcegitcommit: 3bd8800e7410ae4a3b89f5962af957789edd48b0
ms.openlocfilehash: a10fda5663f0a49069388ee8ee7a9ebb575cd549
ms.contentlocale: it-it
ms.lasthandoff: 08/03/2017

---

# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="3a9c8-104">Introduzione a C# e Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3a9c8-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="3a9c8-105">.NET Core offre una piattaforma veloce e modulare per la creazione di applicazioni eseguibili in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="3a9c8-106">Usare Visual Studio Code con l'estensione C# per ottenere un'efficace esperienza di programmazione con il supporto completo per IntelliSense C# (completamento intelligente del codice) e debug.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a9c8-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3a9c8-107">Prerequisites</span></span>

1. <span data-ttu-id="3a9c8-108">Installare [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="3a9c8-109">Installare [.NET Core SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="3a9c8-110">Installare l'[estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) da Visual Studio Code Marketplace.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="3a9c8-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="3a9c8-111">Hello World</span></span>

<span data-ttu-id="3a9c8-112">Si inizia con un semplice programma "Hello World" in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="3a9c8-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="3a9c8-113">Aprire un progetto:</span><span class="sxs-lookup"><span data-stu-id="3a9c8-113">Open a project:</span></span>

    * <span data-ttu-id="3a9c8-114">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="3a9c8-115">Fare clic sull'icona Esplora nel menu a sinistra e quindi fare clic su **Apri cartella**.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="3a9c8-116">Selezionare la cartella in cui inserire il programma C# e fare clic su **Seleziona cartella**.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-116">Select the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="3a9c8-117">Ai fini di questo esempio, verrà creata una cartella per il progetto denominato 'HelloWorld'.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-117">For our example, we'll create a folder for our project named 'HelloWorld'.</span></span> 

  ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

    * <span data-ttu-id="3a9c8-119">In alternativa, è possibile scegliere **File** > **Apri cartella** dal menu principale per aprire la cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-119">Alternatively, you can select **File** > **Open Folder** from the main menu to open your project folder.</span></span>

2. <span data-ttu-id="3a9c8-120">Inizializzare un progetto C#:</span><span class="sxs-lookup"><span data-stu-id="3a9c8-120">Initialize a C# project:</span></span>
    * <span data-ttu-id="3a9c8-121">Aprire il terminale integrato da Visual Studio Code digitando <kbd>CTRL</kbd>+<kbd>\\`</kbd> (apice inverso).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-121">Open the Integrated Terminal from Visual Studio Code by typing <kbd>CTRL</kbd>+<kbd>\\`</kbd> (backtick).</span></span> <span data-ttu-id="3a9c8-122">In alternativa, è possibile selezionare **Visualizza** > **Terminal integrato** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-122">Alternatively, you can select **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="3a9c8-123">Nella finestra del terminale digitare `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-123">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="3a9c8-124">Questa operazione crea un file `Program.cs` nella cartella con un semplice programma "Hello World" già scritto, oltre a un file di progetto C# denominato `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-124">This creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

  ![Comando new di dotnet](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="3a9c8-126">Risolvere le risorse di compilazione:</span><span class="sxs-lookup"><span data-stu-id="3a9c8-126">Resolve the build assets:</span></span>

    * <span data-ttu-id="3a9c8-127">Per **.NET Core 1.1** digitare `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-127">For **.NET Core 1.1**, type `dotnet restore`.</span></span> <span data-ttu-id="3a9c8-128">L'esecuzione di `dotnet restore` consente di accedere ai pacchetti .NET Core necessari per la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-128">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

   ![Comando restore di dotnet](media/with-visual-studio-code/dotnetrestore.png)

    * <span data-ttu-id="3a9c8-130">Questo passaggio è facoltativo per **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-130">For **.NET Core 2.0**, this step is optional.</span></span> <span data-ttu-id="3a9c8-131">Il comando `dotnet restore` viene eseguito automaticamente quando viene creato un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-131">The `dotnet restore` command executes automatically when a new project is created.</span></span>

4. <span data-ttu-id="3a9c8-132">Eseguire il programma "Hello World":</span><span class="sxs-lookup"><span data-stu-id="3a9c8-132">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="3a9c8-133">Digitare `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-133">Type `dotnet run`.</span></span> 

  ![Comando run di dotnet](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="3a9c8-135">Per altre informazioni sull'installazione in [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu), è anche possibile guardare una breve esercitazione video.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-135">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="3a9c8-136">Debug</span><span class="sxs-lookup"><span data-stu-id="3a9c8-136">Debug</span></span>
1. <span data-ttu-id="3a9c8-137">Aprire il file *Program.cs* facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-137">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="3a9c8-138">La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) viene caricato nell'editor.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-138">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) will load in the editor.</span></span>

  ![Aprire il file Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="3a9c8-140">Visual Studio Code chiederà di aggiungere le risorse mancanti per compilare l'applicazione ed eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-140">Visual Studio Code will prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="3a9c8-141">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-141">Select **Yes**.</span></span> 

  ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="3a9c8-143">Per aprire la visualizzazione Debug, fare clic sull'icona Debug nel menu di sinistra.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-143">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

  ![Aprire la scheda Debug](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="3a9c8-145">Individuare la freccia verde nella parte superiore del riquadro.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-145">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="3a9c8-146">Verificare che nel menu a discesa accanto alla freccia sia selezionato `.NET Core Launch (console)`.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-146">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

  ![Selezione di .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="3a9c8-148">Aggiungere un punto di interruzione al progetto facendo clic sul **margine dell'editor** (lo spazio a sinistra dei numeri riga nell'editor) accanto alla riga 9.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-148">Add a breakpoint to your project by clicking on the **editor margin** (the space on the left of the line numbers in the editor) next to line 9.</span></span>

  ![Impostazione di un punto di interruzione](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="3a9c8-150">Premere <kbd>F5</kbd> o fare clic sulla freccia verde per avviare il debug.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-150">Select <kbd>F5</kbd> or the green arrow to start debugging.</span></span> <span data-ttu-id="3a9c8-151">Il debugger interrompe l'esecuzione del programma quando raggiunge il punto di interruzione impostato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-151">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="3a9c8-152">Durante il debug è possibile visualizzare le variabili locali nel riquadro superiore sinistro. In alternativa, usare la console di debug.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-152">While debugging you can view your local variables in the top left pane or use the debug console.</span></span>

  ![Run e Debug](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="3a9c8-154">Selezionare la freccia verde in alto per continuare il debug oppure fare clic sul quadrato rosso per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-154">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="3a9c8-155">Per altre informazioni e per suggerimenti sul debug .NET Core con OmniSharp in Visual Studio Code, vedere [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Istruzioni per l'impostazione del debugger .NET Core).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-155">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a9c8-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a9c8-156">See also</span></span>
<span data-ttu-id="3a9c8-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)  (Impostazione di Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="3a9c8-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
<span data-ttu-id="3a9c8-158">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="3a9c8-158">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>

