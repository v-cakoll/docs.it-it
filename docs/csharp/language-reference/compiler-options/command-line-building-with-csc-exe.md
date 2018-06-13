---
title: Compilazione dalla riga di comando con csc.exe
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: 3cd49a17991f3d7606b0364a83be2b2e30ba0cce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218059"
---
# <a name="command-line-build-with-cscexe"></a><span data-ttu-id="d6058-102">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="d6058-102">Command-line build with csc.exe</span></span>
<span data-ttu-id="d6058-103">È possibile richiamare il compilatore C# digitando il nome del relativo file eseguibile (*csc.exe*) da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d6058-103">You can invoke the C# compiler by typing the name of its executable file (*csc.exe*) at a command prompt.</span></span>

<span data-ttu-id="d6058-104">Se si usa la finestra **Prompt dei comandi per gli sviluppatori per Visual Studio**, tutte le variabili di ambiente necessarie sono impostate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d6058-104">If you use the **Developer Command Prompt for Visual Studio** window, all the necessary environment variables are set for you.</span></span> <span data-ttu-id="d6058-105">Per informazioni su come accedere a questo strumento, vedere [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) (Prompt dei comandi per gli sviluppatori per Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="d6058-105">For information on how to access this tool, see the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) topic.</span></span> 

<span data-ttu-id="d6058-106">Se si usa una finestra del prompt dei comandi standard, è necessario modificare il percorso prima di poter richiamare *csc.exe* da qualsiasi sottodirectory del computer.</span><span class="sxs-lookup"><span data-stu-id="d6058-106">If you use a standard Command Prompt window, you must adjust your path before you can invoke *csc.exe* from any subdirectory on your computer.</span></span> <span data-ttu-id="d6058-107">Si deve anche eseguire *vsvars32.bat* per impostare le variabili di ambiente necessarie per supportare le compilazioni da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d6058-107">You also must run *vsvars32.bat* to set the appropriate environment variables to support command-line builds.</span></span> <span data-ttu-id="d6058-108">Per altre informazioni su *vsvars32.bat*, incluse istruzioni per trovare ed eseguire il file, vedere [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="d6058-108">For more information about *vsvars32.bat*, including instructions for how to find and run it, see [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

<span data-ttu-id="d6058-109">Se nel computer in uso è disponibile solo [!INCLUDE[winsdklong](~/includes/winsdklong-md.md)], è possibile usare il compilatore C# al **Prompt dei comandi di SDK** che viene visualizzato dall'opzione di menu **Microsoft .NET Framework SDK**.</span><span class="sxs-lookup"><span data-stu-id="d6058-109">If you're working on a computer that has only the [!INCLUDE[winsdklong](~/includes/winsdklong-md.md)], you can use the C# compiler at the **SDK Command Prompt**, which you open from the **Microsoft .NET Framework SDK** menu option.</span></span>

<span data-ttu-id="d6058-110">È inoltre possibile utilizzare MSBuild per compilare programmi C# a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d6058-110">You can also use MSBuild to build C# programs programmatically.</span></span> <span data-ttu-id="d6058-111">Per altre informazioni, vedere [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="d6058-111">For more information, see [MSBuild](/visualstudio/msbuild/msbuild).</span></span>

<span data-ttu-id="d6058-112">Il file eseguibile *csc.exe* si trova in genere nella cartella Microsoft.NET\Framework\\*\<versione* della directory *Windows*.</span><span class="sxs-lookup"><span data-stu-id="d6058-112">The *csc.exe* executable file usually is located in the Microsoft.NET\Framework\\*\<Version>* folder under the *Windows* directory.</span></span> <span data-ttu-id="d6058-113">La posizione del file può variare in base all'esatta configurazione di un determinato computer.</span><span class="sxs-lookup"><span data-stu-id="d6058-113">Its location might vary depending on the exact configuration of a particular computer.</span></span> <span data-ttu-id="d6058-114">Se nel computer sono installate più versioni di .NET Framework, saranno disponibili più versioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="d6058-114">If more than one version of the .NET Framework is installed on your computer, you'll find multiple versions of this file.</span></span> <span data-ttu-id="d6058-115">Per altre informazioni su queste installazioni, vedere [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md) (Procedura: Determinare le versioni di .NET Framework installate).</span><span class="sxs-lookup"><span data-stu-id="d6058-115">For more information about such installations, see [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

> [!TIP]
>  <span data-ttu-id="d6058-116">Quando si compila un progetto usando l'IDE di Visual Studio, è possibile visualizzare il comando **csc** e le relative opzioni del compilatore associate nella finestra **Output**.</span><span class="sxs-lookup"><span data-stu-id="d6058-116">When you build a project by using the Visual Studio IDE, you can display the **csc** command and its associated compiler options in the **Output** window.</span></span> <span data-ttu-id="d6058-117">Per visualizzare queste informazioni, seguire le istruzioni in [Procedura: Visualizzare, salvare e configurare file di log di compilazione](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) per impostare il livello di dettaglio dei dati di log su **Normale** o **Dettagliato**.</span><span class="sxs-lookup"><span data-stu-id="d6058-117">To display this information, follow the instructions in [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) to change the verbosity level of the log data to **Normal** or **Detailed**.</span></span> <span data-ttu-id="d6058-118">Al termine della ricompilazione del progetto, nella finestra **Output** cercare **csc** per trovare la chiamata del compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="d6058-118">After you rebuild your project, search the **Output** window for **csc** to find the invocation of the C# compiler.</span></span>

 <span data-ttu-id="d6058-119">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="d6058-119">**In this topic**</span></span>

- [<span data-ttu-id="d6058-120">Regole per la sintassi della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d6058-120">Rules for command-line syntax</span></span>](#-rules-for-command-line-syntax-for-the-c-compiler)

- [<span data-ttu-id="d6058-121">Righe di comando di esempio</span><span class="sxs-lookup"><span data-stu-id="d6058-121">Sample command lines</span></span>](#sample-command-lines-for-the-c-compiler)

- [<span data-ttu-id="d6058-122">Differenze tra l'output del compilatore C# e l'output del compilatore C++</span><span class="sxs-lookup"><span data-stu-id="d6058-122">Differences between C# compiler and C++ compiler output</span></span>](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a><span data-ttu-id="d6058-123">Regole per la sintassi della riga di comando per il compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d6058-123">Rules for command-line syntax for the C# compiler</span></span>

<span data-ttu-id="d6058-124">Il compilatore C# usa le regole seguenti per interpretare gli argomenti visualizzati nella riga di comando del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="d6058-124">The C# compiler uses the following rules when it interprets arguments given on the operating system command line:</span></span>

- <span data-ttu-id="d6058-125">Gli argomenti sono delimitati da spazi vuoti, ovvero da uno spazio o da una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="d6058-125">Arguments are delimited by white space, which is either a space or a tab.</span></span>

- <span data-ttu-id="d6058-126">L'accento circonflesso (^) non viene riconosciuto come carattere di escape o delimitatore.</span><span class="sxs-lookup"><span data-stu-id="d6058-126">The caret character (^) is not recognized as an escape character or delimiter.</span></span> <span data-ttu-id="d6058-127">Il carattere viene gestito dal parser della riga di comando nel sistema operativo prima di essere passato alla matrice `argv` del programma.</span><span class="sxs-lookup"><span data-stu-id="d6058-127">The character is handled by the command-line parser in the operating system before it's passed to the `argv` array in the program.</span></span>

- <span data-ttu-id="d6058-128">Una stringa racchiusa tra virgolette doppie ("string") viene interpretata come argomento singolo, indipendentemente dalla presenza di spazi al suo interno.</span><span class="sxs-lookup"><span data-stu-id="d6058-128">A string enclosed in double quotation marks ("string") is interpreted as a single argument, regardless of white space that is contained within.</span></span> <span data-ttu-id="d6058-129">Una stringa tra virgolette può essere incorporata in un argomento.</span><span class="sxs-lookup"><span data-stu-id="d6058-129">A quoted string can be embedded in an argument.</span></span>

- <span data-ttu-id="d6058-130">Le virgolette doppie precedute da una barra rovesciata (\\") vengono interpretate come carattere letterale virgolette doppie (").</span><span class="sxs-lookup"><span data-stu-id="d6058-130">A double quotation mark preceded by a backslash (\\") is interpreted as a literal double quotation mark character (").</span></span>

- <span data-ttu-id="d6058-131">Le barre rovesciate vengono interpretate letteralmente, a meno che non precedano virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="d6058-131">Backslashes are interpreted literally, unless they immediately precede a double quotation mark.</span></span>

- <span data-ttu-id="d6058-132">Se un numero pari di barre rovesciate è seguito da virgolette doppie, viene inserita solo una barra rovesciata nella matrice `argv` per ogni coppia di barre rovesciate e le virgolette doppie vengono interpretate come delimitatore di stringa.</span><span class="sxs-lookup"><span data-stu-id="d6058-132">If an even number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is interpreted as a string delimiter.</span></span>

- <span data-ttu-id="d6058-133">Se un numero dispari di barre rovesciate è seguito da virgolette doppie, viene inserita solo una barra rovesciata nella matrice `argv` per ogni coppia di barre rovesciate e le virgolette doppie vengono "ignorate" dalla barra rovesciata rimanente.</span><span class="sxs-lookup"><span data-stu-id="d6058-133">If an odd number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is "escaped" by the remaining backslash.</span></span> <span data-ttu-id="d6058-134">Questo determina l'aggiunta di un valore letterale virgolette doppie (") in `argv`.</span><span class="sxs-lookup"><span data-stu-id="d6058-134">This causes a literal double quotation mark (") to be added in `argv`.</span></span>

## <a name="sample-command-lines-for-the-c-compiler"></a><span data-ttu-id="d6058-135">Righe di comando di esempio per il compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d6058-135">Sample command lines for the C# compiler</span></span>

- <span data-ttu-id="d6058-136">Compila *File.cs* e crea *File.exe*:</span><span class="sxs-lookup"><span data-stu-id="d6058-136">Compiles *File.cs* producing *File.exe*:</span></span>

```console
csc File.cs 
```

- <span data-ttu-id="d6058-137">Compila *File.cs* e crea *File.dll*:</span><span class="sxs-lookup"><span data-stu-id="d6058-137">Compiles *File.cs* producing *File.dll*:</span></span>

```console
csc -target:library File.cs
```

- <span data-ttu-id="d6058-138">Compila *File.cs* e crea *My.exe*:</span><span class="sxs-lookup"><span data-stu-id="d6058-138">Compiles *File.cs* and creates *My.exe*:</span></span>

```console
csc -out:My.exe File.cs
```

- <span data-ttu-id="d6058-139">Compila tutti i file C# della directory corrente con le ottimizzazioni attivate e definisce il simbolo DEBUG.</span><span class="sxs-lookup"><span data-stu-id="d6058-139">Compiles all the C# files in the current directory with optimizations enabled and defines the DEBUG symbol.</span></span> <span data-ttu-id="d6058-140">L'output è il *File2.exe*:</span><span class="sxs-lookup"><span data-stu-id="d6058-140">The output is *File2.exe*:</span></span>

```console
csc -define:DEBUG -optimize -out:File2.exe *.cs
```

- <span data-ttu-id="d6058-141">Compila tutti i file C# della directory corrente generando una versione di debug del file *File2.dll*.</span><span class="sxs-lookup"><span data-stu-id="d6058-141">Compiles all the C# files in the current directory producing a debug version of *File2.dll*.</span></span> <span data-ttu-id="d6058-142">Non viene visualizzato nessun logo e nessun avviso:</span><span class="sxs-lookup"><span data-stu-id="d6058-142">No logo and no warnings are displayed:</span></span>

```console
csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
```

- <span data-ttu-id="d6058-143">Compila tutti i file C# della directory corrente creando un file *Something.xyz* (una DLL):</span><span class="sxs-lookup"><span data-stu-id="d6058-143">Compiles all the C# files in the current directory to *Something.xyz* (a DLL):</span></span>

```console
csc -target:library -out:Something.xyz *.cs
```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a><span data-ttu-id="d6058-144">Differenze tra output del compilatore C# e output del compilatore C++</span><span class="sxs-lookup"><span data-stu-id="d6058-144">Differences between C# compiler and C++ compiler output</span></span>
<span data-ttu-id="d6058-145">Dopo il richiamo del compilatore C# non viene creato alcun file oggetto (*.obj*). I file di output vengono creati direttamente.</span><span class="sxs-lookup"><span data-stu-id="d6058-145">There are no object (*.obj*) files created as a result of invoking the C# compiler; output files are created directly.</span></span> <span data-ttu-id="d6058-146">Di conseguenza il compilatore C# non richiede un linker.</span><span class="sxs-lookup"><span data-stu-id="d6058-146">As a result of this, the C# compiler does not need a linker.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6058-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6058-147">See also</span></span>
 [<span data-ttu-id="d6058-148">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d6058-148">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="d6058-149">Opzioni del compilatore C# in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="d6058-149">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [<span data-ttu-id="d6058-150">Opzioni del compilatore C# elencate per categoria</span><span class="sxs-lookup"><span data-stu-id="d6058-150">C# Compiler Options Listed by Category</span></span>](../../../csharp/language-reference/compiler-options/listed-by-category.md)  
 [<span data-ttu-id="d6058-151">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d6058-151">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="d6058-152">Argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d6058-152">Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
 [<span data-ttu-id="d6058-153">Procedura: Visualizzare gli argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="d6058-153">How to: Display Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [<span data-ttu-id="d6058-154">Procedura: Accedere agli argomenti della riga di comando usando foreach</span><span class="sxs-lookup"><span data-stu-id="d6058-154">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [<span data-ttu-id="d6058-155">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="d6058-155">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
