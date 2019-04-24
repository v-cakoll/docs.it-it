---
title: Valori restituiti da Main() - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: f515268af13ef95b8b6d9a79f71c49d5d4a98d05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149838"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="75c9f-102">Valori restituiti da Main() (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="75c9f-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="75c9f-103">Il metodo `Main` può restituire `void`:</span><span class="sxs-lookup"><span data-stu-id="75c9f-103">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="75c9f-104">Può anche restituire `int`:</span><span class="sxs-lookup"><span data-stu-id="75c9f-104">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="75c9f-105">Se il valore restituito da `Main` non viene usato, la restituzione di `void` consente di semplificare leggermente il codice.</span><span class="sxs-lookup"><span data-stu-id="75c9f-105">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="75c9f-106">Tuttavia, la restituzione di un valore intero consente al programma di comunicare le informazioni sullo stato ad altri programmi o script che richiamano il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="75c9f-106">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="75c9f-107">Il valore restituito da `Main` viene considerato come codice di uscita per il processo.</span><span class="sxs-lookup"><span data-stu-id="75c9f-107">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="75c9f-108">L'esempio seguente illustra come è possibile accedere al valore restituito da `Main`.</span><span class="sxs-lookup"><span data-stu-id="75c9f-108">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="75c9f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="75c9f-109">Example</span></span>

<span data-ttu-id="75c9f-110">Questo esempio usa gli strumenti della riga di comando [.NET Core](../../../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="75c9f-110">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="75c9f-111">Per acquisire familiarità con gli strumenti della riga di comando .NET Core, vedere questo [argomento introduttivo](../../../core/tutorials/using-with-xplat-cli.md).</span><span class="sxs-lookup"><span data-stu-id="75c9f-111">If you are unfamiliar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/using-with-xplat-cli.md).</span></span>

<span data-ttu-id="75c9f-112">Convertire il metodo `Main` in *program.cs* come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="75c9f-112">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="75c9f-113">Quando si esegue un programma in ambiente Windows, qualsiasi valore restituito dalla funzione `Main` viene archiviato in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="75c9f-113">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="75c9f-114">Questa variabile di ambiente può essere recuperata mediante `ERRORLEVEL` da un file batch o mediante `$LastExitCode` da PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75c9f-114">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="75c9f-115">È possibile compilare l'applicazione usando il comando [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="75c9f-115">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="75c9f-116">Quindi creare uno script di PowerShell per eseguire l'applicazione e visualizzare il risultato.</span><span class="sxs-lookup"><span data-stu-id="75c9f-116">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="75c9f-117">Incollare il codice seguente in un file di testo e salvarlo come `test.ps1` nella cartella che contiene il progetto.</span><span class="sxs-lookup"><span data-stu-id="75c9f-117">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="75c9f-118">Eseguire lo script di PowerShell digitando `test.ps1` al prompt di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75c9f-118">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="75c9f-119">Poiché il codice restituisce zero, il file batch indicherà un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="75c9f-119">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="75c9f-120">Se tuttavia si modifica MainReturnValTest.cs in modo che restituisca un valore diverso da zero e quindi si ricompila il programma, l'esecuzione successiva dello script di PowerShell segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="75c9f-120">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="75c9f-121">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="75c9f-121">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="75c9f-122">Valori restituiti da Async Main</span><span class="sxs-lookup"><span data-stu-id="75c9f-122">Async Main return values</span></span>

<span data-ttu-id="75c9f-123">I valori restituiti da Async Main trasferiscono il codice boilerplate necessario per la chiamata di metodi asincroni in `Main` a codice generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="75c9f-123">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="75c9f-124">In precedenza era necessario scrivere questo costrutto per chiamare codice asincrono e verificare che il programma rimanesse in esecuzione fino al completamento dell'operazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="75c9f-124">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="75c9f-125">Ora è possibile usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="75c9f-125">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="75c9f-126">Il vantaggio della nuova sintassi è che il compilatore genera sempre il codice corretto.</span><span class="sxs-lookup"><span data-stu-id="75c9f-126">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="75c9f-127">Codice generato dal compilatore</span><span class="sxs-lookup"><span data-stu-id="75c9f-127">Compiler generated code</span></span>

<span data-ttu-id="75c9f-128">Quando il punto di ingresso dell'applicazione restituisce `Task` o `Task<int>` il compilatore genera un nuovo punto di ingresso che chiama il metodo del punto di ingresso dichiarato nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75c9f-128">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="75c9f-129">Supponendo che questo punto di ingresso sia denominato `$GeneratedMain`, il compilatore genera il codice seguente per questi punti di ingresso:</span><span class="sxs-lookup"><span data-stu-id="75c9f-129">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="75c9f-130">`static Task Main()`: il compilatore produce l'equivalente di `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="75c9f-130">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="75c9f-131">`static Task Main(string[])`: il compilatore produce l'equivalente di `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="75c9f-131">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="75c9f-132">`static Task<int> Main()`: il compilatore produce l'equivalente di `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="75c9f-132">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="75c9f-133">`static Task<int> Main(string[])`: il compilatore produce l'equivalente di `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="75c9f-133">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="75c9f-134">Se negli esempi si fosse usato il modificatore `async` sul metodo `Main` il compilatore avrebbe generato lo stesso codice.</span><span class="sxs-lookup"><span data-stu-id="75c9f-134">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="75c9f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75c9f-135">See also</span></span>

- [<span data-ttu-id="75c9f-136">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="75c9f-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="75c9f-137">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="75c9f-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="75c9f-138">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="75c9f-138">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="75c9f-139">Procedura: Visualizzare gli argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="75c9f-139">How to: Display Command Line Arguments</span></span>](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [<span data-ttu-id="75c9f-140">Procedura: Accedere agli argomenti della riga di comando usando foreach</span><span class="sxs-lookup"><span data-stu-id="75c9f-140">How to: Access Command-Line Arguments Using foreach</span></span>](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
