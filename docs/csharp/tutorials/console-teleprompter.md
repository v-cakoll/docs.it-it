---
title: Applicazione console
description: "Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: 08dab8e7b210ab5159645563cd381d50145d764b
ms.sourcegitcommit: be7862cac09066bc505586cbf071d0e2c8fb1508
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2017
---
# <a name="console-application"></a><span data-ttu-id="f35db-104">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="f35db-104">Console Application</span></span>

## <a name="introduction"></a><span data-ttu-id="f35db-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="f35db-105">Introduction</span></span>
<span data-ttu-id="f35db-106">Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="f35db-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="f35db-107">Verranno affrontati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f35db-107">You’ll learn:</span></span>
*   <span data-ttu-id="f35db-108">Nozioni di base sull'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f35db-108">The basics of the .NET Core Command Line Interface (CLI)</span></span>
*   <span data-ttu-id="f35db-109">Struttura di un'applicazione console in C#</span><span class="sxs-lookup"><span data-stu-id="f35db-109">The structure of a C# Console Application</span></span>
*   <span data-ttu-id="f35db-110">Input/output della console</span><span class="sxs-lookup"><span data-stu-id="f35db-110">Console I/O</span></span>
*   <span data-ttu-id="f35db-111">Nozioni di base sulle API di I/O dei file in .NET Core</span><span class="sxs-lookup"><span data-stu-id="f35db-111">The basics of File I/O APIs in .NET Core</span></span>
*   <span data-ttu-id="f35db-112">Nozioni di base sul modello di programmazione asincrona delle attività in .NET Core</span><span class="sxs-lookup"><span data-stu-id="f35db-112">The basics of the Task Asynchronous Programming Model in .NET Core</span></span>

<span data-ttu-id="f35db-113">Verrà creata un'applicazione in grado di leggere un file di testo e restituire il contenuto del file alla console.</span><span class="sxs-lookup"><span data-stu-id="f35db-113">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="f35db-114">La velocità di riproduzione dell'output della console verrà quindi configurata in modo da consentirne la lettura ad alta voce.</span><span class="sxs-lookup"><span data-stu-id="f35db-114">The output to the console will be paced to match reading it aloud.</span></span> <span data-ttu-id="f35db-115">È possibile aumentare o diminuire la velocità premendo il tasto < o >.</span><span class="sxs-lookup"><span data-stu-id="f35db-115">You can speed up or slow down the pace by pressing the ‘<’ or ‘>’ keys.</span></span>

<span data-ttu-id="f35db-116">In questa esercitazione verranno create anche</span><span class="sxs-lookup"><span data-stu-id="f35db-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="f35db-117">numerose funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f35db-117">Let’s build them one by one.</span></span> 
## <a name="prerequisites"></a><span data-ttu-id="f35db-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f35db-118">Prerequisites</span></span>
<span data-ttu-id="f35db-119">È necessario configurare il computer per l'esecuzione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f35db-119">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="f35db-120">Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="f35db-120">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="f35db-121">Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="f35db-121">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="f35db-122">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="f35db-122">You’ll need to install your favorite code editor.</span></span> 
## <a name="create-the-application"></a><span data-ttu-id="f35db-123">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="f35db-123">Create the Application</span></span>
<span data-ttu-id="f35db-124">Il primo passaggio consiste nel creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="f35db-124">The first step is to create a new application.</span></span> <span data-ttu-id="f35db-125">Aprire un prompt dei comandi e creare una nuova directory per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="f35db-125">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="f35db-126">impostandola come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f35db-126">Make that the current directory.</span></span> <span data-ttu-id="f35db-127">Digitare il comando `dotnet new console` al prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="f35db-127">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="f35db-128">Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="f35db-128">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="f35db-129">Prima di iniziare ad apportare modifiche, è opportuno ripercorrere i passaggi necessari per eseguire l'applicazione Hello World semplice.</span><span class="sxs-lookup"><span data-stu-id="f35db-129">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="f35db-130">Dopo aver creato l'applicazione, digitare `dotnet restore` ([vedere la nota](#dotnet-restore-note)) al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f35db-130">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="f35db-131">Questo comando esegue il processo di ripristino dei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="f35db-131">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="f35db-132">Lo strumento NuGet consente di gestire pacchetti .NET.</span><span class="sxs-lookup"><span data-stu-id="f35db-132">NuGet is a .NET package manager.</span></span> <span data-ttu-id="f35db-133">Questo comando scarica eventuali dipendenze mancanti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="f35db-133">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="f35db-134">Poiché si tratta di un nuovo progetto, non è ancora presente alcuna dipendenza e con la prima esecuzione verrà quindi scaricato .NET Core Framework.</span><span class="sxs-lookup"><span data-stu-id="f35db-134">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="f35db-135">Dopo questo passaggio iniziale, sarà solo necessario eseguire `dotnet restore` ([vedere la nota](#dotnet-restore-note)) quando si aggiungere nuovi pacchetti di dipendenti o aggiornare le versioni di una delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="f35db-135">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span> <span data-ttu-id="f35db-136">Questo processo consente anche di creare il file di blocco del progetto (project.lock.json) nella directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="f35db-136">This process also creates the project lock file (project.lock.json) in your project directory.</span></span> <span data-ttu-id="f35db-137">Con questo file è possibile gestire le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="f35db-137">This file helps to manage the project dependencies.</span></span> <span data-ttu-id="f35db-138">Contiene infatti il percorso locale di tutte le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="f35db-138">It contains the local location of all the project dependencies.</span></span> <span data-ttu-id="f35db-139">Non è necessario inserire il file nel controllo del codice sorgente; verrà generato quando si esegue `dotnet restore` ([vedere la nota](#dotnet-restore-note)).</span><span class="sxs-lookup"><span data-stu-id="f35db-139">You do not need to put the file in source control; it will be generated when you run `dotnet restore` ([see note](#dotnet-restore-note)).</span></span> 

<span data-ttu-id="f35db-140">Dopo aver ripristinato i pacchetti, eseguire `dotnet build`</span><span class="sxs-lookup"><span data-stu-id="f35db-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="f35db-141">per avviare il motore di compilazione e creare il file eseguibile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f35db-141">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="f35db-142">Eseguire infine `dotnet run` per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f35db-142">Finally, you execute `dotnet run` to run your application.</span></span>  

<span data-ttu-id="f35db-143">Il codice dell'applicazione Hello World semplice è tutto contenuto in Program.cs.</span><span class="sxs-lookup"><span data-stu-id="f35db-143">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="f35db-144">Aprire il file con un editor di testo</span><span class="sxs-lookup"><span data-stu-id="f35db-144">Open that file with your favorite text editor.</span></span> <span data-ttu-id="f35db-145">per effettuare subito le prime modifiche.</span><span class="sxs-lookup"><span data-stu-id="f35db-145">We’re about to make our first changes.</span></span>
<span data-ttu-id="f35db-146">Nella parte iniziale del file è presente un'istruzione using:</span><span class="sxs-lookup"><span data-stu-id="f35db-146">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="f35db-147">Questa istruzione indica al compilatore che qualsiasi tipo dello spazio dei nomi `System` rientra nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="f35db-147">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="f35db-148">Come altri linguaggi orientati agli oggetti, anche C# ricorre agli spazi dei nomi per organizzare i tipi.</span><span class="sxs-lookup"><span data-stu-id="f35db-148">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="f35db-149">Il programma Hello World non è diverso</span><span class="sxs-lookup"><span data-stu-id="f35db-149">This hello world program is no different.</span></span> <span data-ttu-id="f35db-150">ed è incluso nello spazio dei nomi `ConsoleApplication`.</span><span class="sxs-lookup"><span data-stu-id="f35db-150">You can see that the program is enclosed in the `ConsoleApplication` namespace.</span></span> <span data-ttu-id="f35db-151">Non essendo un nome molto descrittivo, è opportuno modificarlo in `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="f35db-151">That’s not a very descriptive name, so change it to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="f35db-152">Lettura e restituzione del file</span><span class="sxs-lookup"><span data-stu-id="f35db-152">Reading and Echoing the File</span></span>
<span data-ttu-id="f35db-153">La prima funzionalità da aggiungere è la capacità di leggere un file di testo e visualizzare tutto il testo nella console.</span><span class="sxs-lookup"><span data-stu-id="f35db-153">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="f35db-154">Si aggiungerà innanzitutto un file di testo.</span><span class="sxs-lookup"><span data-stu-id="f35db-154">First, let’s add a text file.</span></span> <span data-ttu-id="f35db-155">Copiare il file [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) dal repository GitHub di questo [esempio](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) alla directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="f35db-155">Copy the [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="f35db-156">Questo file verrà usato come script per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f35db-156">This will serve as the script for your application.</span></span> <span data-ttu-id="f35db-157">Per informazioni su come scaricare l'app di esempio per questo argomento, vedere le istruzioni nell'argomento [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="f35db-157">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="f35db-158">Aggiungere quindi il metodo seguente alla classe Program (immediatamente sotto il metodo `Main`):</span><span class="sxs-lookup"><span data-stu-id="f35db-158">Next, add the following method in your Program class (right below the `Main` method):</span></span>

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

<span data-ttu-id="f35db-159">Questo metodo usa tipi provenienti da due nuovi spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f35db-159">This method uses types from two new namespaces.</span></span> <span data-ttu-id="f35db-160">Per eseguirne la compilazione è necessario aggiungere le due righe seguenti all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="f35db-160">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="f35db-161">L'interfaccia `IEnumerable<T>` è definita nello spazio dei nomi `System.Collections.Generic`.</span><span class="sxs-lookup"><span data-stu-id="f35db-161">The `IEnumerable<T>` interface is defined in the `System.Collections.Generic` namespace.</span></span> <span data-ttu-id="f35db-162">La classe <xref:System.IO.File> è definita nello spazio dei nomi `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="f35db-162">The <xref:System.IO.File> class is defined in the `System.IO` namespace.</span></span>

<span data-ttu-id="f35db-163">Questo metodo è un tipo speciale di metodo C# denominato *metodo enumeratore*.</span><span class="sxs-lookup"><span data-stu-id="f35db-163">This method is a special type of C# method called an *Enumerator method*.</span></span> <span data-ttu-id="f35db-164">I metodi enumeratore restituiscono sequenze che vengono valutate in modo differito.</span><span class="sxs-lookup"><span data-stu-id="f35db-164">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="f35db-165">In altre parole, ogni elemento della sequenza viene generato nel momento in cui viene richiesto dal codice che utilizza la sequenza.</span><span class="sxs-lookup"><span data-stu-id="f35db-165">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="f35db-166">I metodi enumeratore contengono una o più istruzioni `yield return`.</span><span class="sxs-lookup"><span data-stu-id="f35db-166">Enumerator methods are methods that contain one or more `yield return` statements.</span></span> <span data-ttu-id="f35db-167">L'oggetto restituito dal metodo `ReadFrom` contiene il codice per generare ogni elemento della sequenza.</span><span class="sxs-lookup"><span data-stu-id="f35db-167">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="f35db-168">In questo esempio, ciò consiste nella lettura della riga di testo successiva dal file di origine e nella restituzione della stringa.</span><span class="sxs-lookup"><span data-stu-id="f35db-168">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="f35db-169">Ogni volta che il codice chiamante richiede l'elemento successivo della sequenza, il codice legge la riga di testo successiva dal file e la restituisce.</span><span class="sxs-lookup"><span data-stu-id="f35db-169">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="f35db-170">Quando il file è stato letto completamente, la sequenza indica che non sono presenti altri elementi.</span><span class="sxs-lookup"><span data-stu-id="f35db-170">When the file has been completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="f35db-171">Altri due elementi della sintassi C# possono risultare nuovi all'utente.</span><span class="sxs-lookup"><span data-stu-id="f35db-171">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="f35db-172">L'istruzione `using` gestisce la pulizia delle risorse in questo metodo.</span><span class="sxs-lookup"><span data-stu-id="f35db-172">The `using` statement in this method manages resource cleanup.</span></span> <span data-ttu-id="f35db-173">La variabile inizializzata nell'istruzione `using` (`reader`, in questo esempio) deve implementare l'interfaccia `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="f35db-173">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the `IDisposable` interface.</span></span> <span data-ttu-id="f35db-174">L'interfaccia <xref:System.IDisposable> definisce un singolo metodo, `Dispose`, che deve essere chiamato quando deve essere rilasciata la risorsa.</span><span class="sxs-lookup"><span data-stu-id="f35db-174">The <xref:System.IDisposable> interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="f35db-175">Il compilatore genera la chiamata quando l'esecuzione raggiunge la parentesi graffa di chiusura dell'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="f35db-175">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="f35db-176">Il codice generato dal compilatore assicura che la risorsa venga rilasciata anche se viene generata un'eccezione dal codice nel blocco definito tramite l'istruzione using.</span><span class="sxs-lookup"><span data-stu-id="f35db-176">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="f35db-177">La variabile `reader` viene definita tramite la parola chiave `var`.</span><span class="sxs-lookup"><span data-stu-id="f35db-177">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="f35db-178">`var` definisce una *variabile locale tipizzata in modo implicito*,</span><span class="sxs-lookup"><span data-stu-id="f35db-178">`var` defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="f35db-179">ovvero il tipo della variabile è determinato dal tipo in fase di compilazione dell'oggetto assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="f35db-179">That means the type of the variable is determined by the compile time type of the object assigned to the variable.</span></span> <span data-ttu-id="f35db-180">Qui, ovvero il valore restituito dal <xref:System.IO.File.OpenText(System.String)> metodo, ovvero un <xref:System.IO.StreamReader> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f35db-180">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>
 
<span data-ttu-id="f35db-181">Si compilerà ora il codice per leggere il file nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="f35db-181">Now, let’s fill in the code to read the file in the `Main` method:</span></span> 

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line); 
}
```

<span data-ttu-id="f35db-182">Eseguire il programma, usando `dotnet run` in modo da poter visualizzare ogni riga visualizzata nella console.</span><span class="sxs-lookup"><span data-stu-id="f35db-182">Run the program (using `dotnet run` and you can see every line printed out to the console).</span></span>  

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="f35db-183">Aggiunta di ritardi e formattazione dell'output</span><span class="sxs-lookup"><span data-stu-id="f35db-183">Adding Delays and Formatting output</span></span>
<span data-ttu-id="f35db-184">Il testo restituito viene visualizzato troppo velocemente per potere essere letto a voce alta.</span><span class="sxs-lookup"><span data-stu-id="f35db-184">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="f35db-185">È quindi necessario aggiungere ritardi nell'output.</span><span class="sxs-lookup"><span data-stu-id="f35db-185">Now you need to add the delays in the output.</span></span> <span data-ttu-id="f35db-186">Si inizierà creando codice di base che consenta l'elaborazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="f35db-186">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="f35db-187">Questi primi passaggi dovranno tuttavia seguire alcuni anti-pattern,</span><span class="sxs-lookup"><span data-stu-id="f35db-187">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="f35db-188">evidenziati nei commenti mentre si aggiunge il codice, e il codice verrà aggiornato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="f35db-188">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="f35db-189">Questa sezione è articolata in due fasi.</span><span class="sxs-lookup"><span data-stu-id="f35db-189">There are two steps to this section.</span></span> <span data-ttu-id="f35db-190">Nella prima fase si aggiornerà il metodo iteratore in modo che restituisca singole parole anziché righe intere.</span><span class="sxs-lookup"><span data-stu-id="f35db-190">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="f35db-191">A questo scopo è necessario apportare le modifiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="f35db-191">That’s done with these modifications.</span></span> <span data-ttu-id="f35db-192">Sostituire la funzione `yield return line;` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f35db-192">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="f35db-193">Sarà quindi necessario modificare il modo in cui vengono usate le righe del file e aggiungere un ritardo dopo la scrittura di ogni parola.</span><span class="sxs-lookup"><span data-stu-id="f35db-193">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="f35db-194">Sostituire l'istruzione `Console.WriteLine(line)` nel metodo `Main` con il blocco seguente:</span><span class="sxs-lookup"><span data-stu-id="f35db-194">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

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

<span data-ttu-id="f35db-195">La classe `Task` si trova nello spazio dei nomi `System.Threading.Tasks` ed è quindi necessario aggiungere l'istruzione `using` all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="f35db-195">The `Task` class is in the `System.Threading.Tasks` namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="f35db-196">Eseguire l'esempio e verificare l'output.</span><span class="sxs-lookup"><span data-stu-id="f35db-196">Run the sample, and check the output.</span></span> <span data-ttu-id="f35db-197">Ogni singola parola viene ora visualizzata, seguita da un ritardo di 200 ms.</span><span class="sxs-lookup"><span data-stu-id="f35db-197">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="f35db-198">L'output visualizzato mostra tuttavia alcuni problemi perché il file di testo di origine presenta più righe con oltre 80 caratteri senza interruzione di riga,</span><span class="sxs-lookup"><span data-stu-id="f35db-198">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="f35db-199">che possono risultare difficili da leggere durante lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="f35db-199">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="f35db-200">Questo problema è facile da risolvere.</span><span class="sxs-lookup"><span data-stu-id="f35db-200">That’s easy to fix.</span></span> <span data-ttu-id="f35db-201">Basta tenere traccia della durata di ogni riga e generare una nuova riga ogni volta che la lunghezza raggiunge una determinata soglia.</span><span class="sxs-lookup"><span data-stu-id="f35db-201">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="f35db-202">Dichiarare una variabile locale dopo la dichiarazione di `words` che contiene la lunghezza di riga:</span><span class="sxs-lookup"><span data-stu-id="f35db-202">Declare a local variable after the declaration of `words` that holds the line length:</span></span>

```csharp
var lineLength = 0;
```
 
<span data-ttu-id="f35db-203">Aggiungere quindi il codice seguente dopo l'istruzione `yield return word + " ";` (prima della parentesi graffa di chiusura):</span><span class="sxs-lookup"><span data-stu-id="f35db-203">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```
 
<span data-ttu-id="f35db-204">Eseguire l'esempio. Sarà possibile ora leggere ad alta voce alla velocità prestabilita.</span><span class="sxs-lookup"><span data-stu-id="f35db-204">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="f35db-205">Attività asincrone</span><span class="sxs-lookup"><span data-stu-id="f35db-205">Async Tasks</span></span>
<span data-ttu-id="f35db-206">In questa fase finale si aggiungerà il codice per scrivere l'output in modo asincrono in un'attività e si eseguirà anche un'altra attività per leggere l'input dell'utente, nel caso in cui si voglia velocizzare o rallentare la visualizzazione del testo.</span><span class="sxs-lookup"><span data-stu-id="f35db-206">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display.</span></span> <span data-ttu-id="f35db-207">Sarà necessario eseguire alcuni passaggi ma, al termine, saranno implementati tutti gli aggiornamenti necessari.</span><span class="sxs-lookup"><span data-stu-id="f35db-207">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="f35db-208">Il primo passaggio consiste nel creare un metodo di restituzione asincrono <xref:System.Threading.Tasks.Task> che rappresenta il codice creato finora per leggere e visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="f35db-208">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="f35db-209">Aggiungere questo metodo alla classe `Program` (tratto dal corpo del metodo `Main`):</span><span class="sxs-lookup"><span data-stu-id="f35db-209">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="f35db-210">Si noteranno due modifiche.</span><span class="sxs-lookup"><span data-stu-id="f35db-210">You’ll notice two changes.</span></span> <span data-ttu-id="f35db-211">Nel corpo del metodo, anziché chiamare <xref:System.Threading.Tasks.Task.Wait> per attendere in modo sincrono il completamento di un'attività, questa versione usa la parola chiave `await`.</span><span class="sxs-lookup"><span data-stu-id="f35db-211">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="f35db-212">A questo scopo, è necessario aggiungere il modificatore `async` alla firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="f35db-212">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="f35db-213">Il metodo restituisce `Task`.</span><span class="sxs-lookup"><span data-stu-id="f35db-213">This method returns a `Task`.</span></span> <span data-ttu-id="f35db-214">Osservare inoltre come non siano presenti istruzioni return che restituiscono un oggetto `Task`.</span><span class="sxs-lookup"><span data-stu-id="f35db-214">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="f35db-215">L'oggetto `Task`, infatti, viene creato dal codice che il compilatore genera quando si usa l'operatore `await`.</span><span class="sxs-lookup"><span data-stu-id="f35db-215">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="f35db-216">È possibile immaginare quindi che il metodo restituisca l'oggetto quando raggiunge la parola chiave `await`.</span><span class="sxs-lookup"><span data-stu-id="f35db-216">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="f35db-217">L'oggetto `Task` restituito indica che il lavoro non è stato completato.</span><span class="sxs-lookup"><span data-stu-id="f35db-217">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="f35db-218">Il metodo riprende l'esecuzione quando viene completata l'attività attesa.</span><span class="sxs-lookup"><span data-stu-id="f35db-218">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="f35db-219">Al termine dell'esecuzione, l'oggetto `Task` restituito indica che il lavoro è stato completato.</span><span class="sxs-lookup"><span data-stu-id="f35db-219">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="f35db-220">Il codice chiamante può monitorare l'oggetto `Task` restituito per determinare quando è stato completato.</span><span class="sxs-lookup"><span data-stu-id="f35db-220">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="f35db-221">È possibile chiamare questo nuovo metodo nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="f35db-221">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="f35db-222">Di seguito, nel metodo `Main`, il codice attende in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="f35db-222">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="f35db-223">Quando possibile, è consigliabile usare l'operatore `await` anziché attendere in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="f35db-223">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="f35db-224">Nel metodo `Main` di un'applicazione console, tuttavia, non è possibile usare l'operatore `await`.</span><span class="sxs-lookup"><span data-stu-id="f35db-224">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="f35db-225">Questo comporterebbe infatti la chiusura dell'applicazione prima che siano state completate tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="f35db-225">That would result in the application exiting before all tasks have completed.</span></span>

<span data-ttu-id="f35db-226">È ora necessario scrivere il secondo metodo asincrono per leggere dalla console e verificare la presenza dei caratteri < e >.</span><span class="sxs-lookup"><span data-stu-id="f35db-226">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ and ‘>’ keys.</span></span> <span data-ttu-id="f35db-227">Di seguito è illustrato il metodo da aggiungere per questa attività.</span><span class="sxs-lookup"><span data-stu-id="f35db-227">Here’s the method you add for that task:</span></span>

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
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="f35db-228">Si crea in questo modo un'espressione lambda per rappresentare un delegato <xref:System.Action> che legge un carattere dalla console e modifica una variabile locale che rappresenta il ritardo quando l'utente preme il tasto < o >.</span><span class="sxs-lookup"><span data-stu-id="f35db-228">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ or ‘>’ keys.</span></span> <span data-ttu-id="f35db-229">Questo metodo usa <xref:System.Console.ReadKey> per bloccare l'operazione e attendere che l'utente prema un tasto.</span><span class="sxs-lookup"><span data-stu-id="f35db-229">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="f35db-230">Per completare questa funzionalità, è necessario creare un nuovo metodo di restituzione `async Task` in grado di avviare entrambe le attività (`GetInput` e `ShowTeleprompter`) e gestire i dati condivisi tra di esse.</span><span class="sxs-lookup"><span data-stu-id="f35db-230">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>
 
<span data-ttu-id="f35db-231">A questo punto, occorre creare una classe in grado di gestire i dati condivisi tra le due attività.</span><span class="sxs-lookup"><span data-stu-id="f35db-231">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="f35db-232">Questa classe contiene due proprietà pubbliche: il ritardo e un flag per indicare che il file è stato interamente letto:</span><span class="sxs-lookup"><span data-stu-id="f35db-232">This class contains two public properties: the delay, and a flag to indicate that the file has been completely read:</span></span>

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
    }
}
```

<span data-ttu-id="f35db-233">Inserire la classe in un nuovo file e includerla nello spazio dei nomi `TeleprompterConsole`, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f35db-233">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="f35db-234">Sarà inoltre necessario aggiungere un'istruzione `using static` in modo da poter fare riferimento ai metodi `Min` e `Max` anche senza conoscere il nome dello spazio dei nomi o della classe di inclusione.</span><span class="sxs-lookup"><span data-stu-id="f35db-234">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` method without the enclosing class or namespace names.</span></span> <span data-ttu-id="f35db-235">Un'istruzione `using static` importa i metodi da una classe.</span><span class="sxs-lookup"><span data-stu-id="f35db-235">A `using static` statement imports the methods from one class.</span></span> <span data-ttu-id="f35db-236">Questo comportamento è in contrasto con le istruzioni `using` usate finora che hanno importato tutte le classi da uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f35db-236">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="f35db-237">L'altra nuova funzionalità di linguaggio consiste nell'istruzione `lock`.</span><span class="sxs-lookup"><span data-stu-id="f35db-237">The other language feature that’s new is the `lock` statement.</span></span> <span data-ttu-id="f35db-238">Questa istruzione garantisce che in un determinato momento possa essere presente un solo thread nel codice.</span><span class="sxs-lookup"><span data-stu-id="f35db-238">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="f35db-239">Se un thread si trova nella sezione bloccata, gli altri thread devono attendere che il primo esca da tale sezione.</span><span class="sxs-lookup"><span data-stu-id="f35db-239">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="f35db-240">L'istruzione `lock` usa un oggetto che protegge la sezione bloccata.</span><span class="sxs-lookup"><span data-stu-id="f35db-240">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="f35db-241">Questa classe segue un linguaggio standard per bloccare un oggetto privato nella classe.</span><span class="sxs-lookup"><span data-stu-id="f35db-241">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="f35db-242">Sarà quindi necessario aggiornare i metodi `ShowTeleprompter` e `GetInput` affinché usino il nuovo oggetto `config`.</span><span class="sxs-lookup"><span data-stu-id="f35db-242">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="f35db-243">Scrivere un ultimo metodo `Task` di restituzione dell'oggetto `async`, in grado di avviare entrambe le attività e chiudere la prima attività nel momento in cui viene completata:</span><span class="sxs-lookup"><span data-stu-id="f35db-243">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="f35db-244">Il nuovo metodo qui è la <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> chiamare.</span><span class="sxs-lookup"><span data-stu-id="f35db-244">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="f35db-245">In questo modo si crea un oggetto `Task` che termina non appena viene completata un'attività inclusa nel relativo elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="f35db-245">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="f35db-246">È ora necessario aggiornare i metodi `ShowTeleprompter` e `GetInput` affinché usino l'oggetto `config` per il ritardo:</span><span class="sxs-lookup"><span data-stu-id="f35db-246">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
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
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="f35db-247">Questa nuova versione di `ShowTeleprompter` chiama un nuovo metodo nella classe `TeleprompterConfig`.</span><span class="sxs-lookup"><span data-stu-id="f35db-247">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="f35db-248">A questo punto, è necessario aggiornare `Main` affinché chiami `RunTeleprompter` anziché `ShowTeleprompter`:</span><span class="sxs-lookup"><span data-stu-id="f35db-248">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

<span data-ttu-id="f35db-249">Sarà necessario infine aggiungere il metodo `SetDone` e la proprietà `Done` alla classe `TelePrompterConfig`:</span><span class="sxs-lookup"><span data-stu-id="f35db-249">To finish, you'll need to add the `SetDone` method, and the `Done` property to the `TelePrompterConfig` class:</span></span>

```csharp
public bool Done => done;

private bool done;

public void SetDone()
{
    done = true;    
}
```

## <a name="conclusion"></a><span data-ttu-id="f35db-250">Conclusione</span><span class="sxs-lookup"><span data-stu-id="f35db-250">Conclusion</span></span>
<span data-ttu-id="f35db-251">In questa esercitazione sono state illustrate diverse funzionalità del linguaggio C# e presentate le librerie .NET Core correlate all'uso di applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="f35db-251">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="f35db-252">A partire da queste informazioni è possibile approfondire la conoscenza del linguaggio e delle classi presentate nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="f35db-252">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="f35db-253">Sono state inoltre fornite nozioni di base sulle operazioni di input/output del file e della console e sull'uso bloccante e non bloccante del modello di programmazione asincrona basato sulle attività, è stata offerta una panoramica del linguaggio C# ed è stata descritta l'organizzazione dei programmi C# e degli strumenti e dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f35db-253">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task based Asynchronous programming model, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>
 
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]