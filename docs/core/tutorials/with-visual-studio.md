---
title: Creare un'applicazione console con .NET Core in Visual Studio
description: Informazioni su come creare un'applicazione console .NET Core con C# o Visual Basic con Visual Studio.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 144d7bb087034839ad2cde2fa28a4961cff4321f
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306994"
---
# <a name="tutorial-create-a-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="ba026-103">Esercitazione: creare un'applicazione console .NET Core in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ba026-103">Tutorial: Create a .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="ba026-104">Questa esercitazione illustra come creare ed eseguire un'applicazione console .NET Core in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="ba026-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba026-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ba026-105">Prerequisites</span></span>

- <span data-ttu-id="ba026-106">[Visual Studio 2019 versione 16,6 o una versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro **sviluppo multipiattaforma .NET Core** installato.</span><span class="sxs-lookup"><span data-stu-id="ba026-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="ba026-107">.NET Core 3,1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ba026-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="ba026-108">Per ulteriori informazioni, vedere la sezione [install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) .</span><span class="sxs-lookup"><span data-stu-id="ba026-108">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="ba026-109">Creare l'app</span><span class="sxs-lookup"><span data-stu-id="ba026-109">Create the app</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="ba026-110">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="ba026-110">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="ba026-111">Creare un nuovo progetto di app console .NET Core denominato "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="ba026-111">Create a new .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="ba026-112">Nella pagina iniziale scegliere **Crea un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="ba026-112">On the start page, choose **Create a new project**.</span></span>

      ![Pulsante Crea un nuovo progetto selezionato nella pagina iniziale di Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="ba026-114">Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ba026-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="ba026-115">Successivamente, scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ba026-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="ba026-116">Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ba026-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Crea una nuova finestra del progetto con i filtri selezionati](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="ba026-118">Se i modelli .NET Core non sono visibili, probabilmente manca il carico di lavoro richiesto.</span><span class="sxs-lookup"><span data-stu-id="ba026-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="ba026-119">Nel messaggio **non trovare ciò che si sta cercando?** scegliere il collegamento **Installa altri strumenti e funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="ba026-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="ba026-120">Verrà visualizzata la Programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ba026-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="ba026-121">Assicurarsi che sia installato il carico di lavoro **sviluppo multipiattaforma .NET Core** .</span><span class="sxs-lookup"><span data-stu-id="ba026-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="ba026-122">Nella pagina **Configura nuovo progetto** immettere **HelloWorld** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="ba026-122">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="ba026-123">Scegli quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ba026-123">Then choose **Create**.</span></span>

      ![Configurare la finestra nuovo progetto con i campi nome progetto, percorso e nome soluzione](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="ba026-125">Il modello di applicazione console per .NET Core definisce una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento.</span><span class="sxs-lookup"><span data-stu-id="ba026-125">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="ba026-126">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba026-126">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="ba026-127">Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.</span><span class="sxs-lookup"><span data-stu-id="ba026-127">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   <span data-ttu-id="ba026-128">Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="ba026-128">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   using System;

   namespace HelloWorld
   {
       class Program
       {
           static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   ```vb
   Imports System

   Module Program
       Sub Main(args As String())
           Console.WriteLine("Hello World!")
       End Sub
   End Module
   ```

   <span data-ttu-id="ba026-129">Il modello crea una semplice applicazione "Hello World".</span><span class="sxs-lookup"><span data-stu-id="ba026-129">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="ba026-130">Chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="ba026-130">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="ba026-131">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="ba026-131">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="ba026-132">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="ba026-132">Run the app</span></span>

1. <span data-ttu-id="ba026-133">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="ba026-133">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Barra degli strumenti di Visual Studio con il pulsante di esecuzione HelloWorld selezionato](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="ba026-135">Viene visualizzata una finestra della console con il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="ba026-135">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="ba026-136">stampato sullo schermo e alcune informazioni di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ba026-136">printed on the screen and some Visual Studio debug information.</span></span>

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="ba026-138">Premere un tasto per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="ba026-138">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="ba026-139">Migliorare l'app</span><span class="sxs-lookup"><span data-stu-id="ba026-139">Enhance the app</span></span>

<span data-ttu-id="ba026-140">Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.</span><span class="sxs-lookup"><span data-stu-id="ba026-140">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="ba026-141">Le istruzioni seguenti modificano l'app ed eseguono di nuovo l'app:</span><span class="sxs-lookup"><span data-stu-id="ba026-141">The following instructions modify the app and run it again:</span></span>

1. <span data-ttu-id="ba026-142">Sostituire il contenuto del `Main` metodo, che attualmente è solo la riga che chiama `Console.WriteLine` , con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ba026-142">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](./snippets/with-visual-studio/csharp/Program.cs#1)]
   [!code-vb[GettingStarted#1](./snippets/with-visual-studio/vb/Program.vb#1)]

   <span data-ttu-id="ba026-143">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="ba026-143">This code displays "What is your name?"</span></span> <span data-ttu-id="ba026-144">nella console e attende che l'utente inserisca una stringa e prema INVIO.</span><span class="sxs-lookup"><span data-stu-id="ba026-144">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="ba026-145">Archivia la stringa in una variabile denominata `name` .</span><span class="sxs-lookup"><span data-stu-id="ba026-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="ba026-146">Recupera inoltre il valore della <xref:System.DateTime.Now?displayProperty=nameWithType> proprietà che contiene l'ora locale corrente e la assegna a una variabile denominata `date` ( `currentDate` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ba026-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="ba026-147">Infine, questi valori vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="ba026-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="ba026-148">`\n`( `vbCrLf` In Visual Basic) rappresenta un carattere di nuova riga.</span><span class="sxs-lookup"><span data-stu-id="ba026-148">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="ba026-149">Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa.</span><span class="sxs-lookup"><span data-stu-id="ba026-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="ba026-150">Il valore dell'espressione viene inserito nella stringa al posto dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ba026-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="ba026-151">Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="ba026-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="ba026-152">Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="ba026-152">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="ba026-153">Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .</span><span class="sxs-lookup"><span data-stu-id="ba026-153">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="ba026-155">Premere un tasto per chiudere la finestra della console.</span><span class="sxs-lookup"><span data-stu-id="ba026-155">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba026-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ba026-156">Next steps</span></span>

<span data-ttu-id="ba026-157">In questa esercitazione è stata creata un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ba026-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="ba026-158">Nell'esercitazione successiva si esegue il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="ba026-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba026-159">Eseguire il debug di un'applicazione console .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ba026-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
