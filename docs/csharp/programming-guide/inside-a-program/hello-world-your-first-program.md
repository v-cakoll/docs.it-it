---
title: Hello World -- Il primo programma - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 40c869d267dcabf4bd209b2ee86085f899a93231
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236388"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="72038-102">Hello World -- Il primo programma (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="72038-102">Hello World -- Your First Program (C# Programming Guide)</span></span>
<span data-ttu-id="72038-103">La procedura seguente crea una versione C# del programma "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="72038-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="72038-104">tradizionale.</span><span class="sxs-lookup"><span data-stu-id="72038-104">program.</span></span> <span data-ttu-id="72038-105">Il programma visualizza la stringa `Hello World!`</span><span class="sxs-lookup"><span data-stu-id="72038-105">The program displays the string `Hello World!`</span></span>  
  
 <span data-ttu-id="72038-106">Per altri esempi di concetti introduttivi, vedere [Introduzione a Visual C# e Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="72038-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="72038-107">Per creare ed eseguire un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="72038-107">To create and run a console application</span></span>  
  
1.  <span data-ttu-id="72038-108">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72038-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="72038-109">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="72038-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="72038-110">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="72038-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="72038-111">Espandere **Installati**, **Modelli** e **Visual C#** e scegliere **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="72038-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="72038-112">Nella casella **Nome** specificare un nome per il progetto e quindi scegliere il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="72038-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="72038-113">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="72038-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="72038-114">Se Program.cs non è aperto nell'**Editor di codice**, aprire il menu di scelta rapida per **Program.cs** in **Esplora soluzioni** e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="72038-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="72038-115">Sostituire il contenuto di Program.cs con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="72038-115">Replace the contents of Program.cs with the following code.</span></span>  
  
     [!code-csharp[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  <span data-ttu-id="72038-116">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="72038-116">Choose the F5 key to run the project.</span></span> <span data-ttu-id="72038-117">Viene visualizzata una finestra del prompt dei comandi che contiene la riga `Hello World!`</span><span class="sxs-lookup"><span data-stu-id="72038-117">A Command Prompt window appears that contains the line `Hello World!`</span></span>  
  
 <span data-ttu-id="72038-118">Successivamente, vengono esaminate le parti importanti del programma.</span><span class="sxs-lookup"><span data-stu-id="72038-118">Next, the important parts of this program are examined.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="72038-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="72038-119">Comments</span></span>  
 <span data-ttu-id="72038-120">La prima riga contiene un commento.</span><span class="sxs-lookup"><span data-stu-id="72038-120">The first line contains a comment.</span></span> <span data-ttu-id="72038-121">I caratteri `//` convertono il resto della riga in un commento.</span><span class="sxs-lookup"><span data-stu-id="72038-121">The characters `//` convert the rest of the line to a comment.</span></span>  
  
 [!code-csharp[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 <span data-ttu-id="72038-122">È anche possibile commentare un blocco di testo racchiudendolo tra i caratteri `/*` e `*/`,</span><span class="sxs-lookup"><span data-stu-id="72038-122">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="72038-123">come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="72038-123">This is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## <a name="main-method"></a><span data-ttu-id="72038-124">Metodo Main</span><span class="sxs-lookup"><span data-stu-id="72038-124">Main Method</span></span>  
 <span data-ttu-id="72038-125">È necessario che un'applicazione console C# contenga un metodo `Main`, in cui il controllo inizia e finisce.</span><span class="sxs-lookup"><span data-stu-id="72038-125">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="72038-126">Il metodo `Main` consente di creare oggetti e di eseguire altri metodi.</span><span class="sxs-lookup"><span data-stu-id="72038-126">The `Main` method is where you create objects and execute other methods.</span></span>  
  
 <span data-ttu-id="72038-127">Il metodo `Main` è un metodo di tipo [static](../../../csharp/language-reference/keywords/static.md) che si trova all'interno di una classe o di uno struct.</span><span class="sxs-lookup"><span data-stu-id="72038-127">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="72038-128">Nell'esempio "Hello World!" precedente</span><span class="sxs-lookup"><span data-stu-id="72038-128">In the previous "Hello World!"</span></span> <span data-ttu-id="72038-129">si trovava in una classe denominata `Hello`.</span><span class="sxs-lookup"><span data-stu-id="72038-129">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="72038-130">È possibile dichiarare il metodo `Main` in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="72038-130">You can declare the `Main` method in one of the following ways:</span></span>  
  
-   <span data-ttu-id="72038-131">Può restituire un valore `void`.</span><span class="sxs-lookup"><span data-stu-id="72038-131">It can return `void`.</span></span>  
  
     [!code-csharp[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   <span data-ttu-id="72038-132">Può restituire anche un valore intero.</span><span class="sxs-lookup"><span data-stu-id="72038-132">It can also return an integer.</span></span>  
  
     [!code-csharp[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   <span data-ttu-id="72038-133">Con entrambi i tipi restituiti, può accettare argomenti.</span><span class="sxs-lookup"><span data-stu-id="72038-133">With either of the return types, it can take arguments.</span></span>  
  
     [!code-csharp[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     <span data-ttu-id="72038-134">oppure</span><span class="sxs-lookup"><span data-stu-id="72038-134">-or-</span></span>  
  
     [!code-csharp[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 <span data-ttu-id="72038-135">Il parametro del metodo `Main`, `args`, è una matrice `string` che contiene gli argomenti della riga di comando usati per richiamare il programma.</span><span class="sxs-lookup"><span data-stu-id="72038-135">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="72038-136">A differenza di C++, la matrice non include il nome del file eseguibile con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="72038-136">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>  
  
 <span data-ttu-id="72038-137">Per altre informazioni sull'uso degli argomenti della riga di comando, vedere gli esempi in [Main() e argomenti della riga di comando](../../../csharp/programming-guide/main-and-command-args/index.md) e [Procedura: Creare e usare assembly dalla riga di comando](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="72038-137">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
 <span data-ttu-id="72038-138">La chiamata a <xref:System.Console.ReadKey%2A> alla fine del metodo `Main` evita che la finestra della console si chiuda prima che sia possibile leggere l'output quando si esegue il programma in modalità di debug, premendo F5.</span><span class="sxs-lookup"><span data-stu-id="72038-138">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>  
  
## <a name="input-and-output"></a><span data-ttu-id="72038-139">Input e output</span><span class="sxs-lookup"><span data-stu-id="72038-139">Input and Output</span></span>  
 <span data-ttu-id="72038-140">In genere i programmi C# usano i servizi di input/output offerti dalla libreria run-time di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72038-140">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="72038-141">L'istruzione `System.Console.WriteLine("Hello World!");` usa il metodo <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="72038-141">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="72038-142">Questo è uno dei metodi di output della classe <xref:System.Console> nella libreria di runtime.</span><span class="sxs-lookup"><span data-stu-id="72038-142">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="72038-143">Visualizza il parametro di tipo stringa sul flusso di output standard seguito da una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="72038-143">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="72038-144">Sono disponibili altri metodi <xref:System.Console> per diverse operazioni di input e output.</span><span class="sxs-lookup"><span data-stu-id="72038-144">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="72038-145">Se si include la direttiva `using System;` all'inizio del programma, è possibile usare direttamente le classi e i metodi <xref:System> senza specificarne il nome completo.</span><span class="sxs-lookup"><span data-stu-id="72038-145">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="72038-146">Ad esempio, è possibile chiamare `Console.WriteLine` anziché `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="72038-146">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-csharp[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 <span data-ttu-id="72038-147">Per altre informazioni sui metodi di input/output, vedere <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="72038-147">For more information about input/output methods, see <xref:System.IO>.</span></span>  
  
## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="72038-148">Esecuzione e compilazione da riga di comando</span><span class="sxs-lookup"><span data-stu-id="72038-148">Command-Line Compilation and Execution</span></span>  
 <span data-ttu-id="72038-149">È possibile compilare il programma "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="72038-149">You can compile the "Hello World!"</span></span> <span data-ttu-id="72038-150">usando la riga di comando invece dell'ambiente di sviluppo integrato (IDE, Integrated Development Environment) di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72038-150">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="72038-151">Per compilare ed eseguire codice a un prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="72038-151">To compile and run from a command prompt</span></span>  
  
1.  <span data-ttu-id="72038-152">Incollare il codice della procedura precedente in un editor di testo e salvare il file come file di testo.</span><span class="sxs-lookup"><span data-stu-id="72038-152">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="72038-153">Denominare il file `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="72038-153">Name the file `Hello.cs`.</span></span> <span data-ttu-id="72038-154">I file del codice sorgente di C# usano l'estensione `.cs`.</span><span class="sxs-lookup"><span data-stu-id="72038-154">C# source code files use the extension `.cs`.</span></span>  
  
2.  <span data-ttu-id="72038-155">Eseguire una delle procedure seguenti per aprire una finestra al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="72038-155">Perform one of the following steps to open a command-prompt window:</span></span>  
  
    -   <span data-ttu-id="72038-156">In Windows 10 nel menu **Start** cercare `Developer Command Prompt` e toccare o selezionare **Prompt dei comandi per gli sviluppatori per VS2017**.</span><span class="sxs-lookup"><span data-stu-id="72038-156">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="72038-157">Viene visualizzata una finestra del prompt dei comandi per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="72038-157">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="72038-158">In Windows 7 aprire il menu **Start**, espandere la cartella della versione corrente di Visual Studio, aprire il menu di scelta rapida per **Strumenti di Visual Studio** e selezionare **Prompt dei comandi per gli sviluppatori per VS2017**.</span><span class="sxs-lookup"><span data-stu-id="72038-158">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="72038-159">Viene visualizzata una finestra del prompt dei comandi per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="72038-159">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="72038-160">Abilitare le compilazioni da riga di comando da una finestra del prompt dei comandi standard.</span><span class="sxs-lookup"><span data-stu-id="72038-160">Enable command-line builds from a standard Command Prompt window.</span></span>  
  
         <span data-ttu-id="72038-161">Vedere [Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="72038-161">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>  
  
3.  <span data-ttu-id="72038-162">Nella finestra del prompt dei comandi passare alla cartella che contiene il file `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="72038-162">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>  
  
4.  <span data-ttu-id="72038-163">Immettere il comando seguente per compilare `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="72038-163">Enter the following command to compile `Hello.cs`.</span></span>  
  
     `csc Hello.cs`  
  
     <span data-ttu-id="72038-164">Se il programma non presenta errori di compilazione, viene creato un file eseguibile denominato `Hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="72038-164">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>  
  
5.  <span data-ttu-id="72038-165">Nella finestra del prompt dei comandi immettere il comando seguente per eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="72038-165">In the command-prompt window, enter the following command to run the program:</span></span>  
  
     `Hello`  
  
 <span data-ttu-id="72038-166">Per altre informazioni sul compilatore C# e le relative opzioni, vedere [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) (Opzioni del compilatore C#).</span><span class="sxs-lookup"><span data-stu-id="72038-166">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="72038-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72038-167">See Also</span></span>

- [<span data-ttu-id="72038-168">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="72038-168">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="72038-169">Contenuto di un programma C#</span><span class="sxs-lookup"><span data-stu-id="72038-169">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
- [<span data-ttu-id="72038-170">Stringhe</span><span class="sxs-lookup"><span data-stu-id="72038-170">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
- [<span data-ttu-id="72038-171">\<Applicazioni di esempio di C#</span><span class="sxs-lookup"><span data-stu-id="72038-171">\<paveover>C# Sample Applications</span></span>](https://msdn.microsoft.com/library/9a9d7aaa-51d3-4224-b564-95409b0f3e15)  
- [<span data-ttu-id="72038-172">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="72038-172">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="72038-173">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="72038-173">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [<span data-ttu-id="72038-174">Guida introduttiva a Visual C# e Visual Basic</span><span class="sxs-lookup"><span data-stu-id="72038-174">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
