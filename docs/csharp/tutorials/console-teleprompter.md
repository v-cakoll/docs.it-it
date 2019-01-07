---
title: Applicazione console
description: Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.
ms.date: 03/06/2017
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: dfd8124eb79690286e5cd876de57394a4d741328
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058399"
---
# <a name="console-application"></a><span data-ttu-id="671bb-103">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="671bb-103">Console Application</span></span>

<span data-ttu-id="671bb-104">Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="671bb-104">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="671bb-105">Verranno affrontati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="671bb-105">You’ll learn:</span></span>

- <span data-ttu-id="671bb-106">Nozioni di base sull'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="671bb-106">The basics of the .NET Core Command Line Interface (CLI)</span></span>
- <span data-ttu-id="671bb-107">Struttura di un'applicazione console in C#</span><span class="sxs-lookup"><span data-stu-id="671bb-107">The structure of a C# Console Application</span></span>
- <span data-ttu-id="671bb-108">Input/output della console</span><span class="sxs-lookup"><span data-stu-id="671bb-108">Console I/O</span></span>
- <span data-ttu-id="671bb-109">Nozioni di base sulle API di I/O dei file in .NET</span><span class="sxs-lookup"><span data-stu-id="671bb-109">The basics of File I/O APIs in .NET</span></span>
- <span data-ttu-id="671bb-110">Nozioni di base sul modello di programmazione asincrona delle attività in .NET</span><span class="sxs-lookup"><span data-stu-id="671bb-110">The basics of the Task-based Asynchronous Programming in .NET</span></span>

<span data-ttu-id="671bb-111">Verrà creata un'applicazione in grado di leggere un file di testo e restituire il contenuto del file alla console.</span><span class="sxs-lookup"><span data-stu-id="671bb-111">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="671bb-112">La velocità di riproduzione dell'output della console verrà quindi configurata in modo da consentirne la lettura ad alta voce.</span><span class="sxs-lookup"><span data-stu-id="671bb-112">The output to the console is paced to match reading it aloud.</span></span> <span data-ttu-id="671bb-113">È possibile aumentare o diminuire la velocità premendo il tasto < (minore di) o > (maggiore di).</span><span class="sxs-lookup"><span data-stu-id="671bb-113">You can speed up or slow down the pace by pressing the ‘<’ (less than) or ‘>’ (greater than) keys.</span></span>

<span data-ttu-id="671bb-114">In questa esercitazione verranno create anche</span><span class="sxs-lookup"><span data-stu-id="671bb-114">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="671bb-115">numerose funzionalità.</span><span class="sxs-lookup"><span data-stu-id="671bb-115">Let’s build them one by one.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="671bb-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="671bb-116">Prerequisites</span></span>

<span data-ttu-id="671bb-117">È necessario configurare il computer per l'esecuzione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="671bb-117">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="671bb-118">Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="671bb-118">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="671bb-119">Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="671bb-119">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="671bb-120">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="671bb-120">You’ll need to install your favorite code editor.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="671bb-121">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="671bb-121">Create the Application</span></span>

<span data-ttu-id="671bb-122">Il primo passaggio consiste nel creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="671bb-122">The first step is to create a new application.</span></span> <span data-ttu-id="671bb-123">Aprire un prompt dei comandi e creare una nuova directory per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="671bb-123">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="671bb-124">impostandola come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="671bb-124">Make that the current directory.</span></span> <span data-ttu-id="671bb-125">Digitare il comando `dotnet new console` al prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="671bb-125">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="671bb-126">Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="671bb-126">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="671bb-127">Prima di iniziare ad apportare modifiche, è opportuno ripercorrere i passaggi necessari per eseguire l'applicazione Hello World semplice.</span><span class="sxs-lookup"><span data-stu-id="671bb-127">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="671bb-128">Dopo aver creato l'applicazione, digitare `dotnet restore` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="671bb-128">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="671bb-129">Questo comando esegue il processo di ripristino dei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="671bb-129">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="671bb-130">Lo strumento NuGet consente di gestire pacchetti .NET.</span><span class="sxs-lookup"><span data-stu-id="671bb-130">NuGet is a .NET package manager.</span></span> <span data-ttu-id="671bb-131">Questo comando scarica eventuali dipendenze mancanti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="671bb-131">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="671bb-132">Poiché si tratta di un nuovo progetto, non è ancora presente alcuna dipendenza e con la prima esecuzione verrà quindi scaricato .NET Core Framework.</span><span class="sxs-lookup"><span data-stu-id="671bb-132">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="671bb-133">Dopo questo passaggio iniziale, sarà sufficiente eseguire `dotnet restore` quando si aggiungono nuovi pacchetti dipendenti o si aggiorna la versione di una delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="671bb-133">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="671bb-134">Dopo aver ripristinato i pacchetti, eseguire `dotnet build`</span><span class="sxs-lookup"><span data-stu-id="671bb-134">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="671bb-135">per avviare il motore di compilazione e creare il file eseguibile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="671bb-135">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="671bb-136">Eseguire infine `dotnet run` per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="671bb-136">Finally, you execute `dotnet run` to run your application.</span></span>

<span data-ttu-id="671bb-137">Il codice dell'applicazione Hello World semplice è tutto contenuto in Program.cs.</span><span class="sxs-lookup"><span data-stu-id="671bb-137">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="671bb-138">Aprire il file con un editor di testo</span><span class="sxs-lookup"><span data-stu-id="671bb-138">Open that file with your favorite text editor.</span></span> <span data-ttu-id="671bb-139">per effettuare subito le prime modifiche.</span><span class="sxs-lookup"><span data-stu-id="671bb-139">We’re about to make our first changes.</span></span>
<span data-ttu-id="671bb-140">Nella parte iniziale del file è presente un'istruzione using:</span><span class="sxs-lookup"><span data-stu-id="671bb-140">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="671bb-141">Questa istruzione indica al compilatore che qualsiasi tipo dello spazio dei nomi `System` rientra nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="671bb-141">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="671bb-142">Come altri linguaggi orientati agli oggetti, anche C# ricorre agli spazi dei nomi per organizzare i tipi.</span><span class="sxs-lookup"><span data-stu-id="671bb-142">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="671bb-143">Il programma Hello World non è diverso.</span><span class="sxs-lookup"><span data-stu-id="671bb-143">This Hello World program is no different.</span></span> <span data-ttu-id="671bb-144">È possibile vedere che il programma è incluso nello spazio dei nomi con il nome basato sul nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="671bb-144">You can see that the program is enclosed in the namespace with the name based on the name of the current directory.</span></span> <span data-ttu-id="671bb-145">Per questa esercitazione, è necessario modificare il nome dello spazio dei nomi per `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="671bb-145">For this tutorial, let's change the name of the namespace to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="671bb-146">Lettura e restituzione del file</span><span class="sxs-lookup"><span data-stu-id="671bb-146">Reading and Echoing the File</span></span>

<span data-ttu-id="671bb-147">La prima funzionalità da aggiungere è la capacità di leggere un file di testo e visualizzare tutto il testo nella console.</span><span class="sxs-lookup"><span data-stu-id="671bb-147">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="671bb-148">Si aggiungerà innanzitutto un file di testo.</span><span class="sxs-lookup"><span data-stu-id="671bb-148">First, let’s add a text file.</span></span> <span data-ttu-id="671bb-149">Copiare il file [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) dal repository GitHub di questo [esempio](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) alla directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="671bb-149">Copy the [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="671bb-150">Questo file verrà usato come script per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="671bb-150">This will serve as the script for your application.</span></span> <span data-ttu-id="671bb-151">Per informazioni su come scaricare l'app di esempio per questo argomento, vedere le istruzioni nell'argomento [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="671bb-151">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="671bb-152">Aggiungere quindi il metodo seguente alla classe `Program` (immediatamente sotto il metodo `Main`):</span><span class="sxs-lookup"><span data-stu-id="671bb-152">Next, add the following method in your `Program` class (right below the `Main` method):</span></span>

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

<span data-ttu-id="671bb-153">Questo metodo usa tipi provenienti da due nuovi spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="671bb-153">This method uses types from two new namespaces.</span></span> <span data-ttu-id="671bb-154">Per eseguirne la compilazione è necessario aggiungere le due righe seguenti all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="671bb-154">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="671bb-155">L'interfaccia <xref:System.Collections.Generic.IEnumerable%601> è definita nello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="671bb-155">The <xref:System.Collections.Generic.IEnumerable%601> interface is defined in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="671bb-156">La classe <xref:System.IO.File> è definita nello spazio dei nomi <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="671bb-156">The <xref:System.IO.File> class is defined in the <xref:System.IO> namespace.</span></span>

<span data-ttu-id="671bb-157">Questo metodo è un tipo speciale di metodo C# denominato *metodo iteratore*.</span><span class="sxs-lookup"><span data-stu-id="671bb-157">This method is a special type of C# method called an *Iterator method*.</span></span> <span data-ttu-id="671bb-158">I metodi enumeratore restituiscono sequenze che vengono valutate in modo differito.</span><span class="sxs-lookup"><span data-stu-id="671bb-158">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="671bb-159">In altre parole, ogni elemento della sequenza viene generato nel momento in cui viene richiesto dal codice che utilizza la sequenza.</span><span class="sxs-lookup"><span data-stu-id="671bb-159">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="671bb-160">I metodi enumeratore contengono una o più istruzioni [`yield return`](../language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="671bb-160">Enumerator methods are methods that contain one or more [`yield return`](../language-reference/keywords/yield.md) statements.</span></span> <span data-ttu-id="671bb-161">L'oggetto restituito dal metodo `ReadFrom` contiene il codice per generare ogni elemento della sequenza.</span><span class="sxs-lookup"><span data-stu-id="671bb-161">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="671bb-162">In questo esempio, ciò consiste nella lettura della riga di testo successiva dal file di origine e nella restituzione della stringa.</span><span class="sxs-lookup"><span data-stu-id="671bb-162">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="671bb-163">Ogni volta che il codice chiamante richiede l'elemento successivo della sequenza, il codice legge la riga di testo successiva dal file e la restituisce.</span><span class="sxs-lookup"><span data-stu-id="671bb-163">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="671bb-164">Quando il file è stato letto completamente, la sequenza indica che non sono presenti altri elementi.</span><span class="sxs-lookup"><span data-stu-id="671bb-164">When the file is completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="671bb-165">Altri due elementi della sintassi C# possono risultare nuovi all'utente.</span><span class="sxs-lookup"><span data-stu-id="671bb-165">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="671bb-166">L'istruzione [`using`](../language-reference/keywords/using-statement.md) gestisce la pulizia delle risorse in questo metodo.</span><span class="sxs-lookup"><span data-stu-id="671bb-166">The [`using`](../language-reference/keywords/using-statement.md) statement in this method manages resource cleanup.</span></span> <span data-ttu-id="671bb-167">La variabile inizializzata nell'istruzione `using` (`reader`, in questo esempio) deve implementare l'interfaccia <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="671bb-167">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="671bb-168">Tale interfaccia definisce un singolo metodo, `Dispose`, che deve essere chiamato quando deve essere rilasciata la risorsa.</span><span class="sxs-lookup"><span data-stu-id="671bb-168">That interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="671bb-169">Il compilatore genera la chiamata quando l'esecuzione raggiunge la parentesi graffa di chiusura dell'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="671bb-169">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="671bb-170">Il codice generato dal compilatore assicura che la risorsa venga rilasciata anche se viene generata un'eccezione dal codice nel blocco definito tramite l'istruzione using.</span><span class="sxs-lookup"><span data-stu-id="671bb-170">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="671bb-171">La variabile `reader` viene definita tramite la parola chiave `var`.</span><span class="sxs-lookup"><span data-stu-id="671bb-171">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="671bb-172">[`var`](../language-reference/keywords/var.md) definisce una *variabile locale tipizzata in modo implicito*,</span><span class="sxs-lookup"><span data-stu-id="671bb-172">[`var`](../language-reference/keywords/var.md) defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="671bb-173">ovvero il tipo della variabile è determinato dal tipo in fase di compilazione dell'oggetto assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="671bb-173">That means the type of the variable is determined by the compile-time type of the object assigned to the variable.</span></span> <span data-ttu-id="671bb-174">In questo caso corrisponde al valore restituito dal metodo <xref:System.IO.File.OpenText(System.String)>, ovvero a un oggetto <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="671bb-174">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>

<span data-ttu-id="671bb-175">Si compilerà ora il codice per leggere il file nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="671bb-175">Now, let’s fill in the code to read the file in the `Main` method:</span></span>

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

<span data-ttu-id="671bb-176">Eseguire il programma, usando `dotnet run` in modo da poter visualizzare ogni riga visualizzata nella console.</span><span class="sxs-lookup"><span data-stu-id="671bb-176">Run the program (using `dotnet run`) and you can see every line printed out to the console.</span></span>

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="671bb-177">Aggiunta di ritardi e formattazione dell'output</span><span class="sxs-lookup"><span data-stu-id="671bb-177">Adding Delays and Formatting output</span></span>

<span data-ttu-id="671bb-178">Il testo restituito viene visualizzato troppo velocemente per potere essere letto a voce alta.</span><span class="sxs-lookup"><span data-stu-id="671bb-178">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="671bb-179">È quindi necessario aggiungere ritardi nell'output.</span><span class="sxs-lookup"><span data-stu-id="671bb-179">Now you need to add the delays in the output.</span></span> <span data-ttu-id="671bb-180">Si inizierà creando codice di base che consenta l'elaborazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="671bb-180">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="671bb-181">Questi primi passaggi dovranno tuttavia seguire alcuni anti-pattern,</span><span class="sxs-lookup"><span data-stu-id="671bb-181">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="671bb-182">evidenziati nei commenti mentre si aggiunge il codice, e il codice verrà aggiornato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="671bb-182">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="671bb-183">Questa sezione è articolata in due fasi.</span><span class="sxs-lookup"><span data-stu-id="671bb-183">There are two steps to this section.</span></span> <span data-ttu-id="671bb-184">Nella prima fase si aggiornerà il metodo iteratore in modo che restituisca singole parole anziché righe intere.</span><span class="sxs-lookup"><span data-stu-id="671bb-184">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="671bb-185">A questo scopo è necessario apportare le modifiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="671bb-185">That’s done with these modifications.</span></span> <span data-ttu-id="671bb-186">Sostituire la funzione `yield return line;` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="671bb-186">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="671bb-187">Sarà quindi necessario modificare il modo in cui vengono usate le righe del file e aggiungere un ritardo dopo la scrittura di ogni parola.</span><span class="sxs-lookup"><span data-stu-id="671bb-187">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="671bb-188">Sostituire l'istruzione `Console.WriteLine(line)` nel metodo `Main` con il blocco seguente:</span><span class="sxs-lookup"><span data-stu-id="671bb-188">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

<span data-ttu-id="671bb-189">La classe <xref:System.Threading.Tasks.Task> si trova nello spazio dei nomi <xref:System.Threading.Tasks> ed è quindi necessario aggiungere l'istruzione `using` all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="671bb-189">The <xref:System.Threading.Tasks.Task> class is in the <xref:System.Threading.Tasks> namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="671bb-190">Eseguire l'esempio e verificare l'output.</span><span class="sxs-lookup"><span data-stu-id="671bb-190">Run the sample, and check the output.</span></span> <span data-ttu-id="671bb-191">Ogni singola parola viene ora visualizzata, seguita da un ritardo di 200 ms.</span><span class="sxs-lookup"><span data-stu-id="671bb-191">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="671bb-192">L'output visualizzato mostra tuttavia alcuni problemi perché il file di testo di origine presenta più righe con oltre 80 caratteri senza interruzione di riga,</span><span class="sxs-lookup"><span data-stu-id="671bb-192">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="671bb-193">che possono risultare difficili da leggere durante lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="671bb-193">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="671bb-194">Questo problema è facile da risolvere.</span><span class="sxs-lookup"><span data-stu-id="671bb-194">That’s easy to fix.</span></span> <span data-ttu-id="671bb-195">Basta tenere traccia della durata di ogni riga e generare una nuova riga ogni volta che la lunghezza raggiunge una determinata soglia.</span><span class="sxs-lookup"><span data-stu-id="671bb-195">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="671bb-196">Dichiarare una variabile locale dopo la dichiarazione di `words` nel metodo `ReadFrom` che contiene la lunghezza di riga:</span><span class="sxs-lookup"><span data-stu-id="671bb-196">Declare a local variable after the declaration of `words` in the `ReadFrom` method that holds the line length:</span></span>

```csharp
var lineLength = 0;
```

<span data-ttu-id="671bb-197">Aggiungere quindi il codice seguente dopo l'istruzione `yield return word + " ";` (prima della parentesi graffa di chiusura):</span><span class="sxs-lookup"><span data-stu-id="671bb-197">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

<span data-ttu-id="671bb-198">Eseguire l'esempio. Sarà possibile ora leggere ad alta voce alla velocità prestabilita.</span><span class="sxs-lookup"><span data-stu-id="671bb-198">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="671bb-199">Attività asincrone</span><span class="sxs-lookup"><span data-stu-id="671bb-199">Async Tasks</span></span>

<span data-ttu-id="671bb-200">In questa fase finale si aggiungerà il codice per scrivere l'output in modo asincrono in un'attività e si eseguirà anche un'altra attività per leggere l'input dell'utente, nel caso in cui si voglia accelerare o rallentare la visualizzazione del testo o arrestarla del tutto.</span><span class="sxs-lookup"><span data-stu-id="671bb-200">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display, or stop the text display altogether.</span></span> <span data-ttu-id="671bb-201">Sarà necessario eseguire alcuni passaggi ma, al termine, saranno implementati tutti gli aggiornamenti necessari.</span><span class="sxs-lookup"><span data-stu-id="671bb-201">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="671bb-202">Il primo passaggio consiste nel creare un metodo di restituzione asincrono <xref:System.Threading.Tasks.Task> che rappresenta il codice creato finora per leggere e visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="671bb-202">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="671bb-203">Aggiungere questo metodo alla classe `Program` (tratto dal corpo del metodo `Main`):</span><span class="sxs-lookup"><span data-stu-id="671bb-203">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="671bb-204">Si noteranno due modifiche.</span><span class="sxs-lookup"><span data-stu-id="671bb-204">You’ll notice two changes.</span></span> <span data-ttu-id="671bb-205">Nel corpo del metodo, anziché chiamare <xref:System.Threading.Tasks.Task.Wait> per attendere in modo sincrono il completamento di un'attività, questa versione usa la parola chiave `await`.</span><span class="sxs-lookup"><span data-stu-id="671bb-205">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="671bb-206">A questo scopo, è necessario aggiungere il modificatore `async` alla firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="671bb-206">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="671bb-207">Il metodo restituisce `Task`.</span><span class="sxs-lookup"><span data-stu-id="671bb-207">This method returns a `Task`.</span></span> <span data-ttu-id="671bb-208">Osservare inoltre come non siano presenti istruzioni return che restituiscono un oggetto `Task`.</span><span class="sxs-lookup"><span data-stu-id="671bb-208">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="671bb-209">L'oggetto `Task`, infatti, viene creato dal codice che il compilatore genera quando si usa l'operatore `await`.</span><span class="sxs-lookup"><span data-stu-id="671bb-209">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="671bb-210">È possibile immaginare quindi che il metodo restituisca l'oggetto quando raggiunge la parola chiave `await`.</span><span class="sxs-lookup"><span data-stu-id="671bb-210">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="671bb-211">L'oggetto `Task` restituito indica che il lavoro non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="671bb-211">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="671bb-212">Il metodo riprende l'esecuzione quando viene completata l'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="671bb-212">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="671bb-213">Al termine dell'esecuzione, l'oggetto `Task` restituito indica che il lavoro è stato completato.</span><span class="sxs-lookup"><span data-stu-id="671bb-213">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="671bb-214">Il codice chiamante può monitorare l'oggetto `Task` restituito per determinare quando è stato completato.</span><span class="sxs-lookup"><span data-stu-id="671bb-214">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="671bb-215">È possibile chiamare questo nuovo metodo nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="671bb-215">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="671bb-216">Di seguito, nel metodo `Main`, il codice attende in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="671bb-216">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="671bb-217">Quando possibile, è consigliabile usare l'operatore `await` anziché attendere in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="671bb-217">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="671bb-218">Nel metodo `Main` di un'applicazione console, tuttavia, non è possibile usare l'operatore `await`.</span><span class="sxs-lookup"><span data-stu-id="671bb-218">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="671bb-219">Questo comporterebbe infatti la chiusura dell'applicazione prima che siano state completate tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="671bb-219">That would result in the application exiting before all tasks have completed.</span></span>

> [!NOTE]
> <span data-ttu-id="671bb-220">Se si usa C# 7.1 o versione successiva è possibile creare applicazioni console con il metodo [ `async` `Main` ](../whats-new/csharp-7-1.md#async-main).</span><span class="sxs-lookup"><span data-stu-id="671bb-220">If you use C# 7.1 or later, you can create console applications with [`async` `Main` method](../whats-new/csharp-7-1.md#async-main).</span></span>

<span data-ttu-id="671bb-221">È ora necessario scrivere il secondo metodo asincrono per leggere dalla console e verificare la presenza del tasto "<" (minore di), ">" (maggiore di), "X" o "x".</span><span class="sxs-lookup"><span data-stu-id="671bb-221">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ (less than), ‘>’ (greater than) and ‘X’ or ‘x’ keys.</span></span> <span data-ttu-id="671bb-222">Di seguito è illustrato il metodo da aggiungere per questa attività.</span><span class="sxs-lookup"><span data-stu-id="671bb-222">Here’s the method you add for that task:</span></span>

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
            {
                break;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="671bb-223">Si crea in questo modo un'espressione lambda per rappresentare un delegato <xref:System.Action> che legge un carattere dalla console e modifica una variabile locale che rappresenta il ritardo quando l'utente preme il tasto < (minore di) o > (maggiore di).</span><span class="sxs-lookup"><span data-stu-id="671bb-223">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ (less than) or ‘>’ (greater than) keys.</span></span> <span data-ttu-id="671bb-224">Il metodo delegato termina quando l'utente preme il tasto "X" o "x", che permette all'utente di arrestare la visualizzazione del testo in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="671bb-224">The delegate method finishes when user presses the ‘X’ or ‘x’  keys, which allow the user to stop the text display at any time.</span></span>
<span data-ttu-id="671bb-225">Questo metodo usa <xref:System.Console.ReadKey> per bloccare l'operazione e attendere che l'utente prema un tasto.</span><span class="sxs-lookup"><span data-stu-id="671bb-225">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="671bb-226">Per completare questa funzionalità, è necessario creare un nuovo metodo di restituzione `async Task` in grado di avviare entrambe le attività (`GetInput` e `ShowTeleprompter`) e gestire i dati condivisi tra di esse.</span><span class="sxs-lookup"><span data-stu-id="671bb-226">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>

<span data-ttu-id="671bb-227">A questo punto, occorre creare una classe in grado di gestire i dati condivisi tra le due attività.</span><span class="sxs-lookup"><span data-stu-id="671bb-227">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="671bb-228">Questa classe contiene due proprietà pubbliche: il ritardo e un flag `Done` per indicare che il file è stato letto interamente:</span><span class="sxs-lookup"><span data-stu-id="671bb-228">This class contains two public properties: the delay, and a flag `Done` to indicate that the file has been completely read:</span></span>

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }

        public bool Done { get; private set; }

        public void SetDone()
        {
            Done = true;
        }
    }
}
```

<span data-ttu-id="671bb-229">Inserire la classe in un nuovo file e includerla nello spazio dei nomi `TeleprompterConsole`, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="671bb-229">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="671bb-230">Sarà inoltre necessario aggiungere un'istruzione `using static` in modo da poter fare riferimento ai metodi `Min` e `Max` anche senza conoscere il nome dello spazio dei nomi o della classe di inclusione.</span><span class="sxs-lookup"><span data-stu-id="671bb-230">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` methods without the enclosing class or namespace names.</span></span> <span data-ttu-id="671bb-231">Un'istruzione [`using static`](../language-reference/keywords/using-static.md) importa i metodi da una classe.</span><span class="sxs-lookup"><span data-stu-id="671bb-231">A [`using static`](../language-reference/keywords/using-static.md) statement imports the methods from one class.</span></span> <span data-ttu-id="671bb-232">Questo comportamento è in contrasto con le istruzioni `using` usate finora che hanno importato tutte le classi da uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="671bb-232">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="671bb-233">L'altra nuova funzionalità di linguaggio consiste nell'istruzione [`lock`](../language-reference/keywords/lock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="671bb-233">The other language feature that’s new is the [`lock`](../language-reference/keywords/lock-statement.md) statement.</span></span> <span data-ttu-id="671bb-234">Questa istruzione garantisce che in un determinato momento possa essere presente un solo thread nel codice.</span><span class="sxs-lookup"><span data-stu-id="671bb-234">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="671bb-235">Se un thread si trova nella sezione bloccata, gli altri thread devono attendere che il primo esca da tale sezione.</span><span class="sxs-lookup"><span data-stu-id="671bb-235">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="671bb-236">L'istruzione `lock` usa un oggetto che protegge la sezione bloccata.</span><span class="sxs-lookup"><span data-stu-id="671bb-236">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="671bb-237">Questa classe segue un linguaggio standard per bloccare un oggetto privato nella classe.</span><span class="sxs-lookup"><span data-stu-id="671bb-237">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="671bb-238">Sarà quindi necessario aggiornare i metodi `ShowTeleprompter` e `GetInput` affinché usino il nuovo oggetto `config`.</span><span class="sxs-lookup"><span data-stu-id="671bb-238">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="671bb-239">Scrivere un ultimo metodo `Task` di restituzione dell'oggetto `async`, in grado di avviare entrambe le attività e chiudere la prima attività nel momento in cui viene completata:</span><span class="sxs-lookup"><span data-stu-id="671bb-239">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="671bb-240">Il nuovo metodo qui è la chiamata <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>.</span><span class="sxs-lookup"><span data-stu-id="671bb-240">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="671bb-241">In questo modo si crea un oggetto `Task` che termina non appena viene completata un'attività inclusa nel relativo elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="671bb-241">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="671bb-242">È ora necessario aggiornare i metodi `ShowTeleprompter` e `GetInput` affinché usino l'oggetto `config` per il ritardo:</span><span class="sxs-lookup"><span data-stu-id="671bb-242">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
            else if (key.KeyChar == 'X' || key.KeyChar == 'x')
                config.SetDone();
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="671bb-243">Questa nuova versione di `ShowTeleprompter` chiama un nuovo metodo nella classe `TeleprompterConfig`.</span><span class="sxs-lookup"><span data-stu-id="671bb-243">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="671bb-244">A questo punto, è necessario aggiornare `Main` affinché chiami `RunTeleprompter` anziché `ShowTeleprompter`:</span><span class="sxs-lookup"><span data-stu-id="671bb-244">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a><span data-ttu-id="671bb-245">Conclusione</span><span class="sxs-lookup"><span data-stu-id="671bb-245">Conclusion</span></span>

<span data-ttu-id="671bb-246">In questa esercitazione sono state illustrate diverse funzionalità del linguaggio C# e presentate le librerie .NET Core correlate all'uso di applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="671bb-246">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="671bb-247">A partire da queste informazioni è possibile approfondire la conoscenza del linguaggio e delle classi presentate nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="671bb-247">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="671bb-248">Sono state inoltre fornite nozioni di base sulle operazioni di input/output del file e della console e sull'uso bloccante e non bloccante della programmazione asincrona basata sulle attività, è stata offerta una panoramica del linguaggio C# ed è stata descritta l'organizzazione dei programmi C# e degli strumenti e dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="671bb-248">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task-based asynchronous programming, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>

<span data-ttu-id="671bb-249">Per altre informazioni su I/O di file, consultare l'argomento [I/O di file e di flussi](../../standard/io/index.md).</span><span class="sxs-lookup"><span data-stu-id="671bb-249">For more information about File I/O, see the [File and Stream I/O](../../standard/io/index.md) topic.</span></span> <span data-ttu-id="671bb-250">Per altre informazioni sul modello di programmazione asincrono usato in questa esercitazione, consultare l'argomento [Programmazione asincrona basata su attività](../..//standard/parallel-programming/task-based-asynchronous-programming.md) e l'argomento [Programmazione asincrona](../async.md).</span><span class="sxs-lookup"><span data-stu-id="671bb-250">For more information about asynchronous programming model used in this tutorial, see the [Task-based Asynchronous Programming](../..//standard/parallel-programming/task-based-asynchronous-programming.md) topic and the [Asynchronous programming](../async.md) topic.</span></span>
