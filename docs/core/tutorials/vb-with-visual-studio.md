---
title: Compilazione di un'applicazione Hello World con .NET Core e Visual Basic in Visual Studio 2017
description: Informazioni su come compilare una semplice applicazione console .NET Core con Visual Basic usando Visual Studio 2017.
keywords: .NET Core, applicazione console .NET Core, Visual Studio 2017
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
dev_langs:
- vb
ms.workload:
- dotnetcore
ms.openlocfilehash: c3775fccf8d6e7c544cbd0b05df7043752e8bef9
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2018
---
# <a name="build-a-visual-basic-hello-world-application-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="7ab70-104">Compilare un'applicazione Hello World in Visual Basic con .NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7ab70-104">Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="7ab70-105">Questo argomento offre un'introduzione dettagliata per la compilazione, il debug e la pubblicazione di una semplice applicazione console .NET Core usando Visual Basic in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7ab70-105">This topic provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using Visual Basic in Visual Studio 2017.</span></span> <span data-ttu-id="7ab70-106">Visual Studio 2017 offre un ambiente di sviluppo completo per la creazione di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ab70-106">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="7ab70-107">Se l'applicazione non ha alcuna dipendenza specifica della piattaforma, è possibile eseguirla su qualsiasi piattaforma usata come destinazione da .NET Core o su qualsiasi sistema in cui è installato .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ab70-107">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ab70-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7ab70-108">Prerequisites</span></span>

<span data-ttu-id="7ab70-109">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.</span><span class="sxs-lookup"><span data-stu-id="7ab70-109">[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="7ab70-110">È possibile sviluppare l'app con .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="7ab70-110">You can develop your app with .NET Core 2.0.</span></span>

<span data-ttu-id="7ab70-111">Per altre informazioni, vedere [Prerequisiti per .NET Core in Windows](../../core/windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="7ab70-111">For more information, see [Prerequisites for .NET Core on Windows](../../core/windows-prerequisites.md).</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="7ab70-112">Semplice applicazione Hello World</span><span class="sxs-lookup"><span data-stu-id="7ab70-112">A simple Hello World application</span></span>

<span data-ttu-id="7ab70-113">Di seguito viene descritta la creazione di una semplice applicazione console "Hello World".</span><span class="sxs-lookup"><span data-stu-id="7ab70-113">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="7ab70-114">Attenersi ai passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7ab70-114">Follow these steps:</span></span>

1. <span data-ttu-id="7ab70-115">Avviare Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7ab70-115">Launch Visual Studio 2017.</span></span> <span data-ttu-id="7ab70-116">Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="7ab70-116">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="7ab70-117">Nella finestra di dialogo *Nuovo progetto*\* selezionare il nodo **Visual Basic** aggiungendo il nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="7ab70-117">In the *New Project*\* dialog, select the **Visual Basic** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="7ab70-118">Selezionare quindi il modello di progetto **App console (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="7ab70-118">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="7ab70-119">Nella casella di testo **Nome** digitare "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="7ab70-119">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="7ab70-120">Selezionare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="7ab70-120">Select the **OK** button.</span></span>

   ![Finestra di dialogo Nuovo progetto con App console selezionata](./media/vb-with-visual-studio/new-project.png)
   
1. <span data-ttu-id="7ab70-122">Visual Studio usa il modello per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="7ab70-122">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="7ab70-123">Il modello App console di Visual Basic per .NET Core definisce automaticamente una classe, `Program`, con un singolo metodo, `Main` che accetta una matrice <xref:System.String> come argomento.</span><span class="sxs-lookup"><span data-stu-id="7ab70-123">The Visual Basic Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="7ab70-124">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7ab70-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="7ab70-125">Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.</span><span class="sxs-lookup"><span data-stu-id="7ab70-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio e il nuovo progetto HelloWorld](./media/vb-with-visual-studio/devenv.png)

   <span data-ttu-id="7ab70-127">Il modello crea una semplice applicazione "Hello World".</span><span class="sxs-lookup"><span data-stu-id="7ab70-127">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="7ab70-128">Chiama il metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> per visualizzare la stringa letterale "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="7ab70-128">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="7ab70-129">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="7ab70-129">in the console window.</span></span> <span data-ttu-id="7ab70-130">Facendo clic sul pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti è possibile eseguire il programma in modalità debug.</span><span class="sxs-lookup"><span data-stu-id="7ab70-130">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="7ab70-131">Se si esegue questa operazione, la finestra della console rimane visibile solo per un intervallo di tempo molto breve.</span><span class="sxs-lookup"><span data-stu-id="7ab70-131">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="7ab70-132">Questo si verifica perché il metodo `Main` termina e l'applicazione viene chiusa non appena viene eseguita l'unica istruzione del metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="7ab70-132">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="7ab70-133">Per impostare l'applicazione in modo che sospenda la finestra della console prima di chiuderla, aggiungere il codice seguente immediatamente dopo la chiamata al metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="7ab70-133">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method:</span></span>

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   <span data-ttu-id="7ab70-134">Il codice chiede all'utente di premere un tasto qualsiasi e quindi sospende il programma fino a quando non viene premuto un tasto.</span><span class="sxs-lookup"><span data-stu-id="7ab70-134">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="7ab70-135">Nella barra dei menu selezionare **Compila** > **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="7ab70-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="7ab70-136">Il programma viene compilato in un linguaggio intermedio (IL) che viene successivamente convertito in codice binario da un compilatore JIT (Just-In-Time).</span><span class="sxs-lookup"><span data-stu-id="7ab70-136">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="7ab70-137">Eseguire il programma facendo clic sul pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="7ab70-137">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/helloworld1.png)

1. <span data-ttu-id="7ab70-139">Premere un tasto qualsiasi per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="7ab70-139">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="7ab70-140">Miglioramento dell'applicazione Hello World</span><span class="sxs-lookup"><span data-stu-id="7ab70-140">Enhancing the Hello World application</span></span>

<span data-ttu-id="7ab70-141">Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.</span><span class="sxs-lookup"><span data-stu-id="7ab70-141">Enhance your application to prompt the user for his or her name and to display it along with the date and time.</span></span> <span data-ttu-id="7ab70-142">Per modificare e testare il programma, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="7ab70-142">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="7ab70-143">Immettere il codice Visual Basic seguente nella finestra del codice immediatamente dopo la parentesi quadra di apertura che segue la riga `Sub Main(args As String())` e prima della prima parentesi quadra di chiusura:</span><span class="sxs-lookup"><span data-stu-id="7ab70-143">Enter the following Visual Basic code in the code window immediately after the opening bracket that follows the `Sub Main(args As String())` line and before the first closing bracket:</span></span>

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="7ab70-144">Questo codice sostituisce le istruzioni <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType> e <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> esistenti.</span><span class="sxs-lookup"><span data-stu-id="7ab70-144">This code replaces the existing <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType>, and <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> statements.</span></span>

   ![File di programma Visual Studio con il metodo Main aggiornato](./media/vb-with-visual-studio/codewindow.png)

   <span data-ttu-id="7ab70-146">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="7ab70-146">This code displays "What is your name?"</span></span> <span data-ttu-id="7ab70-147">nella console e attende che l'utente inserisca una stringa e prema INVIO.</span><span class="sxs-lookup"><span data-stu-id="7ab70-147">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="7ab70-148">Archivia la stringa in una variabile denominata `name`.</span><span class="sxs-lookup"><span data-stu-id="7ab70-148">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="7ab70-149">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `currentDate`.</span><span class="sxs-lookup"><span data-stu-id="7ab70-149">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `currentDate`.</span></span> <span data-ttu-id="7ab70-150">Usa infine una [stringa interpolata](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) per visualizzare questi valori nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="7ab70-150">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="7ab70-151">Compilare il programma scegliendo **Compila** > **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="7ab70-151">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="7ab70-152">Eseguire il programma in modalità debug in Visual Studio selezionando la freccia verde sulla barra degli strumenti, premendo F5 oppure scegliendo la voce di menu **Debug** > **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="7ab70-152">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="7ab70-153">Rispondere alla richiesta immettendo un nome e premendo il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="7ab70-153">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/helloworld2.png)

1. <span data-ttu-id="7ab70-155">Premere un tasto qualsiasi per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="7ab70-155">Press any key to close the console window.</span></span>

<span data-ttu-id="7ab70-156">L'applicazione è stata creata ed eseguita.</span><span class="sxs-lookup"><span data-stu-id="7ab70-156">You've created and run your application.</span></span> <span data-ttu-id="7ab70-157">Per sviluppare un'applicazione professionale, eseguire alcuni passaggi aggiuntivi per rendere un'applicazione pronta per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="7ab70-157">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="7ab70-158">Per altre informazioni sul debug dell'applicazione, vedere [Debug dell'applicazione C# Hello World con Visual Studio 2017](debugging-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7ab70-158">For information on debugging your application, see [Debugging your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="7ab70-159">Per informazioni sullo sviluppo e la pubblicazione di una versione distribuibile dell'applicazione, vedere [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md) (Pubblicazione dell'applicazione Hello World usando C# con Visual Studio 2017).</span><span class="sxs-lookup"><span data-stu-id="7ab70-159">For information on developing and publishing a distributable version of your application, see [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

<!--
## Related topics

Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017. For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).

You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor. For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md). -->
