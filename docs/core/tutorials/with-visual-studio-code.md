---
title: Introduzione a C# e Visual Studio Code - Guida a C#
description: Informazioni su come creare la prima applicazione .NET Core in C# ed eseguirne il debug tramite Visual Studio Code.
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.workload:
- dotnetcore
ms.openlocfilehash: 0c37040220bb7f38cdd75176bb9ed2a2199b7096
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2018
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="97d9a-103">Introduzione a C# e Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="97d9a-103">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="97d9a-104">.NET Core offre una piattaforma veloce e modulare per la creazione di applicazioni eseguibili in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="97d9a-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="97d9a-105">Usare Visual Studio Code con l'estensione C# per ottenere un'efficace esperienza di programmazione con il supporto completo per IntelliSense C# (completamento intelligente del codice) e debug.</span><span class="sxs-lookup"><span data-stu-id="97d9a-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97d9a-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="97d9a-106">Prerequisites</span></span>

1. <span data-ttu-id="97d9a-107">Installare [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="97d9a-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="97d9a-108">Installare [.NET Core SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="97d9a-108">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="97d9a-109">Installare l'[estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) per Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="97d9a-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="97d9a-110">Per altre informazioni su come installare estensioni in Visual Studio Code, vedere [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace delle estensioni di Visual Studio Code).</span><span class="sxs-lookup"><span data-stu-id="97d9a-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="97d9a-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="97d9a-111">Hello World</span></span>

<span data-ttu-id="97d9a-112">Si inizia con un semplice programma "Hello World" in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="97d9a-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="97d9a-113">Aprire un progetto:</span><span class="sxs-lookup"><span data-stu-id="97d9a-113">Open a project:</span></span>

    * <span data-ttu-id="97d9a-114">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="97d9a-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="97d9a-115">Fare clic sull'icona Esplora nel menu a sinistra e quindi fare clic su **Apri cartella**.</span><span class="sxs-lookup"><span data-stu-id="97d9a-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="97d9a-116">Selezionare **File** > **Apri cartella** dal menu principale per aprire la cartella in cui inserire il programma C# e fare clic su **Seleziona cartella**.</span><span class="sxs-lookup"><span data-stu-id="97d9a-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="97d9a-117">Ai fini di questo esempio, viene creata una cartella per il progetto denominato *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="97d9a-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="97d9a-119">Inizializzare un progetto C#:</span><span class="sxs-lookup"><span data-stu-id="97d9a-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="97d9a-120">Aprire il terminale integrato da Visual Studio Code scegliendo **Visualizza** > **Terminale integrato** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="97d9a-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="97d9a-121">Nella finestra del terminale digitare `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="97d9a-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="97d9a-122">Questo comando crea un file `Program.cs` nella cartella con un semplice programma "Hello World" già scritto, oltre a un file di progetto C# denominato `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="97d9a-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![Comando new di dotnet](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="97d9a-124">Risolvere le risorse di compilazione:</span><span class="sxs-lookup"><span data-stu-id="97d9a-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="97d9a-125">Per **.NET Core 1.x** digitare `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="97d9a-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="97d9a-126">L'esecuzione di `dotnet restore` consente di accedere ai pacchetti .NET Core necessari per la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="97d9a-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![Comando restore di dotnet](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="97d9a-128">Eseguire il programma "Hello World":</span><span class="sxs-lookup"><span data-stu-id="97d9a-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="97d9a-129">Digitare `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="97d9a-129">Type `dotnet run`.</span></span> 

      ![Comando run di dotnet](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="97d9a-131">Per altre informazioni sull'installazione in [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu), è anche possibile guardare una breve esercitazione video.</span><span class="sxs-lookup"><span data-stu-id="97d9a-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="97d9a-132">Debug</span><span class="sxs-lookup"><span data-stu-id="97d9a-132">Debug</span></span>

1. <span data-ttu-id="97d9a-133">Aprire il file *Program.cs* facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="97d9a-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="97d9a-134">La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) viene caricato nell'editor.</span><span class="sxs-lookup"><span data-stu-id="97d9a-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![Aprire il file Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="97d9a-136">Visual Studio Code dovrebbe chiedere di aggiungere le risorse mancanti per compilare l'app ed eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="97d9a-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="97d9a-137">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="97d9a-137">Select **Yes**.</span></span> 

    ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="97d9a-139">Per aprire la visualizzazione Debug, fare clic sull'icona Debug nel menu di sinistra.</span><span class="sxs-lookup"><span data-stu-id="97d9a-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Aprire la scheda Debug](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="97d9a-141">Individuare la freccia verde nella parte superiore del riquadro.</span><span class="sxs-lookup"><span data-stu-id="97d9a-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="97d9a-142">Verificare che nel menu a discesa accanto alla freccia sia selezionato `.NET Core Launch (console)`.</span><span class="sxs-lookup"><span data-stu-id="97d9a-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![Selezione di .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="97d9a-144">Aggiungere un punto di interruzione al progetto facendo clic sul **margine dell'editor**, ovvero lo spazio a sinistra dei numeri riga nell'editor, accanto alla riga 9.</span><span class="sxs-lookup"><span data-stu-id="97d9a-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9.</span></span>

    ![Impostazione di un punto di interruzione](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="97d9a-146">Per avviare il debug, premere <kbd>F5</kbd> o fare clic sulla freccia verde.</span><span class="sxs-lookup"><span data-stu-id="97d9a-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="97d9a-147">Il debugger interrompe l'esecuzione del programma quando raggiunge il punto di interruzione impostato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="97d9a-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="97d9a-148">Durante il debug è possibile visualizzare le variabili locali nel riquadro superiore sinistro. In alternativa, usare la console di debug.</span><span class="sxs-lookup"><span data-stu-id="97d9a-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![Run e Debug](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="97d9a-150">Selezionare la freccia verde in alto per continuare il debug oppure fare clic sul quadrato rosso per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="97d9a-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="97d9a-151">Per altre informazioni e per suggerimenti sul debug .NET Core con OmniSharp in Visual Studio Code, vedere [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Istruzioni per l'impostazione del debugger .NET Core).</span><span class="sxs-lookup"><span data-stu-id="97d9a-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97d9a-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97d9a-152">See also</span></span>
<span data-ttu-id="97d9a-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)  (Impostazione di Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="97d9a-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
<span data-ttu-id="97d9a-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="97d9a-154">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
