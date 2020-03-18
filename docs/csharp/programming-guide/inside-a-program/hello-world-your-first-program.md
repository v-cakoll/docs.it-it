---
title: Hello World -- Il primo programma che usa Visual Studio su Windows o Mac - Guida per programmatori C
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 910fa4af1b4e45ce627b589a06910dc168490047
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712143"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="fc5ec-102">Hello World -- Il tuo primo programma</span><span class="sxs-lookup"><span data-stu-id="fc5ec-102">Hello World -- Your first program</span></span>

<span data-ttu-id="fc5ec-103">In questo articolo si userà Visual Studio per creare il tradizionale "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="fc5ec-103">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="fc5ec-104">tradizionale.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-104">program.</span></span> <span data-ttu-id="fc5ec-105">Visual Studio è un ambiente di sviluppo integrato (IDE) professionale con molte funzionalità progettate per lo sviluppo .NET.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-105">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="fc5ec-106">Si useranno solo alcune delle funzionalità di Visual Studio per creare questo programma.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-106">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="fc5ec-107">Per ulteriori informazioni su Visual Studio, vedere [Guida introduttiva a Visual C .](/visualstudio/ide/quickstart-csharp-console)</span><span class="sxs-lookup"><span data-stu-id="fc5ec-107">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="fc5ec-108">Creare una nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="fc5ec-108">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="fc5ec-109">Windows</span><span class="sxs-lookup"><span data-stu-id="fc5ec-109">Windows</span></span>](#tab/windows)

<span data-ttu-id="fc5ec-110">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-110">Start Visual Studio.</span></span> <span data-ttu-id="fc5ec-111">In Windows verrà visualizzata l'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-111">You'll see the following image on Windows:</span></span>

![Schermata iniziale di Visual Studio in Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="fc5ec-113">Selezionare **Crea un nuovo progetto** nell'angolo inferiore destro dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-113">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="fc5ec-114">Visual Studio visualizza la finestra di dialogo **Nuovo progetto:Visual** Studio displays the New Project dialog:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-114">Visual Studio displays the **New Project** dialog:</span></span>

![Schermata del nuovo progetto di Visual Studio in Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="fc5ec-116">Se è la prima volta che si avvia Visual Studio, l'elenco Modelli di **progetto recenti** è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-116">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="fc5ec-117">Nella finestra di dialogo del nuovo progetto scegliere "Console App (.NET Core)" e quindi premere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-117">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="fc5ec-118">Assegnare un nome al progetto, ad esempio "HelloWorld", quindi premere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-118">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="fc5ec-119">Visual Studio apre il progetto.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-119">Visual Studio opens your project.</span></span> <span data-ttu-id="fc5ec-120">È già un "Hello World!" di base</span><span class="sxs-lookup"><span data-stu-id="fc5ec-120">It's already a basic "Hello World!"</span></span> <span data-ttu-id="fc5ec-121">standard.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-121">example.</span></span> <span data-ttu-id="fc5ec-122">`Ctrl`  +  Premere `F5` per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-122">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="fc5ec-123">Visual Studio compila il progetto, convertendo il codice sorgente in un eseguibile.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-123">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="fc5ec-124">Quindi, avvia una finestra di comando che esegue la nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-124">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="fc5ec-125">Nella finestra dovrebbe essere visualizzato il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-125">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="fc5ec-126">Premere un tasto per chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-126">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="fc5ec-127">Macos</span><span class="sxs-lookup"><span data-stu-id="fc5ec-127">macOS</span></span>](#tab/macos)

<span data-ttu-id="fc5ec-128">Avviare Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-128">Start Visual Studio for Mac.</span></span> <span data-ttu-id="fc5ec-129">Vedrai la seguente immagine su Mac:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-129">You'll see the following image on Mac:</span></span>

![Schermata iniziale di Visual Studio su Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="fc5ec-131">Se è la prima volta che si avvia Visual Studio per Mac, l'elenco **Progetti recenti** è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-131">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="fc5ec-132">Selezionare **Nuovo** nell'angolo superiore destro dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-132">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="fc5ec-133">Visual Studio per Mac visualizza la finestra di dialogo **Nuovo progetto:Visual** Studio for Mac displays the New Project dialog:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-133">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Schermata del nuovo progetto di Visual Studio su Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="fc5ec-135">Nella finestra di dialogo del nuovo progetto scegliere ".NET Core" e "Console App" e quindi premere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-135">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="fc5ec-136">È necessario selezionare il framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-136">You'll need to select the target framework.</span></span> <span data-ttu-id="fc5ec-137">L'impostazione predefinita è corretta, quindi premere Avanti.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-137">The default is fine, so press next.</span></span> <span data-ttu-id="fc5ec-138">Assegnare un nome al progetto, ad esempio "HelloWorld", quindi premere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-138">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="fc5ec-139">È possibile utilizzare il percorso predefinito del progetto.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-139">You can use the default project location.</span></span> <span data-ttu-id="fc5ec-140">Non aggiungere questo progetto al controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-140">Don't add this project to source control.</span></span>

<span data-ttu-id="fc5ec-141">Visual Studio per Mac apre il progetto.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-141">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="fc5ec-142">È già un "Hello World!" di base</span><span class="sxs-lookup"><span data-stu-id="fc5ec-142">It's already a basic "Hello World!"</span></span> <span data-ttu-id="fc5ec-143">standard.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-143">example.</span></span> <span data-ttu-id="fc5ec-144">`Ctrl`  +  Premere `Fn`  +  eseguire il `F5` progetto.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-144">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="fc5ec-145">Visual Studio per Mac compila il progetto, convertendo il codice sorgente in un eseguibile.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-145">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="fc5ec-146">Quindi, avvia una finestra di comando che esegue la nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-146">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="fc5ec-147">Nella finestra dovrebbe essere visualizzato il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-147">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="fc5ec-148">Premere un tasto per terminare la sessione.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-148">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="fc5ec-149">Elementi di un programma in C</span><span class="sxs-lookup"><span data-stu-id="fc5ec-149">Elements of a C# program</span></span>

<span data-ttu-id="fc5ec-150">Esaminiamo le parti importanti di questo programma.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-150">Let's examine the important parts of this program.</span></span> <span data-ttu-id="fc5ec-151">La prima riga contiene un commento.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-151">The first line contains a comment.</span></span> <span data-ttu-id="fc5ec-152">I caratteri `//` convertono il resto della riga in un commento.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-152">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="fc5ec-153">È anche possibile commentare un blocco di testo racchiudendolo tra i caratteri `/*` e `*/`,</span><span class="sxs-lookup"><span data-stu-id="fc5ec-153">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="fc5ec-154">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-154">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="fc5ec-155">È necessario che un'applicazione console C# contenga un metodo `Main`, in cui il controllo inizia e finisce.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-155">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="fc5ec-156">Il metodo `Main` consente di creare oggetti e di eseguire altri metodi.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-156">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="fc5ec-157">Il metodo `Main` è un metodo di tipo [static](../../language-reference/keywords/static.md) che si trova all'interno di una classe o di uno struct.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-157">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="fc5ec-158">Nell'esempio "Hello World!" precedente</span><span class="sxs-lookup"><span data-stu-id="fc5ec-158">In the previous "Hello World!"</span></span> <span data-ttu-id="fc5ec-159">si trovava in una classe denominata `Hello`.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-159">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="fc5ec-160">È possibile dichiarare il metodo `Main` in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-160">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="fc5ec-161">Può restituire un valore `void`.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-161">It can return `void`.</span></span> <span data-ttu-id="fc5ec-162">Ciò significa che il programma non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-162">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="fc5ec-163">Può restituire anche un valore intero.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-163">It can also return an integer.</span></span> <span data-ttu-id="fc5ec-164">Il numero intero è il **codice di uscita** per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-164">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="fc5ec-165">Con entrambi i tipi restituiti, può accettare argomenti.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-165">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="fc5ec-166">-oppure-</span><span class="sxs-lookup"><span data-stu-id="fc5ec-166">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="fc5ec-167">Il parametro del metodo `Main`, `args`, è una matrice `string` che contiene gli argomenti della riga di comando usati per richiamare il programma.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-167">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="fc5ec-168">Per ulteriori informazioni sull'utilizzo degli argomenti della riga di comando, consultate gli esempi in Argomenti della riga di [comando e Main().](../main-and-command-args/index.md)</span><span class="sxs-lookup"><span data-stu-id="fc5ec-168">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="fc5ec-169">Input e output</span><span class="sxs-lookup"><span data-stu-id="fc5ec-169">Input and output</span></span>

<span data-ttu-id="fc5ec-170">In genere i programmi C# usano i servizi di input/output offerti dalla libreria run-time di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-170">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="fc5ec-171">L'istruzione `System.Console.WriteLine("Hello World!");` usa il metodo <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-171">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="fc5ec-172">Questo è uno dei metodi di output della classe <xref:System.Console> nella libreria di runtime.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-172">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="fc5ec-173">Visualizza il parametro di tipo stringa sul flusso di output standard seguito da una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-173">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="fc5ec-174">Sono disponibili altri metodi <xref:System.Console> per diverse operazioni di input e output.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-174">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="fc5ec-175">Se si include la direttiva `using System;` all'inizio del programma, è possibile usare direttamente le classi e i metodi <xref:System> senza specificarne il nome completo.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-175">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="fc5ec-176">Ad esempio, è possibile chiamare `Console.WriteLine` anziché `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="fc5ec-176">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="fc5ec-177">Per altre informazioni sui metodi di input/output, vedere <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="fc5ec-177">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc5ec-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc5ec-178">See also</span></span>

- [<span data-ttu-id="fc5ec-179">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fc5ec-179">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fc5ec-180">Esempi ed esercitazioni</span><span class="sxs-lookup"><span data-stu-id="fc5ec-180">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="fc5ec-181">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="fc5ec-181">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="fc5ec-182">Guida introduttiva a Visual C#</span><span class="sxs-lookup"><span data-stu-id="fc5ec-182">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
