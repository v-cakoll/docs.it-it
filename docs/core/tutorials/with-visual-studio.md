---
title: Creare un'applicazione Hello World con .NET Core in Visual StudioCreate a Hello World application with .NET Core in Visual Studio
description: Informazioni su come creare la prima applicazione console .NET Core con Visual Basic o C .
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714004"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="d52e3-103">Esercitazione: Creare la prima applicazione console .NET Core in Visual Studio 2019Tutorial: Create your first .NET Core console application in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d52e3-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="d52e3-104">In questo articolo viene fornita un'introduzione dettagliata per creare ed eseguire un'applicazione console Hello World .NET Core in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="d52e3-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="d52e3-105">Un'applicazione Hello World viene tradizionalmente utilizzata per introdurre i principianti in un nuovo linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d52e3-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="d52e3-106">Questo programma visualizza semplicemente la frase "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="d52e3-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="d52e3-107">sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="d52e3-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d52e3-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="d52e3-108">Prerequisites</span></span>

- <span data-ttu-id="d52e3-109">[Visual Studio 2019 versione 16.4 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro di **sviluppo multipiattaforma .NET Core** installato.</span><span class="sxs-lookup"><span data-stu-id="d52e3-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="d52e3-110">.NET Core 3.1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d52e3-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="d52e3-111">Per altre informazioni, vedere la sezione [Installare con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo Installare [.NET Core SDK.](../install/sdk.md?pivots=os-windows)</span><span class="sxs-lookup"><span data-stu-id="d52e3-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="d52e3-112">Creare l'app</span><span class="sxs-lookup"><span data-stu-id="d52e3-112">Create the app</span></span>

<span data-ttu-id="d52e3-113">Le istruzioni seguenti creano una semplice applicazione console Hello World:The following instructions create a simple Hello World console application:</span><span class="sxs-lookup"><span data-stu-id="d52e3-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="d52e3-114">C #</span><span class="sxs-lookup"><span data-stu-id="d52e3-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="d52e3-115">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="d52e3-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="d52e3-116">Creare un nuovo progetto di app console di C .NET Core denominato "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="d52e3-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="d52e3-117">Nella finestra di avvio scegliere **Crea un nuovo progetto.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-117">On the start window, choose **Create a new project**.</span></span>

      ![Creare un nuovo pulsante di progetto selezionato nella finestra di avvio di Visual StudioCreate a new project button selected on the Visual Studio start window](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="d52e3-119">Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d52e3-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="d52e3-120">Successivamente, scegliere **C '** dall'elenco linguaggio e quindi scegliere Tutte **le piattaforme** dall'elenco Piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d52e3-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="d52e3-121">Scegliere il modello **App console (.NET Core)** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Crea una nuova finestra di progetto con i filtri selezionati](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="d52e3-123">Se i modelli .NET Core non vengono visualizzati, è probabile che il carico di lavoro richiesto sia installato.</span><span class="sxs-lookup"><span data-stu-id="d52e3-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="d52e3-124">Sotto il messaggio **Non si trova quello che stai cercando?** scegliere il collegamento Installa altri strumenti e **funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="d52e3-125">Verrà aperto il programma di installazione di Visual Studio.The Visual Studio Installer opens.</span><span class="sxs-lookup"><span data-stu-id="d52e3-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="d52e3-126">Assicurarsi di avere installato il carico di lavoro di **sviluppo multipiattaforma .NET Core.Make** sure you have the .NET Core cross-platform development workload installed.</span><span class="sxs-lookup"><span data-stu-id="d52e3-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="d52e3-127">Nella pagina **Configura il nuovo progetto** immettere **HelloWorld** nella casella **Nome progetto.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="d52e3-128">Scegliere quindi **Crea,** quindi Crea .</span><span class="sxs-lookup"><span data-stu-id="d52e3-128">Then, choose **Create**.</span></span>

      ![Configurare la finestra del nuovo progetto con i campi Nome progetto, Percorso e Nome soluzione](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="d52e3-130">Il modello C# Console Application per .NET Core definisce automaticamente una classe, `Program`, con un singolo metodo, `Main`, che accetta una matrice <xref:System.String> come argomento.</span><span class="sxs-lookup"><span data-stu-id="d52e3-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="d52e3-131">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d52e3-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="d52e3-132">Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.</span><span class="sxs-lookup"><span data-stu-id="d52e3-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[<span data-ttu-id="d52e3-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d52e3-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="d52e3-135">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="d52e3-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="d52e3-136">Creare un nuovo progetto di app console di Visual Basic .NET Core denominato "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="d52e3-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="d52e3-137">Nella finestra di avvio scegliere **Crea un nuovo progetto.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-137">On the start window, choose **Create a new project**.</span></span>

      ![Creare un nuovo pulsante di progetto selezionato nella finestra di avvio di Visual StudioCreate a new project button selected on the Visual Studio start window](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="d52e3-139">Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d52e3-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="d52e3-140">Scegliere quindi **Visual Basic** dall'elenco Linguaggio, quindi scegliere Tutte le **piattaforme** dall'elenco Piattaforma.</span><span class="sxs-lookup"><span data-stu-id="d52e3-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="d52e3-141">Scegliere il modello **App console (.NET Core)** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Scegliere il modello Visual Basic per l'app console (.NET Framework)](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="d52e3-143">Se i modelli .NET Core non vengono visualizzati, è probabile che il carico di lavoro richiesto sia installato.</span><span class="sxs-lookup"><span data-stu-id="d52e3-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="d52e3-144">Sotto il messaggio **Non si trova quello che stai cercando?** scegliere il collegamento Installa altri strumenti e **funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="d52e3-145">Verrà aperto il programma di installazione di Visual Studio.The Visual Studio Installer opens.</span><span class="sxs-lookup"><span data-stu-id="d52e3-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="d52e3-146">Assicurarsi di avere installato il carico di lavoro di **sviluppo multipiattaforma .NET Core.Make** sure you have the .NET Core cross-platform development workload installed.</span><span class="sxs-lookup"><span data-stu-id="d52e3-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="d52e3-147">Nella pagina **Configura il nuovo progetto** immettere **HelloWorld** nella casella **Nome progetto.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="d52e3-148">Scegliere quindi **Crea,** quindi Crea .</span><span class="sxs-lookup"><span data-stu-id="d52e3-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="d52e3-149">Il modello di app console per .NET `Program`Core definisce `Main`automaticamente una <xref:System.String> classe, , con un singolo metodo, , che accetta una matrice come argomento.</span><span class="sxs-lookup"><span data-stu-id="d52e3-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="d52e3-150">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d52e3-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="d52e3-151">Tutti gli argomenti della `args` riga di comando forniti quando viene avviata l'applicazione sono disponibili nel parametro.</span><span class="sxs-lookup"><span data-stu-id="d52e3-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="d52e3-153">Il modello crea una semplice applicazione "Hello World".</span><span class="sxs-lookup"><span data-stu-id="d52e3-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="d52e3-154">Chiama il metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> per visualizzare la stringa letterale "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="d52e3-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="d52e3-155">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d52e3-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="d52e3-156">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="d52e3-156">Run the app</span></span>

1. <span data-ttu-id="d52e3-157">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Barra degli strumenti di Visual Studio con il pulsante Esegui HelloWorld selezionato](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="d52e3-159">Si apre una finestra della console con il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="d52e3-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="d52e3-160">stampate sullo schermo e alcune informazioni di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d52e3-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="d52e3-162">Premere un tasto per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d52e3-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="d52e3-163">Migliorare l'app</span><span class="sxs-lookup"><span data-stu-id="d52e3-163">Enhance the app</span></span>

<span data-ttu-id="d52e3-164">Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e ora.</span><span class="sxs-lookup"><span data-stu-id="d52e3-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="d52e3-165">Le seguenti istruzioni modificano ed eseguono nuovamente l'app:</span><span class="sxs-lookup"><span data-stu-id="d52e3-165">The following instructions modify and run the app again:</span></span>

# <a name="c"></a>[<span data-ttu-id="d52e3-166">C #</span><span class="sxs-lookup"><span data-stu-id="d52e3-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="d52e3-167">Sostituire il contenuto `Main` del metodo , che attualmente `Console.WriteLine`è solo la riga che chiama , con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d52e3-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="d52e3-168">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="d52e3-168">This code displays "What is your name?"</span></span> <span data-ttu-id="d52e3-169">nella console e attende che l'utente inserisca una stringa e prema INVIO.</span><span class="sxs-lookup"><span data-stu-id="d52e3-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="d52e3-170">Archivia la stringa in una variabile denominata `name`.</span><span class="sxs-lookup"><span data-stu-id="d52e3-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="d52e3-171">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`.</span><span class="sxs-lookup"><span data-stu-id="d52e3-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="d52e3-172">Usa infine una [stringa interpolata](../../csharp/language-reference/tokens/interpolated.md) per visualizzare questi valori nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d52e3-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="d52e3-173">Compilare il programma scegliendo **Compila** > **soluzione**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="d52e3-174">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="d52e3-175">Rispondere al prompt immettendo un nome e premendo il tasto **Invio.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="d52e3-177">Premere un tasto per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d52e3-177">Press any key to close the console window.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="d52e3-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d52e3-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="d52e3-179">Sostituire il contenuto `Main` del metodo , che attualmente `Console.WriteLine`è solo la riga che chiama , con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d52e3-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="d52e3-180">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="d52e3-180">This code displays "What is your name?"</span></span> <span data-ttu-id="d52e3-181">nella console e attende che l'utente inserisca una stringa e prema INVIO.</span><span class="sxs-lookup"><span data-stu-id="d52e3-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="d52e3-182">Archivia la stringa in una variabile denominata `name`.</span><span class="sxs-lookup"><span data-stu-id="d52e3-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="d52e3-183">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`.</span><span class="sxs-lookup"><span data-stu-id="d52e3-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="d52e3-184">Usa infine una [stringa interpolata](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) per visualizzare questi valori nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d52e3-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="d52e3-185">Compilare il programma scegliendo **Compila** > **soluzione**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="d52e3-186">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="d52e3-187">Rispondere al prompt immettendo un nome e premendo il tasto **Invio.**</span><span class="sxs-lookup"><span data-stu-id="d52e3-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="d52e3-189">Premere un tasto per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="d52e3-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="d52e3-190">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d52e3-190">Next steps</span></span>

<span data-ttu-id="d52e3-191">In questo articolo è stata creata ed eseguita la prima applicazione .NET Core.In this article, you've created and run your first .NET Core application.</span><span class="sxs-lookup"><span data-stu-id="d52e3-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="d52e3-192">Nel passaggio successivo verrà eseguito il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="d52e3-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d52e3-193">Debug a .NET Core Hello World application in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d52e3-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
