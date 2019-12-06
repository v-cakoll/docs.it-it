---
title: Valori restituiti da Main() - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 13d1eda178a4c2580af67ef5a7198e7f0884a7d6
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884397"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="0d2dd-102">Valori restituiti da Main() (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0d2dd-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="0d2dd-103">Il metodo `Main` può restituire `void`:</span><span class="sxs-lookup"><span data-stu-id="0d2dd-103">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="0d2dd-104">Può anche restituire `int`:</span><span class="sxs-lookup"><span data-stu-id="0d2dd-104">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="0d2dd-105">Se il valore restituito da `Main` non viene usato, la restituzione di `void` consente di semplificare leggermente il codice.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-105">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="0d2dd-106">Tuttavia, la restituzione di un valore intero consente al programma di comunicare le informazioni sullo stato ad altri programmi o script che richiamano il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-106">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="0d2dd-107">Il valore restituito da `Main` viene considerato come codice di uscita per il processo.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-107">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="0d2dd-108">Se viene restituito `void` da `Main` il codice di uscita sarà in modo implicito `0`.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-108">If `void` is returned from `Main` the exit code will be implicitly `0`.</span></span> <span data-ttu-id="0d2dd-109">L'esempio seguente illustra come è possibile accedere al valore restituito da `Main`.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-109">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="0d2dd-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d2dd-110">Example</span></span>

<span data-ttu-id="0d2dd-111">Questo esempio usa gli strumenti della riga di comando [.NET Core](../../../core/index.md).</span><span class="sxs-lookup"><span data-stu-id="0d2dd-111">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="0d2dd-112">Per acquisire familiarità con gli strumenti della riga di comando .NET Core, vedere questo [argomento introduttivo](../../../core/tutorials/cli-create-console-app.md).</span><span class="sxs-lookup"><span data-stu-id="0d2dd-112">If you are unfamiliar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/cli-create-console-app.md).</span></span>

<span data-ttu-id="0d2dd-113">Convertire il metodo `Main` in *program.cs* come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0d2dd-113">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="0d2dd-114">Quando si esegue un programma in ambiente Windows, qualsiasi valore restituito dalla funzione `Main` viene archiviato in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-114">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="0d2dd-115">Questa variabile di ambiente può essere recuperata mediante `ERRORLEVEL` da un file batch o mediante `$LastExitCode` da PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-115">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="0d2dd-116">È possibile compilare l'applicazione usando il comando [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-116">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="0d2dd-117">Quindi creare uno script di PowerShell per eseguire l'applicazione e visualizzare il risultato.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-117">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="0d2dd-118">Incollare il codice seguente in un file di testo e salvarlo come `test.ps1` nella cartella che contiene il progetto.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-118">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="0d2dd-119">Eseguire lo script di PowerShell digitando `test.ps1` al prompt di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-119">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="0d2dd-120">Poiché il codice restituisce zero, il file batch indicherà un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-120">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="0d2dd-121">Se tuttavia si modifica MainReturnValTest.cs in modo che restituisca un valore diverso da zero e quindi si ricompila il programma, l'esecuzione successiva dello script di PowerShell segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-121">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

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

## <a name="sample-output"></a><span data-ttu-id="0d2dd-122">Output dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="0d2dd-122">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="0d2dd-123">Valori restituiti da Async Main</span><span class="sxs-lookup"><span data-stu-id="0d2dd-123">Async Main return values</span></span>

<span data-ttu-id="0d2dd-124">I valori restituiti da Async Main trasferiscono il codice boilerplate necessario per la chiamata di metodi asincroni in `Main` a codice generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-124">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="0d2dd-125">In precedenza era necessario scrivere questo costrutto per chiamare codice asincrono e verificare che il programma rimanesse in esecuzione fino al completamento dell'operazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="0d2dd-125">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

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

<span data-ttu-id="0d2dd-126">Ora è possibile usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0d2dd-126">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="0d2dd-127">Il vantaggio della nuova sintassi è che il compilatore genera sempre il codice corretto.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-127">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="0d2dd-128">Codice generato dal compilatore</span><span class="sxs-lookup"><span data-stu-id="0d2dd-128">Compiler generated code</span></span>

<span data-ttu-id="0d2dd-129">Quando il punto di ingresso dell'applicazione restituisce `Task` o `Task<int>` il compilatore genera un nuovo punto di ingresso che chiama il metodo del punto di ingresso dichiarato nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-129">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="0d2dd-130">Supponendo che questo punto di ingresso sia denominato `$GeneratedMain`, il compilatore genera il codice seguente per questi punti di ingresso:</span><span class="sxs-lookup"><span data-stu-id="0d2dd-130">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="0d2dd-131">`static Task Main()`: il compilatore produce l'equivalente di `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="0d2dd-131">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="0d2dd-132">`static Task Main(string[])`: il compilatore produce l'equivalente di `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="0d2dd-132">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="0d2dd-133">`static Task<int> Main()`: il compilatore produce l'equivalente di `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="0d2dd-133">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="0d2dd-134">`static Task<int> Main(string[])`: il compilatore produce l'equivalente di `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span><span class="sxs-lookup"><span data-stu-id="0d2dd-134">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="0d2dd-135">Se negli esempi si fosse usato il modificatore `async` sul metodo `Main` il compilatore avrebbe generato lo stesso codice.</span><span class="sxs-lookup"><span data-stu-id="0d2dd-135">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d2dd-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d2dd-136">See also</span></span>

- [<span data-ttu-id="0d2dd-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0d2dd-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0d2dd-138">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0d2dd-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0d2dd-139">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="0d2dd-139">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="0d2dd-140">Procedura: Visualizzare gli argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="0d2dd-140">How to: Display Command Line Arguments</span></span>](./how-to-display-command-line-arguments.md)
