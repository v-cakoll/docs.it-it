---
title: Creare un'applicazione Hello World con .NET Core in Visual Studio
description: Informazioni su come creare la prima applicazione console .NET Core con C# o Visual Basic usando Visual Studio.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 427c4bddc8a3e5c05e6d25cfd72a5a93bfc09a9b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75339526"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="66d4a-103">Esercitazione: creare la prima applicazione console .NET Core in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="66d4a-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="66d4a-104">Questo articolo fornisce un'introduzione dettagliata per creare ed eseguire un'applicazione console Hello World .NET Core in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="66d4a-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="66d4a-105">Un'applicazione Hello World viene tradizionalmente utilizzata per introdurre i principianti di un nuovo linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="66d4a-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="66d4a-106">Questo programma visualizza semplicemente la frase "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="66d4a-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="66d4a-107">sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="66d4a-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66d4a-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="66d4a-108">Prerequisites</span></span>

- <span data-ttu-id="66d4a-109">[Visual Studio 2019 versione 16,4 o una versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro **sviluppo multipiattaforma .NET Core** installato.</span><span class="sxs-lookup"><span data-stu-id="66d4a-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="66d4a-110">.NET Core 3,1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="66d4a-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="66d4a-111">Per ulteriori informazioni, vedere la sezione [install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) .</span><span class="sxs-lookup"><span data-stu-id="66d4a-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="66d4a-112">Creare l'app</span><span class="sxs-lookup"><span data-stu-id="66d4a-112">Create the app</span></span>

<span data-ttu-id="66d4a-113">Le istruzioni seguenti creano una semplice applicazione console Hello World:</span><span class="sxs-lookup"><span data-stu-id="66d4a-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="66d4a-114">C#</span><span class="sxs-lookup"><span data-stu-id="66d4a-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="66d4a-115">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="66d4a-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="66d4a-116">Creare un nuovo C# progetto di app console .NET Core denominato "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="66d4a-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="66d4a-117">Nella finestra iniziale scegliere **Crea un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-117">On the start window, choose **Create a new project**.</span></span>

      ![Pulsante Crea un nuovo progetto selezionato nella finestra di avvio di Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="66d4a-119">Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="66d4a-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="66d4a-120">Scegliere **C#** quindi dall'elenco lingua, quindi scegliere **tutte le piattaforme** dall'elenco piattaforma.</span><span class="sxs-lookup"><span data-stu-id="66d4a-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="66d4a-121">Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Crea una nuova finestra del progetto con i filtri selezionati](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="66d4a-123">Se non vengono visualizzati i modelli .NET Core, probabilmente manca il carico di lavoro richiesto installato.</span><span class="sxs-lookup"><span data-stu-id="66d4a-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="66d4a-124">Nel messaggio **non trovare ciò che si sta cercando?** scegliere il collegamento **Installa altri strumenti e funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="66d4a-125">Verrà visualizzata la Programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66d4a-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="66d4a-126">Assicurarsi che sia installato il carico di lavoro **sviluppo multipiattaforma .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="66d4a-127">Nella pagina **Configura nuovo progetto** immettere **HelloWorld** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="66d4a-128">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-128">Then, choose **Create**.</span></span>

      ![Configurare la finestra nuovo progetto con i campi nome progetto, percorso e nome soluzione](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="66d4a-130">Il modello C# Console Application per .NET Core definisce automaticamente una classe, `Program`, con un singolo metodo, `Main`, che accetta una matrice <xref:System.String> come argomento.</span><span class="sxs-lookup"><span data-stu-id="66d4a-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="66d4a-131">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66d4a-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="66d4a-132">Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.</span><span class="sxs-lookup"><span data-stu-id="66d4a-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basictabvb"></a>[<span data-ttu-id="66d4a-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66d4a-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="66d4a-135">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="66d4a-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="66d4a-136">Creare un nuovo progetto di app console di Visual Basic .NET Core denominato "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="66d4a-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="66d4a-137">Nella finestra iniziale scegliere **Crea un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-137">On the start window, choose **Create a new project**.</span></span>

      ![Pulsante Crea un nuovo progetto selezionato nella finestra di avvio di Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="66d4a-139">Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="66d4a-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="66d4a-140">Successivamente, scegliere **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.</span><span class="sxs-lookup"><span data-stu-id="66d4a-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="66d4a-141">Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Scegliere il modello Visual Basic per l'app console (.NET Framework)](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="66d4a-143">Se non vengono visualizzati i modelli .NET Core, probabilmente manca il carico di lavoro richiesto installato.</span><span class="sxs-lookup"><span data-stu-id="66d4a-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="66d4a-144">Nel messaggio **non trovare ciò che si sta cercando?** scegliere il collegamento **Installa altri strumenti e funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="66d4a-145">Verrà visualizzata la Programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66d4a-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="66d4a-146">Assicurarsi che sia installato il carico di lavoro **sviluppo multipiattaforma .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="66d4a-147">Nella pagina **Configura nuovo progetto** immettere **HelloWorld** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="66d4a-148">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="66d4a-149">Il modello di app console per .NET Core definisce automaticamente una classe, `Program`con un solo metodo, `Main`, che accetta una matrice <xref:System.String> come argomento.</span><span class="sxs-lookup"><span data-stu-id="66d4a-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="66d4a-150">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66d4a-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="66d4a-151">Qualsiasi argomento della riga di comando fornito quando viene avviata l'applicazione è disponibile nel parametro `args`.</span><span class="sxs-lookup"><span data-stu-id="66d4a-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="66d4a-153">Il modello crea una semplice applicazione "Hello World".</span><span class="sxs-lookup"><span data-stu-id="66d4a-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="66d4a-154">Chiama il metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> per visualizzare la stringa letterale "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="66d4a-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="66d4a-155">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="66d4a-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="66d4a-156">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="66d4a-156">Run the app</span></span>

1. <span data-ttu-id="66d4a-157">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Barra degli strumenti di Visual Studio con il pulsante di esecuzione HelloWorld selezionato](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="66d4a-159">Viene visualizzata una finestra della console con il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="66d4a-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="66d4a-160">stampato sullo schermo e alcune informazioni di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66d4a-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="66d4a-162">Premere un tasto qualsiasi per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="66d4a-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="66d4a-163">Migliorare l'app</span><span class="sxs-lookup"><span data-stu-id="66d4a-163">Enhance the app</span></span>

<span data-ttu-id="66d4a-164">Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e ora.</span><span class="sxs-lookup"><span data-stu-id="66d4a-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="66d4a-165">Le istruzioni seguenti modificano ed eseguono di nuovo l'app:</span><span class="sxs-lookup"><span data-stu-id="66d4a-165">The following instructions modify and run the app again:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="66d4a-166">C#</span><span class="sxs-lookup"><span data-stu-id="66d4a-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="66d4a-167">Sostituire il contenuto del metodo `Main`, che attualmente è solo la riga che chiama `Console.WriteLine`, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="66d4a-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="66d4a-168">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="66d4a-168">This code displays "What is your name?"</span></span> <span data-ttu-id="66d4a-169">nella console e attende che l'utente inserisca una stringa e prema INVIO.</span><span class="sxs-lookup"><span data-stu-id="66d4a-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="66d4a-170">Archivia la stringa in una variabile denominata `name`.</span><span class="sxs-lookup"><span data-stu-id="66d4a-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="66d4a-171">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`.</span><span class="sxs-lookup"><span data-stu-id="66d4a-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="66d4a-172">Usa infine una [stringa interpolata](../../csharp/language-reference/tokens/interpolated.md) per visualizzare questi valori nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="66d4a-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="66d4a-173">Compilare il programma scegliendo **Compila** > **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="66d4a-174">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="66d4a-175">Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="66d4a-177">Premere un tasto qualsiasi per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="66d4a-177">Press any key to close the console window.</span></span>

# <a name="visual-basictabvb"></a>[<span data-ttu-id="66d4a-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66d4a-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="66d4a-179">Sostituire il contenuto del metodo `Main`, che attualmente è solo la riga che chiama `Console.WriteLine`, con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="66d4a-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="66d4a-180">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="66d4a-180">This code displays "What is your name?"</span></span> <span data-ttu-id="66d4a-181">nella console e attende che l'utente inserisca una stringa e prema INVIO.</span><span class="sxs-lookup"><span data-stu-id="66d4a-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="66d4a-182">Archivia la stringa in una variabile denominata `name`.</span><span class="sxs-lookup"><span data-stu-id="66d4a-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="66d4a-183">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`.</span><span class="sxs-lookup"><span data-stu-id="66d4a-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="66d4a-184">Usa infine una [stringa interpolata](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) per visualizzare questi valori nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="66d4a-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="66d4a-185">Compilare il programma scegliendo **Compila** > **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="66d4a-186">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="66d4a-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="66d4a-187">Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .</span><span class="sxs-lookup"><span data-stu-id="66d4a-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="66d4a-189">Premere un tasto qualsiasi per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="66d4a-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="66d4a-190">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="66d4a-190">Next steps</span></span>

<span data-ttu-id="66d4a-191">In questo articolo è stata creata ed eseguita la prima applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="66d4a-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="66d4a-192">Nel passaggio successivo verrà eseguito il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66d4a-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="66d4a-193">Eseguire il debug di un'applicazione Hello World .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66d4a-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
